# CODOOR

## Platformă digitală pentru transportul de automobile

**Specificație funcțională și concept de produs**  
Versiune: 1.0  
Statut: propunere pentru analiză, estimare și dezvoltare

---

## 1. Rezumat executiv
CODOOR gestionează întregul proces

```text
Solicitare ofertă → Calcul preț → Rezervare și plată
→ Selectarea transportatorului → Inspecție și preluare
→ Transport cu GPS → Predare și dovadă de livrare
→ Decontare, rating și suport post-livrare
```

Platforma include:

- portal pentru clienți;
- Dealer Portal pentru clienți business;
- portal pentru companii de transport;
- aplicație mobilă pentru șoferi;
- marketplace de comenzi;
- calcul dinamic al prețului;
- Vehicle Inspection System;
- planificarea încărcării transportorului auto;
- GPS, ETA și Vehicle Tracking Timeline;
- chat în timp real;
- Control Tower pentru operațiuni;
- plăți, comisioane și decontări;
- contracte și documente electronice;
- incidente, retururi, claims și despăgubiri;
- verificarea partenerilor și combaterea fraudei;
- funcții AI pentru inspecție, matching și operațiuni;
- soluție White Label pentru clienți enterprise.

---

## 2. Obiective

- rezervare rapidă și transparentă;
- preț clar înainte de plată;
- selectarea transportatorului potrivit;
- reducerea kilometrilor fără încărcătură;
- utilizarea eficientă a pozițiilor de pe transportor;
- verificarea companiilor, șoferilor și asigurărilor;
- urmărirea transportului în timp real;
- documentarea stării automobilului la fiecare transfer;
- reducerea daunelor, disputelor și fraudei;
- automatizarea plăților și decontărilor;
- experiență unitară pentru client, dealer și transportator;

---

## 3. Servicii și limite

### 3.1. Servicii acceptate

- transport deschis sau închis;
- transport individual sau multi-car;
- automobile funcționale și nefuncționale;
- automobile avariate, dacă pot fi transportate în siguranță;
- automobile electrice și hibride;
- automobile clasice, premium și supercar;
- transfer dealer–dealer și dealer–client;
- colectare de la licitații;
- transport către/din port, terminal, service sau parc securizat;
- relocări pentru leasing, rent-a-car și flote;
- drive-away numai dacă este permis legal și contractual.

### 3.2. Categorii

- autoturisme;
- SUV și 4x4;
- vehicule comerciale ușoare compatibile;
- automobile clasice și de colecție;
- automobile premium și supercar;
- EV și hibride;
- automobile nefuncționale sau avariate;
- automobile de licitație, flotă și leasing.

### 3.3. Excluderi

- bani, arme, substanțe ilegale ori periculoase;
- vehicule fără dovada dreptului de transport;
- vehicule care depășesc limitele tehnice sau legale.

Accesoriile originale — chei, carte service, cablu EV, roată de rezervă și unelte originale — se declară și se consemnează în raportul de predare.

---

## 4. Roluri

| Rol | Responsabilitate |
|---|---|
| Client privat | Comandă și urmărește transportul propriului automobil |
| Client business | Creează volume regulate de transport |
| Dealer | Gestionează stocuri, filiale și livrări către cumpărători |
| Companie leasing/flotă | Coordonează returnări și relocări multiple |
| Companie transport | Administrează șoferi, transportoare și comenzi |
| Șofer | Inspectează, preia, transportă și predă automobilul |
| Dispecer partener | Planifică șoferii, rutele și încărcarea |
| Operator CODOOR | Monitorizează transporturile și asistă participanții |
| Manager Compliance | Verifică identitatea, licențele și asigurările |
| Manager Financiar | Gestionează plăți, rambursări și decontări |
| Manager Claims | Analizează incidentele și despăgubirile |
| Administrator | Configurează platforma, regulile și accesul |

Accesul se acordă prin roluri și permisiuni granulare. Toate acțiunile sensibile sunt auditate.

---

## 5. Portalul clientului

### 5.1. Cont

- înregistrare prin telefon/e-mail;
- verificare OTP;
- autentificare, MFA și recuperare acces;
- profil și date de facturare;
- administrarea sesiunilor;
- persoane autorizate pentru predare/primire;
- acceptarea termenilor și politicilor.

### 5.2. Panou principal

