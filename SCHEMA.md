# Vehora — Database Schema Proposal

This conceptual PostgreSQL schema for the vehicle transport platform is based on the [source functional specification](https://github.com/NothingData/CODOOR/blob/main/README.md) (version 1.0). It shows **proposed** tables, fields, and relationships. It is a data model proposal, not an existing database or a set of SQL migrations.

In the diagrams, `1:N` means one record to many records, and `0..1` means an optional relationship. `PK` is a primary key; `FK` is a foreign key. Primary identifiers use `uuid`, money uses `numeric(18,2)` with a currency code, and timestamps use `timestamptz` in UTC.

## Node overview

```mermaid
flowchart LR
    A[User] --> B[Organization and roles]
    A --> C[Order]
    B --> C
    C --> D[Order items: vehicles]
    D --> E[Offers and assignment]
    E --> F[Trip and load plan]
    F --> G[GPS and delivery events]
    D --> H[Inspections and damage]
    D --> I[Custody transfers and POC/POD]
    C --> J[Pricing and payments]
    F --> K[Carrier payouts]
    D --> L[Incidents and claims]
    C --> M[Chat and notifications]
    B --> N[Document verification]
```

The core chain is `orders → order_items → trip_loads → trips`. An order is the customer's commercial transaction; an order item is one vehicle and its delivery route; a trip is the carrier's physical journey. One order can therefore contain multiple vehicles, and a vehicle can travel on successive trips when it is transferred between carriers or vehicles.

## 1. Accounts, organizations, vehicles, and orders

```mermaid
erDiagram
    users ||--o{ organization_members : belongs_to
    organizations ||--o{ organization_members : has
    organizations ||--o{ organization_sites : has
    locations ||--o{ organization_sites : located_at
    organizations o|--o{ vehicles : owns_or_manages
    users o|--o{ vehicles : saves
    users ||--o{ orders : creates
    organizations o|--o{ orders : places
    orders ||--|{ order_items : contains
    vehicles ||--o{ order_items : transported_as
    locations ||--o{ order_items : pickup
    locations ||--o{ order_items : delivery
    orders ||--o{ quotes : priced_by
    quotes ||--|{ quote_lines : includes
    order_items o|--o{ quote_lines : item_price
    orders ||--o{ change_orders : revised_by

    users {
        uuid id PK
        string email
        string phone
        string status
    }
    organizations {
        uuid id PK
        string type
        string legal_name
        string tax_id
        string status
    }
    organization_members {
        uuid id PK
        uuid organization_id FK
        uuid user_id FK
        string role
        string status
    }
    organization_sites {
        uuid id PK
        uuid organization_id FK
        uuid location_id FK
        string type
    }
    vehicles {
        uuid id PK
        uuid organization_id FK
        uuid owner_user_id FK
        string vin
        string registration_number
        string make_model
        int model_year
        string readiness_status
    }
    locations {
        uuid id PK
        string type
        string address
        string country_code
        decimal latitude
        decimal longitude
    }
    orders {
        uuid id PK
        uuid customer_user_id FK
        uuid customer_organization_id FK
        string status
        string currency
        datetime created_at
    }
    order_items {
        uuid id PK
        uuid order_id FK
        uuid vehicle_id FK
        uuid pickup_location_id FK
        uuid delivery_location_id FK
        string status
        string transport_type
        datetime pickup_window_start
        datetime delivery_window_end
    }
    quotes {
        uuid id PK
        uuid order_id FK
        int version
        decimal total_amount
        string currency
        datetime expires_at
        string status
    }
    quote_lines {
        uuid id PK
        uuid quote_id FK
        uuid order_item_id FK
        string type
        decimal amount
    }
    change_orders {
        uuid id PK
        uuid order_id FK
        uuid previous_quote_id FK
        uuid proposed_quote_id FK
        string reason
        string status
    }
```

`vehicles` stores the current vehicle record. Each `order_items` row also stores a **snapshot** of the VIN, specifications, declared value, technical questionnaire, and contacts at booking time. Later edits to the vehicle record must not rewrite order history. The same rule applies to addresses and time windows. For a private customer, `orders.customer_organization_id` is null; for a business customer, it is required.

| Node | Purpose and important additional fields |
| --- | --- |
| `organization_members` | Company membership and access rights; granular rights may use `roles`, `permissions`, and `role_permissions`. |
| `vehicles` | VIN, registration number, dimensions, weight, powertrain/EV type, stock or lot number, and transport readiness. |
| `order_items` | One vehicle to transport; a snapshot of its condition (`is_running`, keys, damage, equipment), declared value, and pickup/delivery windows. |
| `quotes` / `quote_lines` | Versioned price calculations and line items for transport, extras, protection, taxes, and discounts. The accepted version is attached to the order. |
| `change_orders` | A post-booking change: previous and proposed prices, customer approval, reason, author, and time. |

## 2. Carrier, marketplace, and trip

```mermaid
erDiagram
    organizations ||--o| carrier_profiles : carrier
    carrier_profiles ||--o{ transporters : owns
    carrier_profiles ||--o{ driver_profiles : employs
    users ||--o| driver_profiles : drives_as
    order_items ||--o{ offers : listed_for
    carrier_profiles ||--o{ offers : responds
    carrier_profiles ||--o{ trips : operates
    driver_profiles ||--o{ trips : drives
    transporters ||--o{ trips : used_for
    transporters ||--|{ deck_slots : has
    trips ||--|{ trip_stops : visits
    locations ||--o{ trip_stops : stop_at
    trips ||--o{ trip_loads : carries
    order_items ||--o{ trip_loads : travels_in
    deck_slots ||--o{ trip_loads : allocated_to

    carrier_profiles {
        uuid id PK
        uuid organization_id FK
        string verification_status
        string service_regions
    }
    driver_profiles {
        uuid id PK
        uuid carrier_id FK
        uuid user_id FK
        string licence_class
        string availability_status
    }
    transporters {
        uuid id PK
        uuid carrier_id FK
        string registration_number
        string transporter_vin
        decimal payload_kg
        string status
    }
    deck_slots {
        uuid id PK
        uuid transporter_id FK
        string deck
        int position_number
        decimal max_weight_kg
    }
    offers {
        uuid id PK
        uuid order_item_id FK
        uuid carrier_id FK
        decimal payout_amount
        string currency
        string status
        datetime expires_at
    }
    trips {
        uuid id PK
        uuid carrier_id FK
        uuid driver_id FK
        uuid transporter_id FK
        string status
        datetime planned_start_at
    }
    trip_stops {
        uuid id PK
        uuid trip_id FK
        uuid location_id FK
        int sequence_number
        string stop_type
        datetime eta_at
    }
    trip_loads {
        uuid id PK
        uuid trip_id FK
        uuid order_item_id FK
        uuid deck_slot_id FK
        uuid pickup_stop_id FK
        uuid delivery_stop_id FK
        string status
    }
```

An `offers` row belongs to an order item; an accepted offer selects the carrier. `trip_loads` records the actual assignment. This supports multiple vehicles on one trip and a new row when a vehicle moves to another trip. An order item may have only one active load at a time. `trip_stops` defines the ordered stops, while `deck_slots` capacity and placement must be checked before the load plan is approved.

## 3. Inspection, GPS, documents, and chain of custody

```mermaid
erDiagram
    order_items ||--o{ inspections : inspected_at
    order_items ||--o{ damage_cases : has
    inspections ||--o{ damage_observations : records
    damage_cases ||--o{ damage_observations : observed_as
    inspections ||--o{ media_files : photographed_in
    order_items ||--o{ custody_transfers : handed_over
    inspections o|--o{ custody_transfers : supports
    order_items ||--o{ tracking_events : timeline
    trips o|--o{ tracking_events : context
    trips ||--o{ gps_points : tracked_by
    orders ||--o{ documents : produces
    order_items o|--o{ documents : concerns
    documents ||--o{ signatures : signed_by

    inspections {
        uuid id PK
        uuid order_item_id FK
        uuid actor_user_id FK
        string stage
        int odometer_km
        string fuel_or_charge
        datetime completed_at
    }
    damage_cases {
        uuid id PK
        uuid order_item_id FK
        string vehicle_area
        string damage_type
        datetime first_seen_at
    }
    damage_observations {
        uuid id PK
        uuid inspection_id FK
        uuid damage_case_id FK
        string severity
        string comment
    }
    media_files {
        uuid id PK
        uuid inspection_id FK
        string storage_key
        string sha256
        datetime captured_at
    }
    custody_transfers {
        uuid id PK
        uuid order_item_id FK
        uuid inspection_id FK
        uuid from_user_id FK
        uuid to_user_id FK
        string transfer_type
        datetime transferred_at
    }
    tracking_events {
        uuid id PK
        uuid order_item_id FK
        uuid trip_id FK
        uuid actor_user_id FK
        string event_type
        datetime occurred_at
        datetime received_at
    }
    gps_points {
        uuid id PK
        uuid trip_id FK
        decimal latitude
        decimal longitude
        decimal accuracy_m
        datetime recorded_at
    }
    documents {
        uuid id PK
        uuid order_id FK
        uuid order_item_id FK
        string type
        string storage_key
        string sha256
        int version
    }
    signatures {
        uuid id PK
        uuid document_id FK
        uuid signer_user_id FK
        string method
        datetime signed_at
    }
```

Create an `inspections` row at pickup, delivery, and each handover. A completed inspection is immutable. A persistent `damage_cases.id` links observations of the same damage across inspections. `custody_transfers` stores the sender, receiver, time, location, keys, documents, and links to inspection evidence and signatures. POC, POD, and condition reports are `documents` types. Photos and PDFs live in object storage; PostgreSQL holds their metadata and `storage_key`.

`tracking_events` is an append-only status history; corrections create a new event. Offline clients need a unique `client_event_id`, `occurred_at`, and `received_at` so repeated synchronization does not create duplicates. GPS data belongs to an active trip; the associated order and the viewer's role control access.

## 4. Payments, communication, risk, and configuration

```mermaid
erDiagram
    orders ||--o{ payments : paid_by
    payments ||--o{ refunds : refunded_by
    trips ||--o{ payouts : settled_by
    carrier_profiles ||--o{ payouts : receives
    orders ||--o{ invoices : invoiced_by
    organizations o|--o{ invoices : billed_to
    orders ||--o{ conversations : discussed_in
    conversations ||--o{ messages : contains
    users ||--o{ notifications : receives
    order_items o|--o{ incidents : affects
    trips o|--o{ incidents : occurs_on
    incidents o|--o{ claims : may_open
    order_items ||--o{ claims : claimed_for
    organizations ||--o{ compliance_documents : verified_with
    driver_profiles o|--o{ compliance_documents : verified_with
    transporters o|--o{ compliance_documents : verified_with
    organizations ||--o{ tenant_configs : configures
    users ||--o{ audit_log : acts

    payments {
        uuid id PK
        uuid order_id FK
        string provider_reference
        decimal amount
        string currency
        string status
    }
    refunds {
        uuid id PK
        uuid payment_id FK
        decimal amount
        string status
    }
    payouts {
        uuid id PK
        uuid trip_id FK
        uuid carrier_id FK
        decimal amount
        string currency
        string status
    }
    invoices {
        uuid id PK
        uuid order_id FK
        uuid organization_id FK
        string invoice_number
        decimal total_amount
    }
    conversations {
        uuid id PK
        uuid order_id FK
        string type
    }
    messages {
        uuid id PK
        uuid conversation_id FK
        uuid sender_user_id FK
        string body
        datetime sent_at
    }
    notifications {
        uuid id PK
        uuid user_id FK
        string channel
        string status
    }
    incidents {
        uuid id PK
        uuid order_item_id FK
        uuid trip_id FK
        string category
        string status
    }
    claims {
        uuid id PK
        uuid order_item_id FK
        uuid incident_id FK
        string status
        decimal requested_amount
    }
    compliance_documents {
        uuid id PK
        uuid organization_id FK
        uuid driver_id FK
        uuid transporter_id FK
        string document_type
        string document_number
        string storage_key
        datetime expires_at
        string review_status
    }
    tenant_configs {
        uuid id PK
        uuid organization_id FK
        string config_type
        int version
        datetime effective_at
    }
    audit_log {
        uuid id PK
        uuid actor_user_id FK
        string entity_type
        uuid entity_id
        string action
        datetime created_at
    }
```

A `payments` row stores the payment provider reference and transaction status; Vehora does not store card details. A refund references its original payment, while a payout references the trip and carrier. If settlement must be broken down per vehicle, add `payout_lines` with `trip_load_id` and amount. `compliance_documents` supports an organization, driver, or transporter owner, as well as the document number, issuer, expiration, file, and reviewer. `tenant_configs` versions tariffs, SLAs, White Label settings, and rules; each calculated offer should retain the published rule version used for its price.

## Data integrity and access rules

1. **Tenant isolation.** Business data carries `organization_id`, and access is checked through `organization_members`. A private customer's order is visible only to its participants and authorized Vehora staff. White Label tenants use the same isolation model.
2. **Foreign keys.** An order item requires an order and vehicle; a load requires a trip and order item; a damage observation requires an inspection. Historical records should not be cascade-deleted; close or archive them instead.
3. **Status history.** Store the current order, trip, and payout status for fast reads. Also record every transition in `tracking_events` or a dedicated history table with its actor and reason.
4. **Uniqueness.** Normalize `vehicles.vin`; define VIN uniqueness with multi-organization imports in mind. Also enforce unique `(organization_id, user_id)`, `(trip_id, sequence_number)`, `(transporter_id, deck, position_number)`, and offline `client_event_id` values.
5. **Evidence.** Inspections, signed documents, custody transfers, financial transactions, and audit records retain their versions and do not overwrite earlier entries. Media records retain a hash and server timestamp.
6. **Privacy.** Precise GPS coordinates and documents are available according to role and the active transport period. Set retention periods for GPS, messages, and personal data, with separate support for a `legal_hold`.
7. **Performance.** Index all foreign keys, `orders(status, created_at)`, `order_items(vehicle_id, status)`, `tracking_events(order_item_id, occurred_at)`, `gps_points(trip_id, recorded_at)`, and compliance document expiration. Large GPS, event, and audit tables can be partitioned by time.
8. **Ownership.** A vehicle belongs to a private user or an organization. A compliance document belongs to exactly one organization, driver, or transporter. An incident can concern an entire trip, one order item, or both.

## Implementation phases

**MVP:** accounts, carrier organization, vehicles, orders and items, pricing and payment, offers, trips, drivers and transporters, inspections and damage, POC/POD, GPS and timeline, chat, notifications, Change Orders, compliance, payouts, and audit.

**Later phases:** dealer branches and bulk import, detailed multi-vehicle load planning, claims and returns, subscriptions, White Label, advanced rules, AI, and anti-fraud. The diagrams show the target model; later-phase tables can be introduced as the product expands.
