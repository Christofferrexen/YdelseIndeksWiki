# Generel vejledning til anvisninger
for Indeksene
**KOMBIT**

Dette dokument indeholder generel, tværgående vejledning til anvisningerne for anvendersystemernes anvendelse af Sags- og Dokumentindeks og Ydelsesindeks.

**Kim Rosendal Orbe**  
11. november 2019  
Version: 1.2  

---

**KOMBIT A/S**  
Halfdansgade 8  
2300 København S  
Tlf 3334 9400  
[www.kombit.dk](http://www.kombit.dk)  
kombit@kombit.dk  
CVR 19 43 50 75  

Side 2/19  

---

## Indhold
1. [Dokumenthistorik og kontaktinformation](#dokumenthistorik-og-kontaktinformation)  
   1.1 [Dokumenthistorik](#dokumenthistorik)  
   1.2 [Kontaktinformation](#kontaktinformation)  
2. [Hvilke dokumenter er omfattet af denne vejledning?](#hvilke-dokumenter-er-omfattet-af-denne-vejledning)  
3. [Formål med vejledningen (dette dokument)](#formål-med-vejledningen-dette-dokument)  
4. [Formål og baggrund for anvisningerne](#formål-og-baggrund-for-anvisningerne)  
5. [Opbygningen af anvisningerne](#opbygningen-af-anvisningerne)  
   5.1 [Anvisningerne følger XSD’erne](#anvisningerne-følger-xsd’erne)  
   5.2 [Tabelforklaringer](#tabelforklaringer)  
   5.3 [Navigation](#navigation)  
6. [Anvendelse af klassifikationer i Indeksene](#anvendelse-af-klassifikationer-i-indeksene)  
   6.1 [Typer af klassifikationer](#typer-af-klassifikationer)  
7. [Import og registrering](#import-og-registrering)  
8. [Håndhævelse af anvisningerne](#håndhævelse-af-anvisningerne)  
   8.1 [Obligatoriske felter](#obligatoriske-felter)  
9. [Angivelse af en relation](#angivelse-af-en-relation)  
   9.1 [ReferenceID](#referenceid)  
   9.2 [Udvidelsesfelter](#udvidelsesfelter)  
   9.3 [Relationsrolle](#relationsrolle)  
10. [Lokaludvidelsesfelter](#lokaludvidelsesfelter)  
11. [Fra- og tiltidspunkter](#fra-og-tiltidspunkter)  
12. [Dataafgrænsning](#dataafgrænsning)  
   12.1 [Sag](#sag)  
   12.2 [Dokument](#dokument)  
   12.3 [Bevilling](#bevilling)  
   12.4 [Økonomisk effektuering](#økonomisk-effektuering)  
13. [Versionsstyring af anvisningerne](#versionsstyring-af-anvisningerne)  

---

## 1. Dokumenthistorik og kontaktinformation
### 1.1 Dokumenthistorik
| Dato       | Version | Ændret af           | Beskrivelse |
|------------|---------|---------------------|-------------|
| 22.02.2016 | Vers. 1.0 | Søren Philipsen    | Første version klar til brug. |
| 10.06.2016 | Vers. 1.1 | Klaus Rasmussen    | Rettelser i forhold til forretningsregler i STS indekserne. Version til offentliggørelse. |
| 23.07.2016 | Vers 1.1 | Christian Wennemose | Tilføjse af afsnit 1.2 kontaktinformation. |
| 11.11.2019 | Vers 1.2 | Kim Rosendal Orbe | Præciseret at ReferenceID er obligatorisk for alle relationer. Anvisningsdokumentet ’Anvendelse af Klassifikation i indeksene’ er udfaset, og afsnit 6 i dette dokument vedrørende Klassifikation, er udvidet med introduktion til Klassifikation. Præciseret princip for versionering af anvisninger i afsnit 13. |

### 1.2 Kontaktinformation
Spørgsmål angående klassifikationer skal rettes til Støttesystemerne [KDI@kombit.dk](mailto:KDI@kombit.dk) med ”Anvisninger til Indekserne” i emnefeltet.

---

## 2. Hvilke dokumenter er omfattet af denne vejledning?
Nærværende dokument indeholder tværgående vejledninger, samt beskrivelse af formål og baggrund, for anvisningerne udarbejdet for Sags- og Dokumentindekset og Ydelsesindekset.  
Anvisningerne for Sags- og Dokumentindekset og Ydelsesindekset består samlet set af følgende dokumenter:
- **Vejledning til anvisninger for Sags- og Dokumentindekset og Ydelsesindekset** (dette dokument)
- **Anvendelse af Sagsobjektet i Sags- og Dokumentindeks**
- **Anvendelse af Dokumentobjektet i Sags- og Dokumentindeks**
- **Anvendelse af Bevillingsobjektet i Ydelsesindekset**
- **Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset**

---

## 3. Formål med vejledningen (dette dokument)
Denne vejledning fungerer som tværgående ramme og læsevejledning for anvisningerne til Sags- og Dokumentindekset og Ydelsesindekset, der indgår i de fælleskommunale støttesystemer. Vejledningen er udarbejdet med det formål at binde anvisningerne sammen og indeholder fælles retningslinjer og vejledning til læsning og forståelse af anvisningerne, som ellers skulle være gentaget for hver anvisning. Vejledningen bør derfor læses, inden man går i gang med at følge de specifikke anvisninger for informationsobjekterne i Indeksene.

---

## 4. Formål og baggrund for anvisningerne
Anvisningerne for Sags- og Dokumentindekset og Ydelsesindekset er udarbejdet med det formål helt konkret at skulle hjælpe udviklerne af integrationerne mod Indeksene, altså it-leverandørerne, og kommunernes involverede medarbejdere, herunder fx projektledere, digitaliseringskonsulenter eller it-arkitekter. Det er vigtigt, at alle dem, der har ansvaret for at etablere integration til indeksene fra anvendersystemerne, har en fælles og ensartet forståelse af data.

Anvisningerne har derfor til hensigt at fungere som en vejledning i, hvorledes de enkelte dataelementer, som skal udveksles med Indeksene, skal forstås og fyldes ud. Der er ikke tale om en teknisk gennemgang af, hvordan kommunikationen med Indeksene sættes op, men derimod en forretningsmæssig gennemgang, der er foretaget ud fra et informationsperspektiv. Dette til trods, er det i anvisningerne nødvendigt at referere til de XML Schema Definitioner (XSD), der foreligger for snitfladen mod Indeksene, så der sikres en forståelsesmæssig sammenhæng til den praktiske udmøntning.

---

## 5. Opbygningen af anvisningerne
Dette afsnit forklarer opbygningen af anvisningerne og giver vejledning i, hvorledes anvisningerne læses, og hvordan der kan navigeres rundt i dem.

Anvisningerne indeholder, ud over de tværgående vejledninger i dette dokument, en gennemgang af alle dataelementerne i de XML Schema definitioner, som definerer indholdet og strukturen af de data, som udveksles. Endvidere indeholder anvisningerne et særskilt dokument med anvisninger i anvendelse af fælles klassifikationer.

---

### 5.1 Anvisningerne følger XSD’erne
Anvisningerne for anvendelse af Indeksene er struktureret efter de snitfladedefinitioner i form af XML Schema Definitioner (XSD), der er udarbejdet for snitfladen mod Indeksene. XSD’erne er udarbejdet med udgangspunkt i de informationsmodeller, der forefindes for Sags- og Dokumentindeks og for Ydelsesindeks.
---

### 5.2 Tabelforklaringer
For at sikre en ensartet opbygning af dokumentationen for de enkelte informationsobjekter, er anvisningerne for hvert informationsobjekt beskrevet ud fra følgende elementer og med de forklaringer, der fremgår af tabellen herunder:

| Element              | Forklaring |
|----------------------|------------|
| **Felt**             | Navnet på feltet som fremgår af XSD-definitionen. |
| **Type**             | Datatypen for feltet. |
| **Format**           | Beskrivelse af formatet for feltets indhold. |
| **Obligatorisk**     | Angivelse af, om feltet er obligatorisk eller valgfrit. |
| **Forretningsregel** | Beskrivelse af de regler, der gælder for feltets anvendelse og indhold. |
| **Bemærkning**       | Yderligere bemærkninger og eventuelle eksempler på brugen af feltet. |

---

### 5.3 Navigation
For at lette navigationen i anvisningsdokumenterne anbefales det at anvende indholdsfortegnelsen i dokumentet, da denne er opbygget, så det er muligt at klikke sig direkte frem til det ønskede afsnit. Endvidere indeholder hver anvisning en række overskrifter, som beskriver de enkelte informationsobjekter og deres relationer.

---

## 6. Anvendelse af klassifikationer i Indeksene
Anvisningerne for anvendelse af Indeksene indeholder retningslinjer for anvendelse af klassifikationer. Klassifikationerne er systematiske inddelinger af objekter, processer og relationer i en form, der gør dem genkendelige og strukturerede. 

### 6.1 Typer af klassifikationer
Der anvendes flere typer klassifikationer i Indeksene, som for eksempel klassifikationer af sags- og dokumenttyper samt økonomiske ydelser. For en nærmere beskrivelse af de enkelte klassifikationer henvises til den specifikke anvisning.

---

## 7. Import og registrering
Dette afsnit omhandler anvisninger for import og registrering af data i Indeksene. Det er vigtigt, at anvendersystemer, der indlæser data i Indeksene, følger de anviste procedurer nøje for at sikre, at dataene bliver korrekt registreret og tilgængelige for andre systemer.

---

## 8. Håndhævelse af anvisningerne
Det er nødvendigt at sikre, at alle anvendersystemer overholder de obligatoriske anvisninger for dataindtastning og udveksling med Indeksene.

### 8.1 Obligatoriske felter
En række felter i Indeksene er markeret som obligatoriske. Disse felter skal udfyldes af anvendersystemerne for at sikre korrekt dataudveksling.

---

## 9. Angivelse af en relation
Anvisningerne giver vejledning i, hvordan relationer mellem forskellige informationsobjekter skal angives i Indeksene. Dette er nødvendigt for at sikre en korrekt sammenhæng mellem dataene.

### 9.1 ReferenceID
ReferenceID er et unikt id, som anvendes til at identificere en specifik relation mellem objekter. Det er obligatorisk at angive ReferenceID for alle relationer i Indeksene.

### 9.2 Udvidelsesfelter
Udvidelsesfelter kan anvendes til at tilføje yderligere oplysninger til en relation. Disse felter er ikke obligatoriske, men kan anvendes efter behov.

### 9.3 Relationsrolle
Relationsrollen beskriver den specifikke rolle, som en relation har i forhold til de involverede objekter. Det er vigtigt at angive den korrekte rolle for at sikre en meningsfuld anvendelse af relationerne.

---

## 10. Lokaludvidelsesfelter
Lokaludvidelsesfelter er særlige felter, der kan anvendes til at tilføje lokale informationer i Indeksene. Disse felter kan anvendes af kommuner eller anvendersystemer, der har særlige behov for at opbevare data, som ikke er dækket af de standardiserede felter.

---

## 11. Fra- og tiltidspunkter
For at sikre at data i Indeksene kan anvendes tidsmæssigt korrekt, skal alle relevante objekter angive fra- og tiltidspunkter. Dette gør det muligt at registrere, hvornår en bestemt oplysning er gyldig.

---

## 12. Dataafgrænsning
Dette afsnit omhandler de særlige retningslinjer for dataafgrænsning i de forskellige informationsobjekter i Indeksene. Dataafgrænsning er vigtig for at sikre, at kun relevante og aktuelle data indlæses og opbevares i Indeksene.

### 12.1 Sag
For sager er det nødvendigt at definere præcist, hvilke oplysninger der er relevante for registreringen i Sags- og Dokumentindekset. Derudover skal der tages højde for, hvordan sager relaterer til andre informationsobjekter i Indeksene.

### 12.2 Dokument
For dokumenter gælder der lignende retningslinjer som for sager, men med særligt fokus på dokumentets indhold, type og tilknytning til sager.

### 12.3 Bevilling
Bevillinger i Ydelsesindekset skal registreres på en sådan måde, at det er klart, hvilken økonomisk relation bevillingen har til de øvrige objekter i Indeksene.

### 12.4 Økonomisk effektuering
Økonomisk effektuering omfatter de faktiske økonomiske handlinger, der gennemføres i forbindelse med bevillinger. Her er det vigtigt at sikre, at disse data er præcise og tilknyttet de relevante bevillinger.

---

## 13. Versionsstyring af anvisningerne
Versionsstyring er afgørende for at sikre, at alle anvendersystemer anvender de nyeste og mest korrekte versioner af anvisningerne. Det er vigtigt, at alle opdateringer til anvisningerne kommunikeres tydeligt til alle relevante parter.

---

**Afslutning**  
Dette dokument udgør en generel vejledning til anvendelse af anvisningerne for Sags- og Dokumentindekset samt Ydelsesindekset. For yderligere detaljer henvises til de specifikke anvisningsdokumenter.

--- 

# Generel vejledning til anvisninger for Indeksene

**KOMBIT**
Dette dokument indeholder generel, tværgående vejledning til anvisningerne for anvendersystemernes anvendelse af Sags- og Dokumentindeks og Ydelsesindeks.

**Christoffer Rexen**  
**2024. November 08.**  
**Version: 0.1**

Version: 1.2
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 2/19
Indhold
1. Dokumenthistorik og kontaktinformaton.................................................................3
1.1 Dokumenthistorik .........................................................................................3
1.2 Kontaktinformation .......................................................................................3
1. Hvilke dokumenter er omfattet af denne vejledning?.............................................4
2. Formål med vejledningen (dette dokument) ..........................................................4
3. Formål og baggrund for anvisningerne ..................................................................4
4. Opbygningen af anvisningerne ..............................................................................5
5.1 Anvisningerne følger XSD’erne....................................................................5
5.2 Tabelforklaringer ..........................................................................................6
5.3 Navigation ....................................................................................................8
1. Anvendelse af klassifikationer i Indeksene ..........................................................10
6.1 Typer af klassifikationer .............................................................................11
1. Import og registrering ...........................................................................................12
2. Håndhævelse af anvisningerne............................................................................13
8.1 Obligatoriske felter .....................................................................................13
1. Angivelse af en relation........................................................................................14
9.1 ReferenceID...............................................................................................15
9.2 Uvidelsesfelter............................................................................................15
9.3 Relationsrolle .............................................................................................16
1.  Lokaludvidelsesfelter............................................................................................16
2.  Fra- og tiltidspunkter.............................................................................................16
3.  Dataafgrænsning..................................................................................................17
12.1 Sag.............................................................................................................17
12.2 Dokument...................................................................................................17
12.3 Bevilling......................................................................................................18
12.4 Økonomisk effektuering .............................................................................18
1.  Versionsstyring af anvisningerne .........................................................................19
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 3/19
1. Dokumenthistorik og kontaktinformaton
1.1 Dokumenthistorik
Dato Version Ændret af Beskrivelse
22.02.2016 Vers. 1.0 Søren Philipsen Første version kar til brug.
10.06.2016 Vers. 1.1 Klaus Rasmussen Rettelser i forhold til forretningsregler i STS indekserne.
Version til offentliggørelse.
23.07.2016 Vers 1.1 Christian Wennemose
Tilføjse af afsnit 1.2 kontakinformation.
11.11.2019 Vers 1.2 Kim Rosendal Orbe Præciseret at ReferenceID er obligatorisk for alle relationer.
Anvisningsdokumentet ’Anvendelse af Klassifikation i indeksene’ 
er udfaset, og afsnit 6 i dette dokument vedrørende Klassifikation, er udvidet med introduktion til Klassifikation.
Præciseret princip for versionering af anvisninger i afsnit 13.
1.2 Kontaktinformation
Spørgsmål angående klassifikationer skal rettes til Støttesystemerne KDI@kombit.dk
med ”Anvisninger til Indekserne” i emnefeltet.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 4/19
1. Hvilke dokumenter er omfattet af denne vejledning?
Nærværende dokument indeholder tværgående vejledninger, samt beskrivelse af formål og baggrund, for anvisningerne udarbejdet for Sags- og Dokumentindekset og 
Ydelsesindekset.
Anvisningerne for Sags- og Dokumentindekset og Ydelsesindekset består samlet set af 
nedestående dokumenter:
− Vejledning til anvisninger for Sags- og Dokumentindekset og Ydelsesindekset 
(dette dokument)
− Anvendelse af Sagsobjektet i Sags- og Dokumentindeks
− Anvendelse af Dokumentobjektet i Sags- og Dokumentindeks
− Anvendelse af Bevillingsobjektet i Ydelsesindekset
− Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
1. Formål med vejledningen (dette dokument)
Denne vejledning fungerer som tværgående ramme og læsevejledning for anvisningerne til Sags- og Dokumentindekset og Ydelsesindekset, der indgår i de fælleskommunale støttesystemer.
Vejledningen er udarbejdet med det formål at binde anvisningerne sammen og indeholder fælles retningslinjer og vejledning til læsning og forståelse af anvisningerne, som 
ellers skulle være gentaget for hver anvisning. Vejledningen bør derfor læses, inden 
man går i gang med at følge de specifikke anvisninger for informationsobjekterne i Indeksene.
1. Formål og baggrund for anvisningerne
Anvisningerne for Sags- og Dokumentindekset og Ydelsesindekset er udarbejdet med 
det formål helt konkret at skulle hjælpe udviklerne af integrationerne mod Indeksene, 
altså it-leverandørerne, og kommunernes involverede medarbejdere, herunder fx projektledere, digitaliseringskonsulenter eller it-arkitekter. Det er vigtigt, at alle dem, der 
har ansvaret for at etablere integration til indeksene fra anvendersystemerne, har en 
fælles og ensartet forståelse af data.
Anvisningerne har derfor til hensigt at fungere som en vejledning i, hvorledes de enkelte dataelementer, som skal udveksles med Indeksene, skal forstås og fyldes ud. Der 
er ikke tale om en teknisk gennemgang af, hvordan kommunikationen med Indeksene 
sættes op, men derimod en forretningsmæssig gennemgang, der er foretaget ud fra et 
informationsperspektiv. Dette til trods, er det i anvisningerne nødvendigt at referere til 
de XML Schema Definitioner (XSD), der foreligger for snitfladen mod Indeksene, så der 
sikres en forståelsesmæssig sammenhæng til den praktiske udmøntning. På den måde 
kan man nemt genfinde det dataelement (fx ’Dokumenttype’), man læser om i anvisningen, i den XSD, udviklerne arbejder med og skal bruge i praksis.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 5/19
Anvisningerne skal læses i sammenhæng med de generelle integrationsvilkår for de 
fælleskommunale støttesystemer. Idet integrationsvilkårene på mange områder er generiske og dermed åbner op for risikoen for forskellig fortolkning af, hvorledes data lægges i indeksene, er der behov for en forretningsmæssig præcisering af integrationsvilkårene.
I dag forefindes allerede beskrivelser af de logiske informationsmodeller, Indeksene er 
baseret på. Hvor informationsmodellerne er en logisk beskrivelse af indholdet af indeksene, er anvisningerne beskrevet ud fra en anvendelsesorienteret tilgang, så det er tydeligt, hvad der helt konkret skal udveksles.
1. Opbygningen af anvisningerne
Dette afsnit forklarer opbygningen af anvisningerne og giver vejledning i, hvorledes anvisningerne læses, og hvordan der kan navigeres rundt i dem.
Anvisningerne indeholder, ud over de tværgående vejledninger i dette dokument, en 
gennemgang af alle dataelementerne i de XML Schema definitioner, som definerer indholdet og strukturen af de data, som udveksles. Endvidere indeholder anvisningerne et 
særskilt dokument med anvisninger i anvendelse af fælles klassifikationer.
5.1 Anvisningerne følger XSD’erne
Anvisningerne for anvendelse af Indeksene er struktureret efter de snitfladedefinitioner i 
form af XML Schema Definitioner (XSD), der er udarbejdet for snitfladen mod Indeksene. XSD’erne er udarbejdet med udgangspunkt i de informationsmodeller, der forefindes for Sags- og Dokumentindeks og for Ydelsesindeks.
Denne tilgang, hvor anvisningerne er baseret på XSD’erne, er valgt af hensyn til at 
fremstille anvendelsesorienterede anvisninger, der er så konkrete at forholde sig til for 
anvisningernes målgruppe som muligt. Idet de udviklere, digitaliseringskonsulenter, 
mv., der beskæftiger sig med integrationen mod Indeksene, i praksis skal forholde sig til 
snitfladerne i højere grad end informationsmodellerne, er anvisningerne struktureret efter snitfladedefinitionerne, dvs. XSD’erne.
Anvisningerne indeholder derfor en grundig gennemgang af samtlige dataelementer, 
der indgår i XSD’erne. Denne tilgang har medført, at anvisningerne er blevet fhv. omfangsrige, idet mange dataelementer forekommer og beskrives flere gange. Omfanget 
opvejes dog af, at anvisningerne til gengæld er lettere at forholde sig til, da anvisningerne helt konkret kan holdes op imod XSD’erne én-til-én. Læseren slipper så for at 
skulle slå op i anvisningerne flere steder og samtidigt bør det eliminere enhver tvivl om, 
hvilke dataelementer og definitioner af samme, der gør sig gældende i en given sektion 
i XSD’en.
Det er derfor vigtigt at understrege, at selv om et givent dataelement bliver gentaget 
flere gange gennem anvisningen, kan der være forskel i beskrivelsen tilknyttet dataelementet. Et dataelement kan i nogle tilfælde blive anvendt forskelligt afhængigt af den 
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 6/19
kontekst, det indgår i. Et eksempel herpå er dataelementet ’ReferenceID’, der har forskellige anvisninger afhængigt af den relationsrolle, den er tilknyttet.
XSD’erne, anvisningerne forholder sig til, er til en vis udstrækning indlejret i hinanden 
(en XSD importerer andre XSD’er). Sammenhængen mellem de eksisterende XSD’er 
og anvisningerne er som vist nedenfor:
Som det fremgår af ovenstående illustration, kan de samme XSD’er være beskrevet i 
forskellige anvisninger. Dette giver dog god mening, idet anvisningerne til udfyldelsen 
af et givent dataelement kan variere på tværs af anvisningerne, selv om det stammer 
fra den samme XSD.
5.2 Tabelforklaringer
Anvisningerne består i bund og grund af en kronologisk gennemgang af dataelementerne i de XSD’er, der beskriver det centrale forretningsobjekt, fx Sag. XSD’erne er i anvisningerne skrevet ud på tabelform med en række for hvert dataelement.
Sag
Sag
Indeks
Dokument
Indeks
SagDok
Objekt
SagDok
Objekt
Bevilling
Indeks
SagDok
Objekt
OekonomiskEffek
tuering
Indeks
SagDok
Objekt
Generelle 
Definitioner
Generelle 
Definitioner
Generelle 
Definitioner
Generelle 
Definitioner
Beskrevet i
Beskrevet i
Beskrevet i
Beskrevet i
Anvendelse af 
Sagsobjektet i Sagsog Dokumentindeks
Anvendelse af 
Dokumentobjektet i
Sags- og Dokumentindeks
Anvendelse af 
Bevillingsobjektet i 
Ydelsesindeks
Anvendelse af 
Økonomisk 
Effektueringsobjektet
i Ydelsesindeks
XSD’er Anvisninger
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 7/19
Nedenfor er der indsat en kort beskrivelse af, hvordan indholdet af kolonnerne i gennemgangen af dataelementerne i anvisningerne skal læses.
XSD-struktur: Her angives stistrukturen (hierarkiet) i XML Schema Definitionen (XSD), således, at dataelementet kan lokaliseres i 
XSD’en.
Navn på dataelement Definition Regler for udfyldelse Datatype Eksempel
Her er navnet på dataelementet angivet. Det 
er identisk med navnet 
på dataelementet i 
XSD’en, såvel som i de 
fleste tilfælde med attributnavnet i informationsmodellen
Her er angivet en entydig 
definition af dataelementets
betydning.
I denne kolonne er de regler 
beskrevet, som gælder for dataelementet. Dette kan fx være 
en skærpelse af, hvad der må 
fyldes i dataelementet, afhængigheder til andre dataelementer eller om dataelementet 
er obligatorisk (og i hvilke tilfælde, det er det).
Mht. obligatoriske dataelementer henvises til de forskellige 
kategorier i afsnittet nedenfor.
Her angives datatypen, som definerer formatet 
for dataelementet. Datatypen er 
både angivet 
med almindeligt 
sprogbrug (fx 
tekst) og med 
den tekniske 
term (fx string).
Her er der indsat et 
eksempel på, hvordan 
dataelementet kan 
være udfyldt. 
De indsatte værdier, 
fx en UUID, er udelukkende eksempler, og 
henviser ikke til det 
korrekte objekt.
5.2.1 Gentagelse af relationer for hver rolle
I anvisningerne er der afsnit, hvor samme sekvens af dataelementer, tilhørende en relation, gentages flere gange, men med forskelligt indhold. Dette skyldes, at kravene til udfyldelse af dataelementerne for en relation kan variere, afhængigt af, hvilken rolle, der 
er tilknyttet relationen.
Et eksempel på ovenstående er for relationen Sagsaktør i forhold til Sagsobjektet. 
Sagsaktør kan bl.a. have rollen ’ejer’, ’ansvarlig’ eller ’primær sagsbehandler’, og her vil 
der være forskel på anvisningerne til udfyldelse af data, til trods for, at dataelementerne 
som udgangspunkt er ens. Fx må objekttypen for en ejer kun være en Organisation, 
hvor det for den ansvarlige sagsaktør kan være en Organisation eller en OrgEnhed, og 
hvor det for en primær sagsbehandler kan være en OrgEnhed eller en Bruger.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 8/19
5.3 Navigation
For at give overblik over anvisningerne og gøre det lettest muligt for læseren at navigere rundt i anvisningerne er der øverst i hver anvisning indsat en figur, der afspejler 
den XSD-struktur (XSD inkl. importerede XSD’er), som anvisningen forholder sig til.
Nedenfor er indsat et eksempel på en sådan figur fra anvisningen for ”Anvendelse af 
Sagsobjektet i Sags- og Dokumentindeks”. 
Farverne på de enkelte sektioner i figuren har en betydning, som også bidrager til at 
forbedre overblikket. Rækkerne i tabellerne i anvisningerne er farvelagt tilsvarende farverne i figuren. Farvekoderne er følgende:
− Lyseblå = Forretningsdata
Lyseblå markerer de forretningsbærende data, som indeholder oplysninger om fx 
sagen eller ydelsen.
− Lysegrå = Generelle egenskaber
Lysegrå markerer de generelle egenskaber, som er supplerende ”tekniske” data til 
forretningsdata. De generelle egenskaber er virkningsdata og registreringsdata.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 9/19
For hver sektion i anvisningen er en kollapset udgave af figuren gentaget med angivelse af, hvor i strukturen man befinder sig. Figurerne er klikbare, så man hurtigt kan 
navigere hen til den ønskede sektion.
Udover at gøre brug af de klikbare figurer i anvisningerne, er det også muligt at navigere rundt i anvisningerne via indholdsfortegnelsen øverst i dokumenterne eller vha. 
navigationsruden til venstre i MS Word eller PDF (bookmarks).
Nedenfor er vist et eksempel på brug af navigationsrude i MS Word. Navigationsruden 
aktiveres ved at vælge ’Navigationsrude’ under menupunktet ’Vis’.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 10/19
Her er indsat et eksempel på brugen af navigationsruden i PDF. Navigationsruden i 
Acrobat Reader aktiveres ved at vælge ’Bogmærker’ i menuen længst til venstre i billedet nedenfor.
1. Anvendelse af klassifikationer i Indeksene
Dette afsnit gennemgår de konkrete klassifikationer, som der er behov for i Indeksene. 
Afsnittet beskriver således de klassifikationer, der henvises til fra anvisningerne til 
Sags- og Dokumentindekset og iYdelsesindekset – nærmere betegnet fra:
− Anvendelse af Sagsobjektet i Sags- og Dokumentindeks
− Anvendelse af Dokumentobjektet i Sags- og Dokumentindeks
− Anvendelse af Bevillingsobjektet i Ydelsesindekset
− Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
I det føgende gives en præcisering af de forskellige typer af klassifikationer og en anvisning af deres anvendelse. 
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 11/19
6.1 Typer af klassifikationer
Klassifikationer anvendes i Støttesystemerne (STS) både i form af egentlige klassifikationssystemer som fx KLE eller Kontoplan, der kan anvendes til at give objekter en fælles forståelse i form af fælles nøgler. Klassifikationer anvendes også i form af værdilister, der angiver udfaldsrum på attributter. 
Angivelsen af en klassifikation i modellerne i STS kan følge typerne:
• STS Klassifikation har lagret klassifikationen, og der refereres til den via UUID 
fra pågældende model.
• Enumeration, hvor klassifikationens værdier er lagt ind i modellens XSD. 
Brugsscenarierne for klassifikationer er identificeret som:
• Objekttyper og relationsroller på en relation
- En relation til et fremmed objekt beskrives ved hjælp af klassifikationer 
lagret i STS Klassifikation for:
▪ Objekttyper – typen af objekt, som relationen går til.
▪ Relationsroller – rollen for den pågældende relation.
- Refereres via UUID på klasseobjekt
• Værdiliste på en attribut
- Opfattes per definition som en klassifikation.
- Kan enten: 
▪ Lagres som en klassifikation i STS Klassifikation og refereres 
til via UUID på klasseobjekt (referenceID)
▪ Udtrykkes som en enumeration i XSD’en
- Virkning følger attributliste
• Klasserelation – relation til klasseobjekt 
- Relation til en klasse i STS Klassifikation fra et objekts relationsliste. 
- Relationen har egen virkning
Tabellen nedenfor angiver de forskellige måder at arbejde med klassifikationer på. 
• Felterne markeret med X angiver, at det er en gyldig og forekommende måde 
at anvende klassifikationer på i STS. 
• n/a betyder, at det ikke er en gyldig eller forekommende måde at angive klassifikationer i STS. 
Brugsscenarier STS Klassifikation Enumeration
Objekttyper og relationsroller på en relation X n/a
Værdiliste på en attribut X X
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 12/19
6.1.1 Objekttyper og relationsroller på relationer
Ved relation til et eksternt objekt beskrives relationen ved hjælp af objekttype og relationsrolle, der begge skal være kendt i STS Klassifikation. 
Objekttyper og relationsroller for relationerne i Indeksene angives via UUID der er tilgængelige i STS-Klassifikation. 
6.1.2 Værdiliste på en attribut
De tilladte værdier på en attribut udtrykkes i en værdiliste, hvis der er behov for at indsnævre udfaldsrummet til en række foruddefinerede værdier.
Der er forskellige måder at udtrykke de foruddefinerede værdier:
1. De kan oprettes som Klassifikation i STS Klassifikation og udpeges fra objektets attributliste via UUID
o Fleksibel model, nemt at tilføje eller fjerne værdier
o Ingen validering i XSD
o God ved dynamiske værdilister
1. De kan håndhæves som en enumeration i XSD
o Validering i XSD
o Mindre fleksibel model, det kræver ny version af XSD for at tilføje eller 
fjerne værdier
o God ved stabile værdilister
En række af de klassifikationer, der foreslås her, er til attributter, der i dag i XSD’en er 
angivet som en ’string’. For at indsnævre udfaldsrummet af hensyn til visning i SAPA, 
angives i stedet klassifikationer, der skal oprettes i STS Klassifikation. 
Den gældende værdiliste for klassifikationer på attributer tilgås direkte i STS-Klassifikation.
1. Import og registrering
For at øge forståelsen af, hvornår Indeksene opdateres, er der nedenfor givet et konkret eksempel på registrering af sags- og ydelsesoplysninger, der bliver importeret ind i 
Indeksene. Der henvises desuden til dokumentet ”Generelle egenskaber for services 
på sags- og dokumentområdet”1
(side 20) for en beskrivelse af registrering.
En registrering er lig et antal ændringer på en sag foretaget af en enkelt bruger. Dvs. 
omdrejningspunktet for en registrering er den bruger, som har ændret en eller flere dataelementer på en sag i én arbejdsgang.
Fx Hanne Sørensen, som er sagsbehandler i ydelsescenteret og sidder med kontanthjælpssager, arbejder pt. i sit fagsystem KY med Erling Hansens kontanthjælpssag. 
1 https://digitaliser.dk/resource/1567464
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 13/19
Hanne tilføjer et dokument med helbredsoplysninger og skriver et journalnotat, samtidig 
tilføjer hun både Erlings kone Marianne og hans søn Bent som sekundære parter på 
sagen. Hanne slutter af med at ændre sagens tilstand til ’oplyst’, da der ikke mangler 
yderligere oplysninger for at afgøre sagen. Hanne gemmer sagen.
Da sagens tilstand er ændret til ’oplyst’, ved KYs forretningslogik, at den nu kan beregne størrelsen af ydelsen. KY beregner ydelsen og gemmer et journalnotat på sagen. 
Herefter afgør Hanne, om Erling er berettiget til kontanthjælp og gemmer ligeledes et 
journalnotat på sagen, samt ændrer sagens tilstand til ’afgjort’.
Ovenstående ændringer af sagen skal gemmes som tre separate registreringer; én for 
de ændringer, som Hanne først foretager, én for de ændringer som fagsystemet (KY) 
foretager, og en registrering for de ændringer Hanne slutter af med. Hannes registrering indeholder to sagspartrelationer af rollen ’Sekundær part’.
1. Håndhævelse af anvisningerne
Anvisningerne for anvendelse af Sags- og Dokumentindekset og Ydelsesindekset skal 
betragtes som en fælles konvention blandt anvenderne af Indeksene. Mange af kravene til udfyldelse af dataelementer og relationer, herunder fx hvilke dataelementer, der 
er obligatoriske, håndhæves ikke i Indeksene.
Med henblik på at have XSD’er, der kan genbruges til forskellige formål, fx til både at 
importere fra eller opdatere Indeksene, er der ikke mange dataelementer, der er angivet som obligatoriske i XSD’erne. Tilsvarende er det også begrænset, hvilke tekniske 
datavalideringer, der er indbygget i Indeksene.
Dette betyder, at man som anvendersystem ikke kan regne med at modtage en fejlmeddelelse i tilfælde af, at anvisningerne ikke overholdes.
8.1 Obligatoriske felter
Idet nogle dataelementer kan være obligatoriske i visse situationer, men ikke behøver 
at være udfyldte i andre, er der igennem anvisningerne ud for de obligatoriske dataelementer angivet, hvad der forstås herved. 
Der er defineret fem former for obligatoriske dataelementer:
1. [OB1] Et dataelement eller en relation kan være obligatorisk ved import af en ny 
sag i sagsindekset. Dvs. sagen kan ikke eksistere i sagsindekset uden dette dataelement/denne relation, og dermed må dataelementet/relationen heller ikke fjernes 
igen, uden at den erstattes af et lignende dataelement/en lignende relation. 
Et eksempel på et dataelement, som er obligatorisk ved import af en sag, er sagens titel. Sagen skal altid have en titel i sagsindekset, men man kan godt ændre 
titlen.
Et eksempel på en relation, som er obligatorisk ved import af en sag i sagsindekset, er relationen til en sagsaktør med rollen ’Ejer’. Man kan godt erstatte relatio-
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 14/19
nen til en Ejer med en relation til en anden Ejer, der skal bare altid være en sagsaktørrelation med rollen ’Ejer’.
1. [OB2] Et dataelement eller en relation kan være obligatorisk, hver gang man gemmer en registrering af sagen i sagsindekset, dvs. både ved import og ved opdatering af sagen. Disse dataelementer er grundlæggende med til at beskrive selve registreringen, så det er dataelementer som UUID for det objekt, som registreringen 
omhandler, eller fx registreringstidspunktet for de informationer, som registrering 
indeholder.
1. [OB3] Et dataelement kan være obligatorisk ved tilføjelse af en relation. Dvs. hvis 
du ønsker at tilføje en partsrelation af rollen ’sekundær part’, så skal du fx udfylde 
dataelementet ’Type’ og det skal du gøre for hver partsrelation af rollen ’sekundær 
part’, som du tilføjer til sagen.
1. [OB4] Et dataelement kan være obligatorisk, hvis et andet dataelement er udfyldt 
eller ikke udfyldt, eller udfyldes med en bestem værdi. Et eksempel på dette er dataelementet ’TitelAlternativTekst’ som kun er obligatorisk, hvis dataelementet ’OffentlighedUndtagetHjemmelTekst’ er udfyldt. I disse tilfælde betyder det samtidig, 
at dataelementet ’TitelAlternativTekst’ ikke må være udfyldt, hvis dataelementet 
’OffentlighedUndtagetHjemmelTekst’ ikke er udfyldt, og at hvis dataelementet ’OffentlighedUndtagetHjemmelTekst’ slettes, så skal dataelementet ’TitelAlternativTekst’ også slettes.
1. [OB5] Et dataelement, der er med til at angive virkningen for en eller flere dataelementer i en specifik sektion af XSD’en er obligatorisk, hvis en eller flere at de dataelementer, som virkningen gælder for, er udfyldt.
2. Angivelse af en relation
En relation til andre objekter (fx til en sagsaktør) kan beskrives på følgende måde:
Der angives en reference til det relaterede objekt, som gør det muligt for modtagersystemet at slå det relaterede objekt op i et andet IT-system/register, for dér at hente beskrivende data om det relaterede objekt. Det kunne fx være et UUID på en organisationsenhed i støttesystemet Organisation, hvor organisationsenhedens navn, adresse 
mv. hentes. Det kunne også være CPR-nummeret (angivet som URN) på en person, 
hvor data om personen (navn, adresse, alder mv.) hentes i CPR-registeret (se afsnit 
9.1 for mere om ReferenceID).
For det relaterede objekt kan der anives yderligere beskrivende data direkte i indekset 
via relationens ”udvidelsesfelter”
2
. Indekserne indeholder for hver relation et sæt basis 
udvidelsesfelter, som afsendersystemet kan anvende, men det er også muligt for anvendersystemet at tilføjes sine egne lokaludvidelsesfelter, hvis der er relevante beskrivende data om det relaterede objekt, som ikke er dækket af de eksisterende udvidelsesfelter. Sidstnævnte, altså lokaludvidelsesfelterne, er ikke beskrevet i anvisningerne, 
2 Se fx ”Begrebs- og informationsmodel for Ydelsesindeks version 2.0”, side 3, hvor udvidelser, defineret som 
associerede klasser, er beskrevet.
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 15/19
idet disse i første omgang ikke ikke vil blive anvendt, men kan komme på tale på længere sigt, når anvendelsen af indeksene udbredes (se afnit 9.2 for mere om udvidelsesfelterne og afsnit 10 for mere om lokaludvidelser).
9.1 ReferenceID
Et ’ReferenceID’ kan angives enten som et UUID eller som en URN. En URN er en 
særlig syntax til at angive en unik reference til et objekt. Syntaxen indeholder information om, hvem der er ansvarlig for det domæne, som objektet er en del af, hvilken objekttype, der er tale om, samt hvilken unik attribut for objektet, der refereres til. Et eksempel på en URN kunne være angivelse af en bruger i KMD Sag via brugeren 
RACFID (KMDs brugernøgle). En sådan URN vil se således ud: 
’urn:kmd:sag:RACFID:WXYZABC’.
Man må ikke angive ReferenceID til et objekt i de fælleskommunale støttesystemer 
som en URN. Hvis afsendersystemet har en integration til støttesystemet (fx STS Organisation), skal afsendersystemet angive et UUID på det relaterede objekt. Hvis afsendersystemet ikke har en integration til støttesystemet, så angives referencen som en 
URN. Det samme gælder for de fællesoffentlige grunddataregistre, dog er det ikke alle 
registre, der indeholder UUID'er på deres objekter. Fx findes der ikke et UUID på en 
person i CPR-registeret. Kun i de tilfælde, hvor registret ikke anvender UUID'er, må afsendersystemet angive det relaterede objekt med en URN.
I anvisningerne vil det for hver relation være beskrevet, om man må/skal bruge hhv. 
UUID eller URN i den givne situation – om begge typer af referencer er en mulighed, og 
hvorvidt udvidelsesfelterne (fx ’FuldtNavn’) må anvendes. Afsendersystemet skal bestræbe sig på at angive et UUID som referenceID for det relaterede objekt, så modtagersystemer har mulighed for at indhente yderligere oplysninger om objektet.
9.2 Uvidelsesfelter
Udvidelsesfelter er ekstra dataelementer, der er medtaget af hensyn til at gøre Indeksene operationelle, og er udvidelser til informationsmodellerne i OIO-standarden.
Hvis afsendersystemet ikke har mulighed for at angive et ReferenceID for en relation, 
må afsendersystemet angive en URN og eventuelt udfylde ”udvidelsesfelterne” (fx 
’FuldtNavn’).
ReferenceID er obligatorisk, men i nogle tilfælde kan det være relevant at angive både 
et ReferenceID og udfylde udvidelsesfelterne. Dette er relevant, hvis ReferenceID’et 
henviser til et system, som ikke alle modtagersystemer kan forventes at kunne slå det 
relaterede objekt op i. Det kunne fx være et objekt i et lokalt fagsystem (fx KMD Sag) 
eller et objekt i et leverandørspecifikt støttesystem (fx KMD LOS). Afsendersystemer 
kan i denne situation angive et ReferenceID, således at de modtagersystemer, som har 
adgang til at slå det relaterede objekt op og hente yderligere informationer, kan gøre 
det. Samtidig udfylder afsendersystemet udvidelsesfelterne således, at de modtagersystemer, som ikke kan bruge ReferenceID’et, kan anvende informationerne i udvidelsesfelterne. Hvis afsendersystemet i denne situation vælger både at udfylde referenceID 
og lokaludvidelsesfelterne, er der en risiko for, at de to sæt data ikke stemmer overens, 
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 16/19
så ReferenceID’et henviser til et objekt og lokaludvidelsesfelterne beskriver et andet 
objekt. Det er afsendersystemets ansvar at sikre, at dette ikke sker.
Hvis modtagersystemet opdager uoverensstemmelse mellem objektet, der refereres til i 
referenceID, og det objekt, der er beskrevet i udvidelsesfelterne, så er det objektet i ReferenceID, der gælder.
9.3 Relationsrolle
Det er obligatorisk at angive en rolle på hver relation, så det er tydeligt, hvilken rollen en 
given relation spiller i forhold til det objekt, der relateres til. Rollen oplyses altid som en 
UUID til en relationsrolle i STS Klassifikation.
Rollen på en relation kan ikke ændres, da den indgår som en del af relationens sammensatte ID (relationstype-relationsrolle-indeks). Denne sammensatte nøgle er nødvendig for altid at kunne identificere en relation, selv om der er flere relationer med 
samme rolle og evt. samme type. Hvis rollen skal ændres, svarer det til at afslutte den 
nuværende relation via TilTidspunkt på virkning og oprette en ny relation.
Nogle relationer forekommer kun én gang og altid med den samme rolle. I de tilfælde er 
rollen mindre vigtig og kunne i princippet undlades. I anvisningerne er det for konsistensens skyld, og i tilfælde af, at der tilføjes flere roller, dog valgt, at rollen altid skal være 
der.
1.  Lokaludvidelsesfelter
Ud over udvidelsesfelterne, beskrevet i afsnit 9.2, eksisterer der i XSD’erne også såkaldte ”lokaludvidelsesfelter”. Lokaludvidelsesfelterne er indsat forskellige steder i 
XSD’erne som sektioner med navnet ’LokalUdvidelseListe’.
Tanken med lokaludvidelsesfelterne er at muliggøre indsættelse af data i Indeksene, 
som ikke findes i informationsmodellerne i forvejen. Denne mulighed vil ikke blive benyttet i første omgang, og er derfor ikke nærmere beskrevet i anvisningerne. Det forventes, at brugen af lokaludvidelsesfelter kan blive aktuel, når skaren af anvendersystemer udbredes, og der evt. bliver behov for bilaterale aftaler vedr. specifikke data.
1.  Fra- og tiltidspunkter
Der forekommer gennem anvisninger et stort antal fra- og tiltidspunkter eller fra- og tildatoer. De findes både i virkningsdata (FraTidspunkt og TilTidspunkt), men også i de 
forretningsbærende data (fx bevillingsstartdato og bevillingsslutdato).
Tidspunkter og datoer er konsekvent gennem anvisningerne angivet som datatypen 
’dateTime’, der er et tidsstempel, som både indeholder dato og klokkeslæt helt ned på 
tusindedele. 
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 17/19
- Fradatoer og fratidspunkter er altid inklusive. Dvs., at tidsstemplet hører med til den 
periode, som fradatoen eller -tidspunktet angiver starten på. Fradatoer og fratidspunkter er generelt obligatoriske i anvisningerne.
- Tildatoer og tiltidspunkter er altid eksklusive. Dvs., at tidsstemplet ikke hører med til 
den periode, som tildatoen eller -tidspunktet angiver slutningen på. Når tildatoer/-
tidspunkter er eksklusive giver det den fordel, at samme tidsstempel kan være fradato/-tidspunkt for den efterfølgende periode, hvorved der så ikke skal regnes på, 
om der er huller i perioderne (fx virkningen). Tildatoer og tiltidspunkter er generelt 
ikke-obligatoriske i anvisningerne (dog med enkelte undtagelser, fx ’Slutdato’ på 
Egenskaber for økonomisk effektuering).
Tildatoer og tiltidspunkter kan udover at være et tidsstempel, der angiver et eksakt 
tidspunkt, i stedet angive, at perioden er løbende (uendelig). Sidstnævnte angives 
på to forskellige måder. Enten skal det angives som ’true’ (boolean), eller når boolean ikke er muligt, som et tomt (ikke udfyldt) felt.
1.  Dataafgrænsning
Nedenfor gives en kort introduktion til dataafgrænsningen i Støttesystemernes indekser 
ved fremsøgning af sags-, dokument- og ydelsesdata. 
Den grundlæggende dataafgrænsning i Støttesystemernes indekser foretages ud fra 
objektets knytning til CVR (kommunen/myndigheden), KLE-nummer og følsomhedsniveau. Derudover kan modtagersystemerne vælge at dataafgrænse på andre dataelementer (fx ansvarlig organisatorisk enhed), men dette behandles ikke yderligere i anvisningerne.
12.1 Sag
En sag dataafgrænses altid på baggrund af sagens egne egenskaber – dvs. sagens 
sagsaktør med rollen ’Ejer’ (CVR), sagens sagsklasse med rollen ’Primær klasse’ (KLE) 
samt værdien i attributten ’Foelsomhed’ under sagsindeksegenskaber. Både modtagersystemet og systemets bruger skal opfylde alle tre dataafgrænsninger for at sagen må 
hentes og vises.
12.2 Dokument
Et dokument dataafgrænses først om fremmest ud fra den sag, som dokumentet er tilknyttet. Dvs. hvis modtagersystemet og systemets bruger opfylder dataafgrænsningen 
for den tilknyttede sag, så må dokumentet som udgangspunkt vises. Dog skal det samtidig tjekkes, om modtagersystemet og systemets bruger opfylder følsomhedsangivelsen for dokumentet. I visse tilfælde kan et dokument have en højere følsomhedsklassi-
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 18/19
fikation, og i det tilfælde kan det være at modtagersystemet og systemets bruger opfylder sagens dataafgrænsning på følsomhed, men at de ikke opfylder dokumentets dataafgrænsning på følsomhed, og i det tilfælde må dokumentet ikke vises.
Et dokument kan være knyttet til mere end en sag. I dette tilfælde er det nok, at modtagersystemet og systemets bruger opfylder dataafgrænsningen for bare én af sagerne, 
som dokumentet er tilknyttet.
Et dokument kan også være oprettet i Sags- og dokumentindekset uden relation til en 
sag. I dette tilfælde skal dataafgrænsingen ske udelukkende på dokumentets egne dataafgrænsningsværdier – dvs. dokumentets dokumentaktør med rollen ’Ejer’ (CVR), dokumentets dokumentklasse med rollen ’Primær klasse’ (KLE) samt værdien af attributten ’Foelsomhed’ under dokumentegenskaber. Dokumentets ejer og primære klasse 
anvendes dermed kun, hvis dokumentet ikke er tilknyttet en sag.
12.3 Bevilling
En bevilling dataafgrænses ud fra bevillingens egen angivelse af ejer og følsomhed, 
den primære emneklasse, som ligger på den bevilligede ydelse samt på de tilknyttede
økonomiske effektueringer. Bevillingen må kun vises, hvis mindst én af de tilknyttede 
økonomiske effektueringer opfylder dataafgrænsningen. Dette gælder også modsat, at 
en økonomisk effektuering kun må vises, hvis mindst én af de tilknyttede bevillinger opfylder dataafgrænsningen (se afsnit nedenfor om økonomisk effektuering). Dataafgrænsningen på bevilling er dog ikke påvirket af den tilknyttede sags dataafgrænsning, 
men ejeren og følsomheden på en bevilling vil oftest være identisk med sagens.
En bevillings emneklasse (KLE) angives ikke på selve bevillingen men derimod på de 
underliggende bevilligede ydelser. Dette betyder, at et modtagersystem og systemets 
bruger kan komme i den situation, at bevillingen gerne må vises, men at det ikke er alle 
bevillingens bevilligede ydelser, der må vises. For at en bevilling må vises, skal emneklassen for minimum en af de underliggende bevilligede ydelser opfylde dataafgrænsningen. Bevillingsobjektets egne dataafgrænsningsattributter er dermed bevillingens 
bevillingsaktør med rollen ’Ejer’ (CVR), klassifikationen med rollen ’Primær klasse’ 
(KLE) på den bevilligede ydelse samt værdien af bevillingens attribut ’Foelsomhed’ under egenskaber for bevilling.
12.4 Økonomisk effektuering
En økonomisk effektuering dataafgrænses ud fra effektueringens egen angivelse af 
ejer, den primære emneklasse, som ligger på den underliggende økonomiske ydelseseffektuering samt på den tilknyttede bevilling. Den økonomiske effektuering må kun vises, hvis mindst én af de tilknyttede bevillinger (via knytning mellem økonomisk ydelseseffektuering og bevilget ydelse) opfylder dataafgrænsningen. Dette gælder også 
modsat, at en bevilling kun må vises, hvis mindst én af de tilknyttede økonomiske effektueringer opfylder dataafgrænsningen (se afsnit ovenfor om bevilling). 
Vejledning til anvisninger for Indeksene
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 19/19
En økonomiske effektuerings emneklasse (KLE) angives ikke på selve den økonomiske 
effektuering men derimod på de underliggende økonomiske ydelseseffektuering. Dette 
betyder, at et modtagersystem og systemets bruger kan komme i den situation, at den 
økonomiske effektuering gerne må vises, men at det ikke er alle underliggende økonomiske ydelseseffektueringer, der må vises. For at en økonomisk effektuering må vises, 
skal emneklassen for minimum en af de underliggende økonomiske ydelseseffektueringer opfylde dataafgrænsningen. Effektueringsobjektets egne dataafgrænsningsattributter er dermed den økonomiske effektueringsaktør med rollen ’Ejer’ (CVR), klassifikationsreferencen i attributten ’Klassifikationsbeskrivelse’ på den økonomiske ydelseseffektuering. 
Effektueringsobjektet har ikke sin egen angivelse af følsomhed og vil derfor udelukkende blive dataafgrænset på følsomhed ud fra bevillingens følsomhed.
1.  Versionsstyring af anvisningerne
Versionsstyring af anvisningerne til anvendelse af Sags- og Dokumentindeks og Ydelsesindeks vil være et vigtigt element i at sikre en tilfredsstillende datakvalitet, så der 
ikke er tvivl om, hvilken version af anvisningerne, der er gældende på et givent tidspunkt.
En givet version af anvisningerne er ikke rettet mod en specifik version af snitfladerne. 
Det er således altid den nyeste version af anvisningerne der er gældende. I de tilfælde 
hvor der er behov for at målrette anvisningerne mod specifikke snitfladeversioner vil det 
fremgå eksplicit i dokumentet.
Opdateringer til anvisningerne kan afstedkommes af flere årsager. Enten har det været 
nødvendigt at ændre anvisningerne, fordi de ikke har været præcise nok, eller man er 
blevet klogere undervejs, fx fordi nye fagsystemer har meldt sig på banen – eller, der er 
foretaget rettelser til XSD’erne, som anvisningerne forholder sig til. 
Når der er tale om rettelser til anvisningerne, der beskriver en ændret måde at anvende 
indekserne på, og det dermed forudsætter at anvendere af indekserne skal ændre i intgrationen til indekserne, vil de berørte anvisninger få et nyt ’major’ versionsnummer, fx 
gå fra version 1.x til 2.0. En sådan ændring kan sammenlignes med udgivelsen af en ny 
majorversion af snitfladerne, der tilsvarende kan medføre ændring til den eksisterende 
integration. En sådan ændring til anvisningerne vil derfor blive varslet og udmeldt på 
samme måde, som en ny major version af snitfladerne. 
Er der tale om rettelser, der ikke kræver ændring i eksisterende integrationer, eksempelvis præciseringer, fejlretteser og udvidelser, vil dokumentet få et nyt ’minor’ versionsnummer, dvs. det sidste ciffer vil blive opdateret, fx fra version 1.3 til 1.4.