- transporturi active, planificate, finalizate și anulate;
- automobile salvate;
- status și următoarea etapă;
- ETA de preluare/livrare;
- hartă live în perioada autorizată;
- compania și șoferul atribuit;
- mesaje, notificări și Change Orders;
- facturi, rapoarte și POD;
- incidente, claims și review-uri;
- repetarea unei comenzi.

### 5.3. Crearea comenzii

1. Adresa de preluare și livrare.
2. Tipul locației: domiciliu, dealer, licitație, port, service sau parc.
3. VIN, număr de înmatriculare, marcă, model, an și culoare.
4. Masa și dimensiunile, când sunt necesare.
5. Starea tehnică.
6. Fotografii actuale.
7. Data și intervalul dorit.
8. Transport deschis, închis sau individual.
9. Valoarea declarată.
10. Persoanele autorizate.
11. Documentele/release reference.
12. Nivelul de protecție disponibil.

### 5.4. Chestionar tehnic

- motorul pornește;
- automobilul se deplasează;
- direcția și frânele funcționează;
- transmisia intră în neutral;
- frâna de parcare se eliberează;
- roțile se rotesc și pneurile sunt umflate;
- există chei;
- există scurgeri;
- automobilul este coborât sau modificat;
- există piese desprinse;
- bateria EV este deteriorată;
- este necesar troliu, patine sau stivuitor.

Răspunsurile determină eligibilitatea, metoda de încărcare, transportorul și prețul.

### 5.5. Administrarea transportului

- modificarea datelor înainte de termen;
- schimbarea contactelor;
- încărcarea documentelor;
- acceptarea unui Change Order;
- anulare sau reprogramare;
- tracking și istoric complet;
- chat cu șoferul și suportul;
- link temporar pentru o terță persoană;
- descărcarea facturii și rapoartelor;
- deschiderea unei reclamații;
- rating după livrare.

### 5.6. Acces delegat

Expeditorul și destinatarul pot primi acces limitat prin link securizat sau OTP pentru a confirma identitatea, intervalul, inspecția, predarea și primirea fără un cont complet.

---

## 6. Dealer Portal

Dealer Portal este destinat dealerilor, grupurilor auto, flotelor, companiilor de leasing, rent-a-car și remarketing.

### 6.1. Organizație

- companie, grupuri și filiale;
- showroom-uri și parcuri;
- departamente și centre de cost;
- entități de facturare;
- utilizatori și roluri;
- limite bugetare;
- aprobări interne;
- conturi API și SSO.

Roluri: owner, transport manager, branch manager, booking agent, vehicle inspector, accountant, viewer și integration account.

### 6.2. Registrul automobilelor

- VIN și număr de înmatriculare;
- stock/lot/fleet number;
- marcă, model, an și culoare;
- locație și status de pregătire;
- valoare declarată;
- fotografii și inspecții;
- documente;
- cumpărător/filială destinatară;
- transport atribuit;
- istoricul relocărilor.

Datele se adaugă manual, prin CSV/Excel sau API din DMS, ERP, CRM ori licitații.

### 6.3. Comenzi în masă

- import de sute de VIN-uri;
- validare și preview;
- grupare după origine/destinație;
- loturi de transport;
- selecție single/multi-car;
- interval comun sau individual;
- cost total și per automobil;
- erori la nivel de rând;
- șabloane;
- aprobare bugetară;
- creare într-o singură operațiune.

### 6.4. Scenarii

- transfer între filiale;
- livrare către cumpărător;
- colectare trade-in;
- returnare leasing/rent-a-car;
- transport către service/bodyshop;
- licitație și remarketing;
- parc securizat;
- dealer–port și port–dealer;
- echilibrarea stocului.

### 6.5. Monitorizare și finanțe

- hartă și ETA pentru întreaga organizație;
- întârzieri și transporturi neatribuite;
- documente lipsă și automobile nepregătite;
- Vehicle Condition Reports;
- Change Orders, incidente și claims;
- SLA per transportator;
- tarife contractuale;
- purchase orders și credit account;
- factură consolidată detaliată per VIN;
- TVA, centre de cost și reconciliere;
- export CSV/PDF.

### 6.6. Integrări și rapoarte

- DMS, CRM, ERP și contabilitate;
- inventory și vehicle data provider;
- platforme de licitații și leasing;
- REST API și webhooks;
- SSO SAML/OIDC;
- durată Ready-to-Pickup;
- punctualitate și cost per automobil;
- costuri de așteptare/depozitare;
- damage/claim rate;
- performanță filială și transportator.

---

## 7. Portalul transportatorului

### 7.1. Onboarding și verificare

1. Cont și contacte verificate.
2. Date juridice, fiscale și bancare.
3. Verificarea reprezentantului/beneficiarilor, dacă este necesar.
4. Licențe și asigurări.
5. Transportoare și șoferi.
6. Regiuni și servicii.
7. Acord de parteneriat semnat.
8. Review Compliance.
9. Activarea marketplace-ului.

Statusuri: `Draft → Submitted → Under Review → Information Required → Approved → Suspended → Rejected`.

### 7.2. Flotă

- tip și configurație;
- număr și VIN transporter;
- masă proprie, payload și limite pe axe;
- deck positions și dimensiuni;
- rampă, hidraulică și troliu;
- compatibilitate EV/non-running/low-clearance;
- fotografii și echipament;
- asigurări și inspecții;
- status activ, ocupat, service sau blocat.

Documentele expirate și defectele critice blochează alocarea.

### 7.3. Echipă și dispecerat

- owner, manager, dispatcher, driver și accountant;
- invitații și permisiuni;
- planificarea încărcării;
- GPS și incidente;
- timp de condus și pauze.

### 7.4. Marketplace și finanțe

- listă/hartă de comenzi;
- filtre și recomandări;
- payout, distanță și durată;
- acceptare fixă sau bid;
- watchlist și rute preferate;
- backload și capacitate liberă;
- verificare compatibilitate;
- sold estimat, blocat și disponibil;
- bonusuri, comisioane și TVA;
- Express Pay;
- statement, invoice și reconciliere;
- dispută financiară.

---

## 8. Aplicația mobilă CODOOR Driver

Aplicația acoperă întregul program al șoferului și funcționează offline pentru operațiunile critice.

### 8.1. Securitate și profil

- login, MFA/OTP, PIN și biometrie;
- dispozitive de încredere și logout de la distanță;
- verificarea identității în funcție de risc;
- Driver Terms, GPS consent și privacy notice;
- companie, permis, documente și certificări;
- tipuri de transporter și regiuni autorizate;
- rating, punctualitate și transporturi finalizate;
- cursuri, restricții și expirări.

### 8.2. Statusuri

`Offline → Available → Scheduled → Driving to Pickup → At Pickup → Inspecting → Loading → In Transit → On Break → At Delivery → Unloading → Completed`.

Există și statusul `Incident`. Etapele importante sunt generate din geozone și acțiuni verificate.

### 8.3. Ecran principal

- tura și transporterul;
- următoarea locație;
- ETA și distanță;
- automobile la bord;
- plan de încărcare;
- alerte și mesaje;
- venit estimat;
- timp de lucru rămas;
- `Start`, `Navigate`, `Arrived`, `SOS`;
- indicator offline/sincronizare.

### 8.4. Marketplace mobil

- hartă și listă;
- payout și cheltuieli estimate;
- distanță totală și kilometri goi;
- tipul/starea automobilului;
- open/enclosed și running/non-running;
- intervale;
- compatibilitate transporter;
- accept, bid, decline sau watchlist;
- conflicte de program/documente;
- completarea rutelor existente.

### 8.5. Checklist înainte de tură

- numărul transporterului și kilometraj;
- combustibil/încărcare;
- pneuri și lumini;
- rampă, hidraulică și troliu;
- chingi, opritoare și PPE;
- avarii existente;
- documente și tahograf;
- raportarea defectului;
- blocarea pornirii la defect critic.

### 8.6. Preluarea automobilului

```text
Navigare și GPS
→ Sosire confirmată prin geozonă
→ Contact autorizat și OTP/release code
→ Scanare VIN și număr
→ Inspecție și Damage Map
→ Chei, kilometraj, fuel/charge și documente
→ Change Order dacă există diferențe
→ Semnătura expeditorului
→ Încărcare conform Load Plan
→ Fotografii poziție și fixare
→ Proof of Collection și transfer de custodie
```

### 8.7. Transport

- GPS heartbeat și ETA;
- navigație și rută pentru transporter, dacă există date;
- avertismente pentru poduri joase, taxe și feribot;
- abatere de la traseu;
- pauze și timp de condus;
- parcare securizată;
- manifestul automobilelor;
- întârziere și incident;
- transfer către alt șofer;
- cache offline;
- fără interacțiuni periculoase în timpul condusului.

### 8.8. Livrarea

1. Sosire prin geozonă.
2. Verificarea destinatarului OTP/QR.
3. Confirmarea unei zone sigure.
4. Verificarea VIN-ului.
5. Fotografii înainte de eliberarea fixării.
6. Descărcare.
7. Inspecție de livrare.
8. Comparație cu pickup.
9. Predarea cheilor/documentelor.
10. Kilometraj și fuel/charge.
11. Observații și semnătură.
12. Proof of Delivery.
13. Transfer de custodie.
14. Eliberarea poziției pe trailer.

### 8.9. Transfer și offline

Transferul între șoferi sau parcuri cere identificarea ambelor părți, inspecție nouă, chei, poziție, timp, GPS și semnături duble.

Offline funcționează ruta, VIN, inspecția, fotografiile, Damage Map, checklist-ul, semnăturile, evenimentele, incidentele și drafturile POC/POD. Sincronizarea folosește identificatori unici și previne duplicatele.

### 8.10. GPS și confidențialitate

- tracking numai în tura/comanda activă;
- clientul vede doar propria livrare;
- locațiile personale sunt ascunse;
- aplicația afișează tracking-ul activ;
- coordonatele includ acuratețe;
- detectarea GPS spoofing;
- retention limitat;
- accesul angajaților este auditat.

### 8.11. Chat, incident și SOS

- chat cu clientul, dispecerul și suportul;
- text, foto, video, document și voce;
- traducere și răspunsuri rapide;
- incident pentru VIN greșit, chei lipsă, mașină nefuncțională, scurgeri, EV, locație închisă, destinatar absent, accident, daună, furt sau amenințare;
- SOS trimite locația, transporterul, comanda și VIN-urile.

### 8.12. Rating și niveluri

Clientul evaluează punctualitatea, comunicarea, profesionalismul, grija față de automobil, inspecția și predarea.

Platforma calculează:

- on-time rate;
- cancellation rate;
- accepted-to-completed rate;
- incident/claim rate;
- completitudinea inspecțiilor;
- acoperirea GPS/milestones;
- timpul de răspuns;
- respectarea checklist-urilor.

Niveluri posibile: Verified, Experienced, Professional, Elite, Luxury/Classic Approved, Enclosed Approved, EV Trained și Recovery Specialist. Rating-ul poate fi contestat și nu înlocuiește compliance-ul.

### 8.13. Venituri și training

- payout per comandă;
- sold estimat, blocat și disponibil;
- bonusuri și taxe aprobate;
- Express Pay;
- facturi și TVA;
- venit per kilometru/oră;
- contestație financiară;
- cursuri de onboarding, încărcare, inspecție, EV, luxury, non-running, incidente, privacy și conduită.

---

## 9. Vehicle Inspection System

Modulul creează dovezi standardizate despre starea automobilului la pickup, încărcare, handover, depozitare, incident, descărcare, delivery și retur.

### 9.1. Identificare

- VIN manual, barcode și OCR;
- număr de înmatriculare;
- marcă, model, an, culoare;
- lot/stock/fleet number;
- kilometraj;
- chei;
- combustibil/încărcare;
- running/non-running.

Neconcordanța VIN/plate blochează pickup până la decizia operatorului.

### 9.2. Fotografii obligatorii

- față, spate și ambele laterale;
- patru colțuri;
- plafon, dacă poate fi fotografiat sigur;
- fiecare jantă și pneu;
- geamuri;
- interior și bord;
- kilometraj și martori;
- VIN plate;
- chei și accesorii;
- fiecare daună în plan general și close-up.

Aplicația verifică lumina, claritatea și unghiul. Media include inspection ID, timestamp server, GPS și watermark. Imaginile externe sunt interzise sau marcate separat.

### 9.3. Damage Map

- scratch, dent, chip și crack;
- piesă spartă/lipsă;
- vopsea, rugină, jantă, pneu și geam;
- interior;
- avertizare mecanică;
- scurgere;
- daună de accident.

Fiecare marcaj are zonă, severitate, dimensiune, comentariu, fotografii și Damage ID persistent.

### 9.4. Checklist și semnare

- motor, deplasare, direcție și frâne;
- neutral și parking brake;
- roți, pneuri și gardă la sol;
- uși și piese securizate;
- scurgeri;
- alarmă/immobiliser;
- EV transport mode;
- metoda sigură de încărcare.

Expeditorul și șoferul verifică raportul, apoi semnează sau folosesc OTP. Refuzul semnării pornește un exception workflow.

### 9.5. Comparație și raport final

Pickup și delivery sunt afișate side-by-side cu overlay al daunelor. AI poate sugera diferențe, dar o persoană confirmă rezultatul.

Vehicle Condition Report include VIN, participanți, timp, GPS, fotografii, Damage Map, checklist, kilometraj, fuel/charge, chei, observații, semnături, hash și QR de verificare. Inspecțiile sunt append-only.

---

## 10. Planificatorul încărcării

### 10.1. Model transporter

- tip, configurație și payload;
- masă proprie și limite pe axe;
- poziții upper/lower deck;
- dimensiunea și limita fiecărui slot;
- platforme reglabile;
- înălțime totală;
- rampă și troliu;
- compatibilitate non-running, EV și low-clearance.

### 10.2. Model automobil

- lungime, lățime, înălțime și masă;
- ampatament și console;
- gardă la sol;
- running/non-running;
- roți și puncte de tractare;
- EV/ICE;
- valoare declarată;
- ordine pickup/delivery;
- cerințe speciale.

### 10.3. Editor și optimizare

- schemă 2D/3D și drag-and-drop;
- slot liber, ocupat sau rezervat;
- verificarea compatibilității;
- masă pe axe și înălțime;
- ordine de încărcare/descărcare;
- avertisment de blocare a unui automobil;
- fotografii per poziție;
- optimizare după rută, ferestre, greutate, număr de rearanjări, backload, valoare, non-running și timp legal de condus;
- explicația planului automat.

### 10.4. Flux de încărcare

1. Plan aprobat.
2. Scanare VIN.
3. Inspecție completă.
4. Poziție afișată.
5. Poziție reală confirmată.
6. Checklist de fixare.
7. Fotografii ale mașinii și chingilor.
8. Recalcularea limitelor.
9. Manifest semnat.
10. Status `Load Verified`.

Plecarea este blocată la VIN greșit, depășirea limitelor, lipsa inspecției, fotografiilor, fixării sau aprobării.

---

## 11. Marketplace și matching

Modele: alocare automată, acceptare fixă, bid, preferred fleet și dispecerizare manuală.

Matching-ul analizează:

- compatibilitatea automobil–transporter;
- running/non-running;
- distanța până la pickup;
- kilometri goi și direcția rutei;
- sloturi disponibile;
- intervale;
- rating și experiență;
- documente/asigurări;
- punctualitate, anulări și claims;
- certificări;
- cost;
- timp legal de condus.

Decizia trebuie să fie explicabilă. La anulare, întârziere sau defecțiune se activează rescue: incident, localizare, replacement carrier, handover, ETA nou și informarea clientului.

---

## 12. Preț dinamic

```text
Preț client = transport + suplimente + protecție + taxe + serviciu
Marjă CODOOR = preț client − payout − costuri de plată − costuri operaționale
```

Factori:

- distanță, timp și kilometri goi;
- open/enclosed și single/multi-car;
- dimensiuni, masă și gardă;
- running/non-running;
- troliu, patine sau stivuitor;
- daune la roți/direcție/suspensie;
- luxury/classic/supercar;
- valoare declarată;
- urgență și flexibilitate;
- cerere și capacitate regională;
- drum, feribot, port și vamă;
- așteptare și acces restricționat;
- discount multi-vehicle și backload;
- marjă minimă.

Oferte: fix instant, estimare verificată, dată garantată, fereastră flexibilă, enclosed premium, B2B rate și bid. Price floor, route check și compatibility check protejează calculul.

---

## 13. Change Order

Change Order modifică oficial o comandă plătită.

Motive: automobilul nu pornește, chei lipsă, roți blocate, dimensiuni greșite, mașină coborâtă, scurgere, adresă schimbată, așteptare, echipament suplimentar, open→enclosed, dată nouă, automobil suplimentar sau taxe externe.

Flux:

1. Motiv standard și dovezi.
2. Recalculare preț, payout și ETA.
3. Review operator pentru schimbări mari.
4. Comparație `înainte/după` pentru client.
5. Acceptare/refuz.
6. Plată sau refund.
7. Work Order nou.
8. Instrucțiuni actualizate.

Istoricul original nu poate fi suprascris.

---

## 14. Vehicle Tracking Timeline

### 14.1. Etape

```text
Quote Created → Payment Confirmed → Vehicle Ready
→ Matching → Carrier/Driver Assigned → Pickup Confirmed
→ Driver En Route → Arrived → Identity/VIN Verified
→ Pickup Inspection Signed → Loaded → Load Secured
→ Proof of Collection → In Transit
→ Delivery Arrival → Unloaded → Delivery Inspection
→ Keys/Documents Transferred → Proof of Delivery
→ Completed → Payout Released → Closed
```

Evenimente alternative: Change Order, reprogramare, reatribuire, așteptare, failed pickup/delivery, GPS lost, incident, SOS, storage, return, claim, refund și payout hold.

### 14.2. Date și acces

Fiecare eveniment are ID, VIN, timp server/dispozitiv, GPS/acuratețe, actor, motiv, dovezi, status anterior/nou, sursă, vizibilitate, indicator offline și audit metadata.

Clientul vede formulări clare, ETA, hartă și documente. Operatorul vede istoricul tehnic complet. Datele interne, marja și coordonatele personale ale șoferului sunt protejate.

### 14.3. Link de tracking

- token criptografic și expirare;
- revocare și OTP;
- drepturi expeditor/destinatar;
- no-index și rate limiting;
- jurnal de acces;
- ascunderea GPS după livrare;
- branding CODOOR/White Label.

Timeline este append-only; o corectare produce un eveniment compensator.

---

## 15. Chat și notificări

Conversații: client–support, client–driver, driver–dispatcher, company–CODOOR, incident room și internal notes.

Funcții:

- realtime WebSocket/SignalR;
- text, foto, video, document, voce și locație;
- răspunsuri rapide și traducere;
- sent/delivered/read;
- push, e-mail, SMS/WhatsApp fallback;
- căutare și citare;
- card comandă;
- protecția datelor;
- audit și escaladare.

Notificări importante: plată, atribuire, fereastră, plecare, sosire, preluare, ETA, Change Order, incident, livrare, documente, claim și payout.

---

## 16. Control Tower și urgențe

### 16.1. Control Tower

- hartă live;
- comenzi neatribuite;
- întârzieri și risc SLA;
- GPS pierdut sau rută deviată;
- așteptare excesivă;
- sloturi libere pe transportoare;
- Change Orders și inspecții incomplete;
- lipsa OTP/semnăturii;
- incidente, claims și SOS;
- documente expirate;
- plăți/payout-uri eșuate;
- acțiuni de reatribuire, rescue, hold și escaladare.

### 16.2. SOS

Categorii: accident, defecțiune, incendiu/EV, scurgere, daună, furt, amenințare, urgență medicală, fixare compromisă sau imposibilitatea continuării.

SOS transmite locația, transporterul, comanda și VIN-urile. Se deschide incident room, se afișează instrucțiuni, se colectează dovezi și se organizează recovery, storage sau replacement carrier. CODOOR nu înlocuiește serviciile publice de urgență.

---

## 17. Retur, custodie, daune și claims

Returul se folosește pentru destinatar absent, refuz, locație închisă, document lipsă, anulare după pickup, relivrare, storage sau transfer după defecțiune.

Soluții: retry, retur la origine, altă locație autorizată, parc securizat sau alt transportator. Fiecare necesită preț, ETA, acord și handover.

Chain of Custody păstrează VIN, părți, timp, GPS, kilometraj, fuel/charge, chei, documente, stare, poziție, fotografii, semnături și motiv.

Claim flow:

`Reported → Evidence Required → Review → Partner Response → Expert Assessment → Decision → Offer → Accepted/Appealed → Paid/Rejected → Closed`.

Decizia finală aparține unei persoane autorizate/asigurătorului. Condițiile juridice și de asigurare trebuie validate în fiecare țară.

---

## 18. Plăți și decontări

1. Clientul vede prețul detaliat.
2. Furnizorul licențiat procesează plata.
3. CODOOR nu stochează datele cardului.
4. Change Order are acord și tranzacție separată.
5. După POD începe hold-ul configurat.
6. Payout-ul devine disponibil.
7. Se deduc comisionul și ajustările explicate.
8. Se generează statement/invoice.
9. Se efectuează payout-ul.

Sunt necesare card, wallet, transfer B2B, deposit, capture, refund, chargeback, VAT, failed payout și reconciliere.

---

## 19. Contracte electronice

Documente: Customer Terms, Privacy/Cookie Policy, Transport Partner Agreement, Driver Terms, DPA, SLA, Work Order, Vehicle Condition Report, Proof of Collection, Proof of Delivery, Handover Report, Incident Report, Settlement Statement și Claims Decision.

Semnarea păstrează versiunea, limba, identitatea, autoritatea semnatarului, timpul, IP/dispozitivul, metoda de confirmare, hash-ul și audit trail-ul.


---

## 20. Compliance, rating și servicii partener

Verificări: identitate, companie, taxe, permis, licență, asigurare comercială, goods-in-transit/motor trade, public liability, transporter, inspecție tehnică, bancă, sancțiuni și training.

Documentele au emitent, număr, dată, expirare, status și reviewer. Expirările critice blochează activitatea.

Măsuri: `Coaching → Warning → Restriction → Suspension → Compliance Review → Termination`, cu motiv și apel.

Servicii opționale: asigurare prin partener, fuel/charging cards, toll/ferry, roadside assistance, leasing transporter, service, telematică, echipament, secure storage, training, EV safety, contabilitate, KYC și payout rapid.

---

## 21. White Label și abonamente

White Label oferă dealerilor/flotelor domeniu, branding, formular, portal, tracking, tarife, utilizatori, aprobări, notificări, DMS/ERP/API, rapoarte, SLA și izolare tenant.

Niveluri:

| Nivel | Funcții |
|---|---|
| Verified | Marketplace și payout standard |
| Pro | Rute salvate, analytics și payout rapid |
| Fleet | Flotă, șoferi, dispecerat și Load Planner |
| Enterprise | SLA, API, White Label și suport dedicat |

Abonamentul este separat de Trust Score. Plata nu cumpără rating și nu elimină verificările.

---

## 22. Configurare No-Code și Rules Engine

Configurabile fără deploy:

- țări, regiuni, porturi și parcuri;
- categorii auto și transportoare;
- prețuri, comisioane și payout rules;
- așteptare, anulare și no-show;
- documente și limite de asigurare;
- Change Order, Incident și SOS;
- vehicule/conținut interzis;
- contracte și notificări;
- SLA, abonamente și feature flags;
- retention.

Schimbările au draft, preview, aprobare în patru ochi, valabilitate, versiune, audit, rollback și test.

Exemple de reguli:

```text
DACĂ running = false → troliu obligatoriu + taxă non-running
DACĂ valoarea > limită → enclosed + aprobare asigurare
DACĂ EV battery damage = suspected → blocare + Safety Review
DACĂ pickup = auction → release reference + program obligatoriu
```

Orice decizie automată oferă o explicație.

---

## 23. AI și Anti-Fraud

### 23.1. AI

- verificarea unghiurilor și calității fotografiilor;
- detectarea posibilelor daune;
- comparație pickup/delivery;
- OCR VIN/plate cu confirmare umană;
- recomandări pentru Damage Map;
- matching automobil–transporter;
- backload și optimizare multi-car;
- ETA și risc de întârziere;
- rezumat timeline/chat;
- rescue plan;
- clasificare incident și documente lipsă.

AI nu decide definitiv răspunderea, claim-ul, despăgubirea sau blocarea unei persoane. Există human review și apel.

### 23.2. Anti-Fraud

- card sau identitate suspectă;
- VIN/document fals;
- automobil în căutare baze;
- valoare declarată anormală;
- chargebacks;
- GPS spoofing;
- traseu imposibil;
- fotografii reutilizate/editate;
- semnătură/OTP falsificat;
- finalizare fără geozonă;
- șofer/transporter substituit;
- conturi și reviews fictive;
- claim rate anormal.

Se verifică perceptual hash, EXIF, timestamp server, GPS media, VIN/plate, kilometraj și persoana autorizată. Flux: `Detected → Scored → Verification/Review/Hold → Cleared/Restricted/Reported`.

---

## 24. Arhitectură 

```text
Customer Web/App     Dealer Portal     Partner Portal
          \               |               /
                   Driver App
                       |
                 CODOOR API
                       |
     Database — Object Storage — Event Bus — Cache
                       |
 Maps — Payments — KYC — e-Sign — Messaging — Vehicle Data
```

Servicii logice: Identity, Customer, Organisation, Partner, Driver, Vehicle, Orders, Pricing, Marketplace, Routing, Tracking, Inspection, Load Planning, Communication, Payments, Documents, Claims, Compliance, Notifications, Risk, Reporting și Configuration.

Tehnologii:

- React/Next.js pentru web;
- React Native sau Flutter pentru mobil;
- ASP.NET Core pentru backend;
- PostgreSQL și Redis;
- S3-compatible storage;
- SignalR/WebSocket;
- cloud queue/event bus;
- furnizor de hărți și rutare comercială;
- marketplace payment provider;
- containere, cloud, logs, metrics și tracing.

MVP-ul poate porni ca modular monolith bine separat. Microserviciile se extrag când volumul o justifică.

---

## 25. Statusuri

### Comandă

`Draft → Quoted → Awaiting Payment → Booked → Matching → Assigned → Confirmed → In Progress → Completed → Settled`.

Alternative: `Change Requested`, `On Hold`, `Cancelled`, `Failed`, `Disputed`, `Refunded`.

### Preluare

`Pending → Driver En Route → Arrived → Identity Verified → Inspection → Loading → Collected → Issue`.

### Livrare

`Pending → In Transit → Driver En Route → Arrived → Unloading → Inspection → Delivered → Failed → Returned`.

### Partener

`Draft → Verification → Information Required → Approved → Active → Restricted → Suspended → Terminated`.

### Payout

`Estimated → Pending → On Hold → Available → Processing → Paid → Failed → Reversed`.

Fiecare tranziție păstrează autorul, timpul, motivul, statusul anterior și dovezile.

---

## 26. Securitate

- HTTPS și criptare;
- MFA și RBAC;
- izolare tenant;
- secret manager;
- tokenizarea plăților;
- audit append-only;
- scanarea fișierelor;
- WAF, rate limiting și DDoS protection;
- backup și disaster recovery;
- logs, metrics, tracing și alerte;
- managementul vulnerabilităților;
- audit GPS/documente;
- retention, export și ștergere;
- legal hold;
- minimizarea datelor;
- testare unit, integration, security și end-to-end.

---

## 27. MVP și etape

### Faza 1 — MVP

1. Portal client și rezervare pentru un automobil.
2. Chestionar running/non-running.
3. Preț și plată.
4. Companie, șofer și transporter.
5. Verificarea documentelor.
6. Marketplace fix și atribuire manuală.
7. Driver App offline.
8. VIN, GPS, ETA și Timeline.
9. Inspection, Damage Map, POC și POD.
10. Chat și notificări.
11. Change Order.
12. Control Tower.
13. Comision și payout.
14. Contracte și configurare de bază.

### Faza 2

- Dealer Portal și import în masă;
- Load Planner multi-car;
- matching automat;
- claims și e-sign avansat;
- licitații și parcuri;
- abonamente;
- AI Inspection și anti-fraud.

### Faza 3

- White Label și enterprise API;
- telematică;
- optimizare multi-car avansată;
- dynamic demand pricing;
- BI, predicție și servicii pentru parteneri.

---

## 28. Indicatori de succes

- conversie ofertă–rezervare;
- timp până la atribuire;
- rată de matching automat;
- punctualitate pickup/delivery;
- kilometri fără încărcătură;
- utilizarea sloturilor;
- marjă per comandă;
- cancellation/no-show;
- incident/damage/claim rate;
- inspecții complete;
- disponibilitate GPS;
- timp de răspuns suport;
- CSAT/NPS;
- rating și retenție partener;
- venit șofer pe oră/kilometru;
- payout failure rate;
- timp de soluționare claim.

---

## 29. Cerințe juridice înainte de lansare


- Termeni si Conditiile bine scrise legal


---

## 30. Concluzie


```text
Marketplace auto
+ Customer Portal
+ Dealer Portal
+ Partner Portal
+ Driver App
+ Vehicle Inspection
+ Load Planning
+ GPS Tracking
+ Control Tower
+ Payments & Payouts
+ Compliance & Claims
+ AI & Anti-Fraud
```

Platforma oferă clientului transparență, transportatorului acces la comenzi și instrumente profesionale, iar echipei CODOOR control asupra calității, operațiunilor, plăților și riscurilor.

Pașii următori recomandați:

1. aprobarea scope-ului MVP;
2. definirea țărilor de lansare;
3. user journeys și wireframes;
4. backlog cu user stories;
5. arhitectură tehnică;
6. estimare per modul;
7. calendar de implementare;
8. validarea modelului comercial și juridic.

---

**CODOOR **
