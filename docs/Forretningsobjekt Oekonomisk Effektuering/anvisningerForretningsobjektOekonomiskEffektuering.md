# Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT
Dette dokument indeholder definitioner af dataelementerne 
for Økonomisk Effektueringsobjektet i Ydelsesindekset og 
anvisninger til, hvorledes de skal udfyldes af anvendersystemerne. 
Henrik Bering
7. juli 2023
Version: 2.3
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 2/46
Indhold
1. Dokumenthistorik og kontaktinformation..................................................................................................3
1.1 Dokumenthistorik ...........................................................................................................................3
1.2 Kontaktinformation .........................................................................................................................6
1.3 Versionering...................................................................................................................................6
2. Indholdet af anvisningerne .......................................................................................................................6
2.1 Sådan læses gennemgangen af dataelementerne........................................................................8
3. Dataelementer i Økonomisk Effektuering ................................................................................................9
3.1 ID for Økonomisk Effektuering .......................................................................................................9
3.2 Registrering..................................................................................................................................10
3.3 Egenskaber for Økonomisk Effektuering .....................................................................................12
3.4 Relation: Økonomisk Ydelseseffektuering ...................................................................................18
3.5 Relation: Økonomisk Effektueringsaktør .....................................................................................24
3.6 Relation: It-system .......................................................................................................................33
3.7 Relation: Økonomisk Effektueringspart .......................................................................................41
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 3/46
1. Dokumenthistorik og kontaktinformation
1.1 Dokumenthistorik
Dato Version Ændret af Beskrivelse
22.02.2016 Vers. 1.0 Søren Philipsen Første version kar til brug.
10.06.2016 Vers. 1.1 Klaus Rasmussen Rettelser i forhold til forretningsregler i STS indekserne.
Version til offentliggørelse.
19.11.2019 Vers 2.0 Kim Rosendal Orbe Denne version af dokumentet betegnes som en ny majorversion, 
hvilket betyder dokumentet beskriver ændringer der kan kræve 
rettelser i eksisterende integrationer til ydelsesindekset, for at 
anvisningerne fortsat overholdes.
Der er foretaget én ændring af denne karakter. Denne ændring 
beskrives her: 
I erkendelse af at dobbelthistorik ikke anvendes i praksis i ydelsesindekset, er der foretaget en generel ændring i anvisningen 
til udfyldelse af Virkningselementet. Fremover skal Virkning/FraTidspunkt i ydelsesindekset udfyldes med tidspunktet for hvornår 
registreringen er foretaget i fagsystemet. Der er ikke ændringer 
til de øvrige attributter i virkningselementet.
Herudover er der foretaget følgende mindre ændringer og præciseringer i dokumentet. 
Præciseret at ydelsesperiode for økonomisk ydelseseffektuering 
ved korrektion af tidligere effektueringer, skal angives for den 
periode korrektionen vedrører, og ikke for den periode hvor korrektionen er foretaget.
Ved import og opdatering skal livscykluskoden altid angives som 
’Importeret’. Øvrige livscykluskoder anvendes ikke i Ydelses 
indeks. Dette er præciseret her da de er nævnt i 
snitfladedokumentationen. 
Anvisningsdokumentet ’Anvendelse af Klassifikation i indeksene’ 
er udfaset. Tidligere reference til dette dokument er fjernet, og i 
stedet henvises generelt til STS-Klassifikation’s brugergrænseog snitflade, for eksempel i forbindelse med opslag af UUID’er 
for roller og typer i sagsrelationer.
Det er præciseret at IT-System, med rollernene ’Master’ og 
’Afsender’, angives med UUID for IT-systeminstancen, og ikke 
med reference til Organisation
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 4/46
Alle eksempler på UUID’er er rettet til ’1111aaaa-11aa-22bb33cc-111111aaaaaa’ for at tydeliggøre det blot er eksempler.
Angivet URN formatet for angivelse af IT-system i Brugerref i 
Registreingsdata, ’urn:oio:it-system-uuid:<uuid>’
Tilføjet afsnit 1.3 vedrørende versionering.
Kontaktmail er rettet til KDI@Kombit.dk
28.01.2020 Vers. 2.1 Joachim Barslev Anvisning til attributterne AktoerRef og AktoerTypeKode er rettet 
så det frem over skal angives hvilken bruger eller IT-System der 
har foretaget ændringen i kildesystemet. 
AktoerRef og AktoerTypeKode indgår begge i virkningselementet for alle relationer og objekter.
31.08.2020 Vers 2.2 Christian Wahlstrøm Larsen
Konsekvensrettet ”fagsystem” og "kildesystem" til ”afsendersystem”
Konsekvensrettet grundet ændret navngivning af fælleskommunale systemer: 
• ”STS Sags- og dokumentindeks” ændret til ”Fælleskommunalt Sags- og Dokumentindeks”
• ”STS Ydelsesindeks” ændret til ”Fælleskommunalt 
Ydelsesindeks”
• ”STS Organisation” ændret til ”Fælleskommunalt Organisationssystem”
• ”STS Klassifikation” ændret til ”Fælleskommunalt Klassifikationssystem”
Præciseret, at LivscyklusKode og BrugerRef kun er obligatoriske 
ved import og at værdierne ikke efterfølgende kan ændres, samt 
at Tidspunkt er obligatorisk ved import og opdatering.
Præciseret, at master- og afsender it-systemer skal henvise til 
Fælleskommunalt Administrationsmodul.
07.07.2023 Vers. 2.3 Bjørg Tausen Fjernet SE-nummer som mulig ID-type, med hvilken, man kan 
angive økonomiske effektueringsparter af typen ’virksomhed’.
Tilføjet og beskrevet, at det nu er muligt at angive økonomiske 
effektueringsparter af typen ’person’ med ’PersonID’ og ’BorgerID’. Det er også blevet beskrevet, hvilken URN-struktur, der skal 
bruges, når man vil angive en økonomisk effektueringspart med 
’PersonID’ og ’BorgerID’ i dataelement ’ReferenceID’.
Fjernet værdierne; ’Oprettet’, ’Passiviseret’ og ’slettet’ fra dataelementet ’LivscyklusKode’ under ’Registreringsdata’.
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 5/46
Fjernet dataelementet ’SkattepligtigFast’ fra ’Egenskaber for 
økonomisk effektuering’
Fjernet dataelementet ’SkattepligtigReg’ fra ’Egenskaber for 
økonomisk effektuering’ 
Fjernet dataelementet ’ATPBeloeb’ fra ’Egenskaber for økonomisk effektuering’
Fjernet dataelementet ’A-skat’ fra ’Egenskaber for økonomisk effektuering’
Fjernet dataelementet ’SkattefriFast’ fra ’Egenskaber for økonomisk effektuering’
Fjernet dataelementet ’SkattefriReg’ fra ’Egenskaber for økonomisk effektuering’ 
Fjernet dataelementet ’Andet’ fra ’Egenskaber for økonomisk effektuering’
Tilføjet og beskrevet dataelementet ’BeloebEfterSkatATP’ i 
’Egenskaber for økonomisk effektuering’
Tilføjet og beskrevet dataelementet ’BeloebUdbetalt’ i ’Egenskaber for økonomisk effektuering’
Tilføjet og beskrevet dataelementet ’SendtTilUdbetalingTekst’ i 
’Egenskaber for økonomisk effektuering’
Tilføjet og beskrevet dataelementet ’UdbetaltTekst’ i ’Egenskaber for økonomisk effektuering’
10.07.2023 Vers. 2.3 Bjørg Tausen Fjernet dataelementerne ’CPR-nr’, ’CVR-nr’ og ’P-nr’ fra 
økonomisk effektueringspartsrelationen. Felterne må i forvejen 
ikke udfyldes, men skal – som det er tilfældet ved ’BorgerID’ og 
’PersonID’ angives i atributten ’ReferenceID’ med en URN 
indeholdende de respektive ID-typer. Hvilken URN-struktur, der i 
det enkelte tilfælde skal bruges, er specificeret i dataelementet 
’ReferenceID’ under ’Økonomisk Effektueringspart’.
Dataelementet ’BrugervendtNoegle’ under ’Økonomisk 
Effektueringspart’ er rettet, så det nu står som værende valgfrit 
at udfylde. Det er også uddybet med eksempler på CPR-nr, 
CVR-nr, P-nr, BorgerID og PersonID.
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 6/46
Præciseret at dataelementet ’Nettoboleb’ er ændret til ’BeloebSendtTilUdbetaling’ under ’Egenskaber for økonomisk effektuering’ samt skærpet beskrivelsen af ’BeloebSendtTilUdbetaling’ 
(det gamle ’Nettobeleob’).
1.2 Kontaktinformation
Spørgsmål angående klassifikationer skal rettes til KDI@kombit.dk med ”Anvisninger til Indekserne” i emnefeltet.
1.3 Versionering
Anvisningerne er ikke rettet mod en specifik version af snitfladerne. Det er således altid den nyeste version af 
anvisningerne der er gældende. I de tilfælde hvor der er behov for at målrette anvisningerne mod specifikke 
snitfladeversioner vil det fremgå eksplicit i dokumentet.
2. Indholdet af anvisningerne
Anvisningerne indeholder en gennemgang af alle dataelementerne i de XML Schema definitioner, som definerer indholdet 
og strukturen af de data, som udveksles for Økonomisk Effektueringsobjektet i Ydelses indekset. For økonomisk effektueringsobjektet drejer det sig om følgende XSD’er:
• OekonomiskEffektueringIndeks.xsd
• SagDokObjekt.xsd 
• GenerelleDefinitioner.xsd
Til trods for, at det kan lyde teknisk, er der tale om en forretningsmæssig gennemgang af de data, som indgår i 
indekset og ikke en teknisk gennemgang af, hvordan integrationen etableres.
Nedenstående figur er en grafisk illustration af strukturen for Effektueringsobjektet. Figuren er indsat for at give 
overblik over Effektueringsobjektets bestanddele, samt gøre det lettere for læseren at orientere sig og navigere 
rundt i anvisningen. For hvert afsnit i anvisningen gentages figuren i sammenklappet form med angivelse af, 
hvor i figuren, man befinder sig.
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 7/46
Hvor informationsmodellen, der ligger til grund for Ydelsesindekset, er en logisk beskrivelse, er anvisningerne 
derimod beskrevet ud fra en anvendelsesorienteret tilgang, så det er tydeligt, hvad der helt konkret skal udveksles. Denne tilgang betyder dog også, at anvisningerne er blevet omfangsrige, idet mange felter forekommer og 
beskrives flere gange. Selv om et dataelement som udgangspunkt har samme betydning, fx ’Indeks’ der indgår i 
alle relationer, skal det alligvel udfyldes forskelligt afhængigt af den kontekst, det indgår i. Anvisningerne indeholder således den samlede mængde dataelementer, der i dag er defineret for Økonomisk Effektueringsobjektet 
i Indeksene. 
Der henvises til dokumentet ”Vejledning til anvisninger for Indeksene” for yderligere vejledning til anvisningerne.
## 03. Egenskaber for 
økonomisk effekt.
Forretningsdata
Virkning
EFFEKTUERINGSOBJEKT
## 01. ID for økonomisk 
effektuering
## 04. Økonomisk ydelseseffektuering
## 02. Registreringsdata
## EFFEKTUERING
## 05. Økonomisk effektueringsaktør
Forretningsdata
Virkning
06. 
IT-system
Forretningsdata
Virkning
07. Økonomisk 
effektueringspart
Forretningsdata
Virkning
Bevilget ydelse
RELATIONER RELATIONER
Klik på et element i figuren
Forretningsdata
Virkning
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 8/46
2.1 Sådan læses gennemgangen af dataelementerne
Nedenfor er der indsat en kort beskrivelse af, hvordan indholdet af kolonnerne i gennemgangen af dataelementerne skal læses.
XSD-struktur: Her angives stistrukturen (hierarkiet) i XML Schema Definitionen (XSD), således, at dataelementet kan lokaliseres i 
XSD’en.
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
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
kategorier i afsnit 8.1 i ”Vejledning til anvisninger for Indeksene”.
Her angives datatypen, som definerer formatet 
for dataelementet. Datatypen er 
både angivet 
med almindeligt 
sprogbrug (fx 
tekst) og med 
den tekniske 
term (fx string).
Her er der i de fleste 
tilfælde indsat et eksempel på, hvordan 
dataelementet kan 
være udfyldt. 
De indsatte værdier, 
fx en UUID, er udelukkende eksempler, og 
henviser ikke til det 
korrekte objekt.
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 9/46
3. Dataelementer i Økonomisk Effektuering
I nedenstående anvisninger gennemgås alle de dataelementer og relationer, som kan udfyldes i forbindelse 
med import/opdatering af en ny registrering af en økonomisk effektuering.
3.1 ID for Økonomisk Effektuering
ID for den Økonomiske Effektuering er den unikke identifikation af effektueringen i Ydelsesindekset.
XSD-struktur: OekonomiskEffektueringIndeksType
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
UUIDIdentifikator Unik identifikation af den 
økonomiske effektuering i 
Ydelsesindekset. UUID’et 
genereres af afsendersystemet. Afsendersystemet 
kan godt have et andet ID, 
som anvendes som den 
primære nøgle i afsendersystemet, men afsendersystemet skal stadig generere, lagre og anvende 
UUID’et i denne attribut i 
forbindelse med opdatering 
af den økonomiske effektuering i Ydelsesindekset.
[OB2] Altid obligatorisk ved 
import og ved update.
UUID’et genereres af afsendersystemet.
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 10/46
3.2 Registrering
Registreringsdata er ”tekniske” oplysninger, som knyttes til hver registrering af data i Indekset.
Den økonomiske effektuering samler de Økonomiske Ydelseseffektueringer i en samlet enhed, hvor alle bruttobeløb samles, og der eksempelvis er fratrukket Skat, ATP mv. Svarer til en lønseddel, hvor Ydelseseffektueringerne svarer til de enkelte lønlinjer.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Tidspunkt Tidspunktet for, hvornår 
registreringen (oprettelsen eller ændringen) blev 
foretaget i afsendersystemet. 
Dette tidspunkt er identisk 
med det tidspunkt der 
skal angives i Virkning/FraTidspunkt for alle 
elementer der opdateres i 
samme request.
[OB2] Altid obligatorisk ved 
import og ved update.
Tidspunkt angives ud fra følgende format: ’YYYY-MMDDThh:mm:ss.sssTZD’.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
StsTidspunkt Tidspunktet for, hvornår 
registreringen er modtaget i Ydelsesindekset.
Modtagersystemer kan 
søge på dette tidspunkt 
for at finde ud af, hvad 
Ydelsesindekset vidste på 
et givent tidspunkt.
NB: Dette felt udfyldes ikke
af afsendersystemet, men af 
Ydelsesindekset selv. Det er 
muligt at hente dette tidspunkt ud ved opslag på en 
økonomisk effektuering i indekset.
Format: ’YYYY-MMDDThh:mm:ss.sssTZD’.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 11/46
LivscyklusKode Objektets livscyklus beskriver den økonomiske 
effektuerings tekniske tilstand.
I snitfladen er der defineret følgende værdier:
• Importeret
[OB1] Altid obligatorisk ved 
import.
Udfyldes altid med ’Importeret’.
Værdilisten er defineret i 
XSD’en.
Tekst 
(string/enumeration)
Importeret
BrugerRef Aktør af typen bruger, 
som har foretaget registrering (oprettelsen eller 
ændringen af den økonomiske effektuering) i afsendersystemet. Ofte vil 
det være en medarbejder 
(alm. bruger), men det 
kan også være afsendersystemet selv, der har foretaget ændringen, repræsenteret ved IT-system, hvis fx afsendersystemet har foretaget en 
ny beregning af en økonomisk effektuering.
[OB1] Altid obligatorisk ved 
import. Kan ikke efterfølgende ændres.
Hvis afsendersystemet har 
en integration til Fælleskommunalt Organisationssystem
og den bruger, som har foretaget registreringen findes 
her, skal afsendersystemet 
angive en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis afsendersystemet IKKE 
har en integration til Fælleskommunalt Organisationssystem, angives brugerreferencen som en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen er foretaget 
af afsendersystemet selv, 
angives IT-system som en 
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
urn:oio:kmd:sag:RAC
FID:WXYZABC
eller
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
NoteTekst Der kan kobles en note til 
registreringen.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 12/46
3.3 Egenskaber for Økonomisk Effektuering
En økonomisk effektuering er en registrering og dokumentation af, hvad der er effektueret (udbetalt eller sendt 
til udbetaling). Effektueringen fortæller altid om, hvad der er sket, hvorimod effektueringsplanen (i Bevillingen) 
fortæller om, hvad der skal ske fremadrettet.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/AttributListe/Egenskaber
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
BrugervendtNoegle Nøgle, som identificerer
den økonomiske effektuering, og som brugeren forstår.
Dvs. det ID, som vises for 
brugere af afsendersystemet, og som brugerne anvender som deres entydige reference for den 
økonomiske effektuering.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 50 
karakterer
Startdato Effektueringens startdato. [OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
Startdatoen for den periode, 
som effektueringen gælder.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Slutdato Effektueringens slutdato. [OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
Slutdatoen for den periode, 
som effektueringen gælder.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Dispositionsdato Den dato, hvor beløbet 
skal være til disposition 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 13/46
på ydelsesmodtagerens 
konto.
Udregnet på baggrund af effektueringsplanens dispositionsdag. Fx er ”Sidste bankdag i måneden” i januar 
2016 den 29. januar.
SamletBruttobeloeb Det samlede bruttobeløb 
for alle Ydeleseffektueringer i samme effektuering.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
Beløb angives uden tusindetalsseparator og med punktum som separator mellem 
kroner og ører.
Tekst 
(string)
1234.56
BeloebEfterSkatATP ’BeloebEfterSkatATP’ er 
det samlede bruttobeløb, 
som er fratrukket A-SKAT 
og ATP.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
’BeloebEfterSkatATP’ angives med punktum som separator mellem kroner og ører. 
Beløbet angives IKKE
med tusindetalsseparatorer.
Tekst 
(string)
1234.56
BeloebSendtTilUdbetaling
’BeloebSendtTilUdbetaling’ er ’BeloebEfterSkatATP’, eventuelt fratrukket den udbetalende 
myndigheds modregning.
Når den udbetalende 
myndighed foretager 
yderligere modregning i 
ydelsen, vil ’BelobSendtTilUdbetaling’ være 
mindre end ’BeloebEfterSkatATP’. Når dette scenarie indtræffer, vil baggrunden herfor blive beskrevet i ’SendtTilUdbetalingTekst’
Hvis den udbetalende 
myndighed ikke foretager 
modregning, vil ’BeloebSendtTilUdbetaling’og 
’BeloebEfterSkatATP’ 
være ens.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres.
’BeloebSendtTilUdbetaling’ 
angives med punktum som 
separator mellem kronerne 
ører. Beløbet angives IKKE
med tusindetalsseparatorer.
Tekst 
(string)
1234.56
BeloebUdbetalt ’BeloebUdbetalt’ er det 
beløb der vil stå til disposition på borgerens eller 
virksomhedens bankkonto. 
Feltet er ikke obligatorisk.
Feltet udfyldes af den udbetalende myndighed, når der 
modtages en kvittering fra 
Tekst 
(string)
1234.56
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 14/46
I tilfælde, hvor f.eks. 
Gældsstyrelsen laver 
yderligere modregning –
f.eks. i form lønindeholdelse - af det beløb, som 
den udbetalende myndighed har sendt til udbetaling, vil ’BeloebUdbetalt’ 
være mindre end ’BeloebSendtTilUdbetaling’. Når 
dette scenarie indtræffer, 
vil baggrunden herfor 
blive beskrevet i feltet 
’UdbetaltTekst’.
Hvis Gældsstyrelsen ikke 
foretager modregning, vil 
’BeloebSendtTilUdbetaling’og ’BeloebUdbetalt’ 
være ens.
NemKonto, der viser det eksakt udbetalte beløb til effektueringsparten i den aktuelle 
økonomiske effektuering.
SendtTilUdbetalingTekst
I tilfælde, hvor der er en 
forskel mellem ’BeloebEfterSkatATP’ og ’BeloebSendtTilUdbetaling’ -
grundet modregning beskrevet i ’BeloebSendtTilUdbetaling’ - beskrives 
grunden til forskellen i 
dette felt.
Feltet er ikke obligatorisk, 
men skal udfyldes i tilfælde, 
hvor der er en difference 
mellem ’BeloebEfterSkatATP’ og ’BeloebSendtTilUdbetaling’.
Tekst 
(string)
Op til 255 
karakterer
Modregning af ressourceforløbsydelse
UdbetaltTekst I tilfælde, hvor der er en 
forskel mellem ’BeloebSendtTilUdbetaling’ og 
’BeloebUdbetalt’ – som 
følge af modregning fra 
Gældsstyrelsen – beskrives grunden herfor i 
dette felt. 
Feltet er ikke obligatorisk, 
men skal udfyldes i tilfælde, 
hvor der er en difference 
mellem og ’BeloebSendtTilUdbetaling’ og ’BeloebUdbetalt’.
Tekst 
(string)
Op til 255 
karakterer
Modregning fra 
Gældsstyrelsen
Udbetalingsafdeling Tekstuel angivelse af enheden som er ansvarlig 
for udbetalingen.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Udbetalingsafdelingen som 
angives i denne attribut skal 
være den samme som angives i relationen ’Økonomisk 
effektueringsaktør’ med rollen ’Udbetalende enhed’
Tekst 
(string) 
Op til 255 
karakterer
n/a
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 15/46
Attributten giver modtagersystemer mulighed for at vise 
og søge på udbetalingsafdeling, uden at skulle anvende 
Fælleskommunalt Organisationssystem.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Virkning/FraTidspunkt
Tidspunkt, hvor den registrerede Effektuering gælder fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder egenskabsattributter for den økonomiske effektuering, dvs. 
hvis én eller flere af ovenstående (blå) attributter under 
overskriften ’Egenskaber for 
økonomisk effektuering’ er 
udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’.
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Virkning/TilTidspunkt Tidspunkt, hvor den registrerede Effektuering gælder til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder egenskabsattributter for den økonomiske effektuering, dvs. 
hvis én eller flere af ovenstående (blå) attributter under 
overskriften ’Egenskaber for 
økonomisk effektuering’ er 
udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Graenseindikator
(boolean).
true
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 16/46
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem 
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
værdier, men kun værdierne 
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
Tekst 
(string/enumeration)
Bruger
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 17/46
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Virkning/NoteTekst Der kan kobles en note til 
virkningen af oplysninger
under ’Egenskaber for 
økonomisk effektuering’, 
som fx kan beskrive, på 
hvilken baggrund effektueringen er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 18/46
3.4 Relation: Økonomisk Ydelseseffektuering
Den økonomiske ydelseseffektuering er dokumentation af effektueringen af den enkelte bevilgede ydelse. Dette 
svarer til den enkelte linje på en udbetalings- eller bevillingsmeddelelse. 
Relationens rolle ifht. effektueringen: DelAf
Forekomster:
1..*
En effektuering kan have et vilkårligt antal relationer til økonomisk ydelseseffektueringer, men der skal minimum være 1 
relation.
[OB1] Obligatorisk ved import – relationen med 
denne rolle må ikke fjernes, men gerne erstattes af 
en ny relation.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/OekonomiskYdelseEffektueringRelation
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Der findes pt. ikke flere 
roller inden for relationen 
’Økonomisk ydelseseffektuering’, hvorfor alle relationer vil have rollen 
’DelAf’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Rollen på en relation kan 
ikke ændres, da den indgår 
som en del af relationens 
sammensatte ID (relationstype-relationsrolle-indeks).
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Type En økonomisk ydelseseffektuering kan kun være 
af typen ’Økonomisk 
Ydelseseffektuering’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
ReferenceID Identifikation af den Effektuering, som den økonomiske ydelseseffektuering er en del af, dvs. til 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 19/46
dataelementet ’UUIDindifikator’ i afnit 3.1.
Her er det vigtigt, at det er en 
reference til den effektuering, 
som den økonomiske ydelseseffektuering er en del af 
og at den økonomiske effektuering eksisterer i Ydelsesindekset.
Indeks Indeks angiver en unikt 
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Det kan fx være 
et heltal. Indeksværdien 
anvendes sammen med 
relationstypen (her økonomisk ydelseseffektuering) og relationens rolle 
til unikt at udpege en 
specifik relation – fx ’økonomisk ydelseseffektuering-DelAf-1’. Denne 
sammensatte nøgle skal 
fx anvendes ved opdatering af en relation.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Indeksværdien skal altid 
være unikt inden for relationer med samme relationstype og rolle.
Tekst 
(string)
Op til 36 
karakterer
1
YdelsesperiodeStartdato
Startdatoen for den enkelte ydelseseffektuering.
Det vil sige, hvis ydelsen 
udbetales for maj måned, 
så vil startdatoen for 
ydelseseffektueringen 
være 2019-05-01.
Denne dato må ikke forveksles med ’BevilgetYdelseStartdato’ på bevillingsobjektet, som er datoen for, hvornår borgeren første gang har modtaget denne ydelse.
Ved korrekton af Økonomisk ydelseseffektuering 
angives startdato for den
periode korrektionen gælder for, og ikke for den 
periode som korrektionen 
er foretaget i.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 20/46
YdelsesperiodeSlutdato
Slutdatoen for den enkelte ydelseseffektuering.
Det vil sige, hvis ydelsen 
udbetales for maj måned, 
så vil slutdatoen for ydelseseffektueringen være 
2019-05-31.
Denne dato må ikke forveksles med ’BevilgetYdelseSlutdato’ på bevillingsobjektet, som er datoen for, hvornår denne 
ydelse ikke længere udbetales til borgeren.
Ved korrekton af Økonomisk ydelseseffektuering 
angives slutdato for den 
periode korrektionen gælder for, og ikke for den 
periode som korrektionen 
er foretaget i.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Ydelsesbeloeb Bruttobeløb for den enkelte ydelseseffektuering.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Beløb angives uden tusindetalsseparator og med punktum som separator mellem 
kroner og ører.
Skal overholde RegEx:
-?[0-9]+(\.[0-9]+)?
Tekst 
(string)
1234.56
Klassifikationsbeskrivelse
Angivelse af effektueringens emneklassifikation. 
KL Emneplanens emnefacet (KLE) anvendes 
som klassifikationssystem.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Attributten skal udfyldes, da 
relationen anvendes som primær dataafgrænsning.
KLE-nummeret udfyldes med 
6-cifre i formatet ’xx.xx.xx’.
Tekst
(string)
Op til 8 
karakterer
32.24.04
BevilgetYdelseRef/UUIDIdentifikator
Effektueringen knyttes til 
en bevilget ydelse. I 
denne attribut angives referencen til den bevilling, 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 21/46
som den pågældende bevilgede ydelse tilhører.
Skal være identisk med indeholdet af dataelementet 
’UUIDIdentifikator’ under BevilingsID i afsnit 3.1 i ”Anvendelse af Bevillingsobjektet i 
Ydelsesindekset”.
BevilgetYdelseRef/BevilgetYdelseId
Effektueringen knyttes til 
en bevilget ydelse. I 
denne attribut angives referencen til den eksakte 
bevilgede ydelse under 
en bevilling.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Skal være identisk med indeholdet af dataelementet ’Id’ 
under Beviliget Ydelse i afsnit 3.4 i ”Anvendelse af Bevillingsobjektet i Ydelsesindekset”.
Tekst 
(string)
Op til 36 
karakterer
3
Virkning/FraTidspunkt Tidspunkt, hvor relationen til den enkelte ydelseseffektuering gælder 
fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk ydelseseffektuering, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Økonomisk ydelseseffektuering’ er udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’.
Dato og 
tidspunkt 
(dateTime).
2014-03-23
T14:54:23.234+01.00
Virkning/TilTidspunkt Tidspunkt, hvor relationen til den enkelte ydelseseffektuering gælder 
til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk ydelseseffektuering, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Økonomisk ydelseseffektuering’ er udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Graenseindikator
(boolean).
true
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 22/46
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
Tekst 
(string/enumeration)
Bruger
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 23/46
værdier, men kun værdierne
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
baggrund ydelseseffektueringen er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 24/46
3.5 Relation: Økonomisk Effektueringsaktør
Denne relation vedrører sammenhængen mellem den økonomiske effektuering og en økonomisk effektueringsaktør. Den økonomiske effektueringsaktør forekommer to gange med roller:
- Ejer
- Udbetalende enhed
Den økonomiske effektueringsaktør hedder blot ’Aktør’ i XSD’en.
3.5.1 Ejer
Relationens rolle ifht. effektueringen: Ejer
Forekomster:
1
En effektuering SKAL have nøjagtig 1 relation til den økonomiske effektueringsaktør med rollen ’ejer’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne ændres. 
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/Aktoer
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Denne specifikation af 
aktør gælder for rollen 
’Ejer’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Rollen på en relation kan 
ikke ændres, da den indgår
som en del af relationens
sammensatte ID (relationstype-relationsrolle-indeks).
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Type Ejeren af en økonomisk 
effektuering er den kommune/myndighed, som 
bevillingen behandles i. 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 25/46
Det kunne fx være Roskilde kommune eller Udbetaling Danmark.
For rollen ’Ejer’ kan Objekttypen kun være ’Organisation’.
ReferenceID Reference til en aktør, 
som effektueringen knyttes til.
[OB1] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Afsendersystemet kan enten 
angive et UUID, som referer 
direkte til organisationen i 
Fælleskommunalt Organisationssystem, eller angive en 
URN med CVR-nummer. 
UUID foretrækkes.
For at sikre at der refereres 
til organisation af typen kommune/myndighed skal afsender ved angivelse af UUID 
sikre sig, at det objekt af objektypen ’Organisation’, som 
der refereres til, skal have en 
direkte relation til et myndighedsobjekt i Fælleskommunalt Organisationssystem. 
Det er ikke muligt fra indekset at relatere direkte til myndighedsobjektet i Fælleskommunalt Organisationssystem.
URN-strukturen er:
’urn:oio:cvr-nr:[0-9]{8}’
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
eller
urn:oio:cvrnr:12345678
Indeks Indeks angiver en unikt 
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Da der ikke kan 
angives flere økonomiske 
effektueringsaktører med 
samme rolle, anvendes 
attributten ’Indeks’ ikke 
på økonomisk effektueringsaktørrelationer.
MÅ IKKE UDFYLDES.
For rollen ’Ejer’ giver det ikke 
mening at angive et indeks, 
da der kun må være én aktør 
med denne rolle.
Tekst 
(string)
Op til 36 
karakterer
n/a
CVR-nr Organisationens CVRnummer.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Tekst 
(string)
Op til 8 
karakterer
12345678
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 26/46
CVR-nummer på kommunen 
(eller UDK) angives, da relationen anvendes som primær 
dataafgrænsning, og ejerens 
CVR-nummer dermed af performancemæssige hensyn 
skal fremgå direkte af Ydelsesindeksets egne data.
CVR angives med 8 cifre.
FuldtNavn Fuldt navn på Aktøren fx 
kommunens navn (organisation).
[OB1] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Attributten er obligatorisk, da 
navnet anvendes af modtagersystemer ved søgning.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 255 
karakterer
Roskilde kommune
BrugervendtNoegle Den brugervendte nøgle 
er en unik identifikation af 
en organisation, som en 
bruger kan forstå. Det 
kan fx være et kommunenummer.
[OB4] Obligatorisk, hvis attributten ’ReferenceID’ er udfyldt med en URN.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 50 
karakterer
Virkning/FraTidspunkt Tidspunkt, hvor relationen til aktøren gælder 
fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringsaktør med rollen ’ejer’, 
dvs. hvis én eller flere af 
ovenstående (blå) attributter 
under overskriften ’Ejer’ er 
udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
Dato og 
tidspunkt 
(dateTime).
2014-03-23
T14:54:23.234+01.00
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 27/46
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’..
Virkning/TilTidspunkt Tidspunkt, hvor relationen til aktøren gælder 
til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringsaktør med rollen ’ejer’, 
dvs. hvis én eller flere af 
ovenstående (blå) attributter 
under overskriften ’Ejer’ er 
udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Graenseindikator
(boolean).
true
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 28/46
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
værdier, men kun værdierne
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Tekst 
(string/enumeration)
Bruger
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
baggrund effektueringsaktøren er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
3.5.2 Udbetalende enhed
Relationens rolle ifht. effektueringen: Udbetalende enhed
Forekomster:
1
En effektuering SKAL have nøjagtig 1 relation til den økonomiske effektueringsaktør med rollen ’udbetalende enhed’.
[OB1] Obligatorisk ved import – relationen med 
denne rolle må ikke fjernes, men gerne erstattes af 
en ny relation.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/Aktoer
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Denne specifikation af 
aktør gælder for rollen 
’Udbetalende enhed’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Rollen på en relation kan 
ikke ændres, da den indgår
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 29/46
som en del af relationens
sammensatte ID (relationstype-relationsrolle-indeks).
Type Udbetalende enhed for 
den økonomisk effektuering er den organisatoriske enhed i kommunen/myndigheden, som 
udbetaler ydelsen. 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
For rollen ’Udbetalende enhed’ kan Objekttypen kun 
være ’OrgEnhed’.
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
ReferenceID Reference til en aktør, 
som effektueringen knyttes til.
[OB1] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Referencen kan angives enten som UUID til aktøren i 
Fælleskommunalt Organisationssystem, eller som URN. 
UUID foretrækkes.
Ved angivelse af URN skal 
følgende URN-struktur anvendes: ’urn:oio:<org>:<idtype>:xxxx’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
Indeks Indeks angiver en unikt 
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Da der ikke kan 
angives flere økonomiske 
effektueringsaktører med 
samme rolle, anvendes 
attributten ’Indeks’ ikke 
på økonomisk effektueringsaktørrelationer.
MÅ IKKE UDFYLDES.
For rollen ’Udbetalende enhed’ giver det ikke mening at 
angive et indeks, da der kun 
må være én aktør med 
denne rolle.
Tekst 
(string)
Op til 36 
karakterer
n/a
CVR-nr Organisationens CVRnummer.
[OB4] Obligatorisk, hvis attributten ’ReferenceID’ er udfyldt med en URN – ellers 
må den ikke udfyldes.
Attributten angiver CVRnummeret for den overliggende myndighed – altså typisk kommunens CVR-nummer.
CVR angives med 8 cifre.
Tekst 
(string)
Op til 8 
karakterer
12345678
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 30/46
FuldtNavn Fuldt navn på den organisatoriske enhed, der udbetaler ydelsen.
[OB1] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Attributten er obligatorisk, da 
navnet anvendes af modtagersystemer ved søgning.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 255 
karakterer
BrugervendtNoegle Den brugervendte nøgle 
er en unik identifikation af 
en organisatorisk enhed, 
som en bruger kan forstå. 
Det kan fx være et afdelingsnummer.
[OB4] Obligatorisk, hvis attributten ’ReferenceID’ er udfyldt med en URN.
En brugervendt nøgle skal 
være unik inden for en objekttype inden for en kommune/myndighed. Det betyder fx at to organisationsenheder i samme kommune
ikke må have samme brugervendte nøgle.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 50 
karakterer
Virkning/FraTidspunkt Tidspunkt, hvor relationen til aktøren gælder 
fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringsaktør med rollen ’udbetalende enhed’, dvs. hvis én 
eller flere af ovenstående 
(blå) attributter under overskriften ’Udbetalende enhed’ 
er udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
Dato og 
tidspunkt 
(dateTime).
2014-03-23
T14:54:23.234+01.00
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 31/46
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’..
Virkning/TilTidspunkt Tidspunkt, hvor relationen til aktøren gælder 
til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringsaktør med rollen ’udbetalende enhed’, dvs. hvis én 
eller flere af ovenstående 
(blå) attributter under overskriften ’Udbetalende enhed’ 
er udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Graenseindikator
(boolean).
true
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 32/46
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
værdier, men kun værdierne 
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Tekst 
(string/enumeration)
Bruger
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
baggrund effektueringsaktøren er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 33/46
3.6 Relation: It-system
Relationen angiver, hvilken it-system instans, der har foretaget effektueringen. Dette angives med UUID for den 
pågældende IT-systeminstans.
Økonomiske effektueringer kan eksistere digitalt i et eller flere afsendersystemer. Et af disse IT-system instanser opbevarer ’originalen’ af effektueringen - dette IT-system kaldes Master.
Effektueringer afleveres i Fælleskommunalt Ydelsesindeks af en IT-system instans– dette IT-system kaldes Afsender. Ofte vil det være samme system, der både er master for effektueringen, og som afleverer effektueringen i indekset. En IT-system instans kan oprettes med en af de to ovennævnte roller:
- Master
- Afsender
Mastersystemet kan ikke ændres. Det håndhæves af Ydelsesindekset, at det altid er samme master system, 
der står bag en opdatering af en effektuering.
3.6.1 Master
Relationens rolle ifht. effektueringen: Master
Forekomster:
1
En effektuering SKAL have nøjagtig 1 relation til et IT-system med rollen ’Master’.
[OB1] Obligatorisk ved import – relationen med 
denne rolle må ikke fjernes, men gerne erstattes af 
en ny relation.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/ItSystem
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Denne specifikation af en
IT-system instans gælder 
for rollen ’Master’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Rollen på en relation kan 
ikke ændres, da den indgår 
UUID
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 34/46
som en del af relationens
sammensatte ID (relationstype-relationsrolle-indeks).
Type Objekttypen fra Fælleskommunalt Klassifikationssystem, her af typen 
IT-system instans.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
For rollen ’Master’ kan Objekttypen kun være ’IT-system’.
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
ReferenceID UUID som henviser til et 
it-system i Fælleskommunalt Administrationsmodul
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Denne reference anvendes 
som primær dataafgrænsning på IT-system, hvorfor 
den ikke kan erstattes ved at 
udfylde attributterne ’SystemNavn’ og ’SystemURI’ 
nedenfor.
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Indeks Indeks angiver en unik 
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Da der ikke kan 
angives flere IT-systemer 
med samme rolle, anvendes attributten ’Indeks’ 
ikke på IT-systemrelationer.
MÅ IKKE UDFYLDES.
For rollen ’Master’ giver det 
ikke mening at angive et indeks, da der kun må være ét 
IT-system med denne rolle.
Tekst 
(string)
Op til 36 
karakterer
n/a
SystemNavn Navnet på IT-system instansen. 
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Attributten giver modtagersystemer mulighed for at vise 
og søge på systemnavn.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 255 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 35/46
SystemURI URI (Uniform Ressource 
Identifier) for IT-systemet. 
Muliggør hop til IT-systemet.
MÅ IKKE UDFYLDES.
Hop til IT-system håndteres 
ikke længere via dette felt.
Tekst 
(string)
Op til 255 
karakterer
n/a
Virkning/FraTidspunkt Tidspunkt, hvor relationen til IT-systemet gælder fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for IT-system med rollen 
’master’, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Master’ er udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’..
Dato og 
tidspunkt 
(dateTime)
2014-03-23
T14:54:23.234+01.00
Virkning/TilTidspunkt Tidspunkt, hvor relationen til IT-systemet gælder til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for IT-system med rollen 
’master’, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Master’ er udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Graenseindikator
(boolean).
true
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 36/46
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
værdier, men kun værdierne
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Tekst 
(string/enumeration)
Bruger
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives WindowsTekst 
(string)
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 37/46
baggrund oplysningerne 
om IT-systemet er ændret.
stil: ”carriage-return followed 
by a newline (\r\n)”.
Op til 1024 
karakterer
3.6.2 Afsender
Relationens rolle ifht. effektueringen: Afsender
Forekomster:
1
En effektuering SKAL have nøjagtig 1 relation til en IT-system instans med rollen 
’Afsender’.
[OB1] Obligatorisk ved import – relationen med 
denne rolle må ikke fjernes, men gerne erstattes af 
en ny relation.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/ItSystem
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Denne specifikation af en
IT-system instans gælder 
for rollen ’Afsender’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Rollen på en relation kan 
ikke ændres, da den indgår
som en del af relationens
sammensatte ID (relationstype-relationsrolle-indeks).
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Type Objekttypen fra Fælleskommunalt Klassifikationssystem, der relaterer 
til en aktør i Fælleskommunalt Organisationssystem, her af typen IT-system.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
For rollen ’Afsender’ kan Objekttypen kun være ’IT-system’.
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
ReferenceID UUID som henviser til et 
it-system i Fælleskommunalt Administrationsmodul
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
UUID 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Indeks Indeks angiver en unikt 
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Da der ikke kan 
angives flere IT-systemer 
med samme rolle, anvendes attributten ’Indeks’ 
ikke på IT-systemrelationer.
MÅ IKKE UDFYLDES.
For rollen ’Afsender’ giver 
det ikke mening at angive et 
indeks, da der kun må være 
ét IT-system med denne 
rolle.
Tekst 
(string)
Op til 36 
karakterer
n/a
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 38/46
SystemNavn Navnet på IT-systemet. 
Attributten anvendes kun, 
hvis IT-systemet ikke er 
oprettet i Fælleskommunalt Organisationssystem.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Attributten giver modtagersystemer mulighed for at vise 
og søge på systemnavn.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string)
Op til 255 
karakterer
SystemURI URI (Uniform Ressource 
Identifier) for IT-systemet. 
Muliggør hop til IT-systemet.
MÅ IKKE UDFYLDES.
Hop til IT-system håndteres 
ikke længere via dette felt.
Tekst 
(string)
Op til 255 
karakterer
n/a
Virkning/FraTidspunkt Tidspunkt, hvor relationen til IT-systemet gælder fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for IT-system med rollen 
’afsender’, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Afsender’ er udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’..
Dato og 
tidspunkt 
(dateTime).
2014-03-23
T14:54:23.234+01.00
Virkning/TilTidspunkt Tidspunkt, hvor relationen til IT-systemet gælder til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for IT-system med rollen 
’afsender’, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Afsender’ er udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Graenseindikator
(boolean).
true
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 39/46
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Virkning/AktoerRef Bruger eller system som 
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
Tekst 
(string/enumeration)
Bruger
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 40/46
værdier, men kun værdierne 
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
baggrund oplysningerne 
om IT-systemet er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 41/46
3.7 Relation: Økonomisk Effektueringspart
Relationen ’Økonomisk Effektueringspart’ beskriver den part, som har modtaget betalingen (også kaldet Ydelsesmodtager). Det er ikke nødvendigvis den samme part, som har fået Bevillingen.
Svarer til den part, som blev lagt ind som ’Ydelsesmodtager’ i Bevilling.
Relationens rolle ifht. effektueringen: Effektueringsmodtager
Forekomster:
1
En effektuering SKAL have nøjagtig 1 relation til en økonomisk effektueringspart
med rollen ’Effektueringsmodtager’.
[OB1] Obligatorisk ved import – relationen med 
denne rolle må ikke fjernes, men gerne erstattes af 
en ny relation.
XSD-struktur: OekonomiskEffektueringIndeksType/Registrering/RelationListe/OekonomiskEffektueringPart
Navn på dataelement Definition Regler for udfyldelse Datatype Evt. eksempel
Rolle Der findes ikke flere roller 
inden for relationen ’Økonomisk effektueringspart’, 
hvorfor rollen altid vil 
være ’Effektueringsmodtager’.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation. 
Rollen på en relation kan 
ikke ændres, da den indgår 
som en del af relationens 
sammensatte ID (relationstype-relationsrolle-indeks).
UUID
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
Type Angiver typen af Part, der 
optræder som økonomisk 
effektueringsaktør.
Effektueringsmodtageren 
kan både være en person 
eller en virksomhed.
[OB1] Obligatorisk ved import – må ikke fjernes, men 
gerne erstattes af en ny relation.
Objekttypen kan kun være 
’Person’ eller ’Virksomhed’.
UUID
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa
EFFEKTUERINGSOBJEKT
01. ID for økonomisk 
effektuering
02. 
Registreringsdata
EFFEKTUERING
05. Økonomisk 
effektueringsaktør
06. 
IT-system
07. Økonomisk 
effektueringspart
RELATIONER RELATIONER
Klik på et element i figuren
03. Egenskaber for 
økonomisk effekt.
04. Økonomisk 
ydelseseffektuering
Her er du
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 42/46
ReferenceID Reference til en part, 
som sagen knyttes til.
[OB3] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Hvis attributten ’Type’ er udfyldt med ’Person’, angives 
CPR-nummer som URN i 
denne attribut.
URN-strukturen er følgende:
’urn:oio:cpr-nr:[0-9]{10}’
Hvis attributten ’Type’ er udfyldt med ’Person’, men vedkommende endnu ikke er tildelt et administrativt CPRnummer, angives ’PersonID’ 
som URN i denne attribut.
URN-strukturen er følgende: 
urn:oio:us:personid:[0-9]{7}
Ved borgere, der administreres i Udbetaling Danmarks 
IT-systemer, og som endnu 
ikke er tildelt et administrativt 
CPR-nummer, angives ’BorgerID’ som URN i denne attribut. 
URN-strukturen er følgende: 
urn:oio:udk:borgerid:[0-9]{12}
Hvis attributten ’Type’ er udfyldt med ’Virksomhed’, angives CVR- eller P-nummer 
som URN i denne attribut.
URN-strukturen er følgende:
’urn:oio:cvr-nr:[0-9]{8}’
’urn:oio:pnr:[0-9]{10}’
Hvis parten ikke har hverken 
CPR-, CVR- eller P-nummer 
angives partens fulde navn 
URN
(string) 
Op til 255 
karakterer
urn:oio:cprnr:0123456789
urn:oio:us:personid:1234567
urn:oio:us:borgerid:123456789123
urn:oio:cvrnr:12345678
urn:oio:pnr:12345678
90
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 43/46
som URN med denne struktur:
urn:oio:fuldtnavn:xxxx
Det er ikke muligt at referere 
til et objekt i Fælleskommunalt Organisationssystem, da 
Sags- og dokumentindekset 
ikke tillader UUID’er i denne 
attribut, og man kan derfor 
ikke angive en organisatorisk 
enhed eller en bruger som 
part i sag. Hvis man har behov for at angive en kommune eller fx en skole som 
part angives dette som en 
virksomhed med URN for 
CVR- eller P-nummer.
urn:oio:fuldtnavn:Hans Hansen
Indeks Indeks angiver en unikt
streng for denne relation i 
forhold til andre relation 
af samme relationstype 
og rolle. Da der ikke kan 
angives flere økonomiske 
effektueringsparter med 
samme rolle, anvendes 
attributten ’Indeks’ ikke 
på økonomisk effektueringspartrelationer.
MÅ IKKE UDFYLDES.
Det giver ikke mening at angive et indeks, da der kun 
må være én Økonomisk Effektueringspart.
Tekst 
(string)
Op til 36 
karakterer
n/a
FuldtNavn Fuldt navn på parten. [OB1] Obligatorisk ved import – må ikke fjernes men 
gerne erstattes af en ny relation. 
Attributten er obligatorisk, da 
navnet anvendes af modtagersystemer ved søgning.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre tekstformateringstegn.
Tekst 
(string) 
Op til 255 
karakterer
Hans Hansen
BrugervendtNoegle En unik identifikation af 
en virksomhed eller person (i dette tilfælde effektueringsmodtageren), 
som en bruger kan forstå. 
Det kan være ved et:
IKKE OBLIGATORISK
Den brugervendte nøgle skal 
være unik for den effektueringsmodtager, der er tale 
Tekst 
(string) 
Op til 50 
karakterer
n/a
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 44/46
CPR-nummer (ID til identifikation af statsborgere og borgere med opholdstilladelse eller 
andre anliggender i Danmark)
CVR-nummer (ID til identifikation af en virksomhed)
P-nummer (ID til identifikation 
af underliggende produktionsenhed)
BorgerID (ID på borgere, der 
administreres i Udbetaling Danmarks IT-systemer, og som 
endnu ikke er tildelt et administrativt CPR-nummer)
PersonID (ID som Udlændingestyrelsen udsteder til udenlandske borgere, der endnu ikke 
er blevet tildelt et administrativt 
CPR-nummer)
om ift. den aktuelle økonomiske effektuering. En effektueringsmodtager kan godt forekomme på forskellige økonomiske effektueringer med 
den samme brugervendte 
nøgle.
Tekstformatet er UTF8. Teksten skal angives som en enkelt linje og må dermed ikke 
indeholde linjeskift eller andre 
tekstformateringstegn.
Virkning/FraTidspunkt Tidspunkt, hvor relationen til den Økonomiske 
Effektueringspart gælder 
fra/har virkning fra.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringspart, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Økonomisk effektueringspart’ er udfyldt.
VirkningFra udfyldes med 
tidspunktet for hvornår registreringen er foretaget i afsendersystemet. Dette gøres 
da dobbelthistorik ikke anvendes i Ydelsesindekset, og 
ændringen derfor har virkning fra registreringstidspunktet.
VirkningFra skal dermed 
være identisk med det tidspunkt, der er angivet i attributten ’Tidspunkt’ under elementet ’Registreringsdata’.
Dato og 
tidspunkt 
(dateTime).
2014-03-23
T14:54:23.234+01.00
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 45/46
Virkning/TilTidspunkt Tidspunkt, hvor relationen til den Økonomiske 
Effektueringspart gælder 
til/har virkning til.
[OB5] Obligatorisk, hvis registeringen indeholder attributter for økonomisk effektueringspart, dvs. hvis én eller 
flere af ovenstående (blå) attributter under overskriften 
’Økonomisk effektueringspart’ er udfyldt.
I attributten TilTidspunkt kan 
der kun angives uendelig. 
Det giver ikke mening at angive et specifikt tidspunkt for 
en effektuering.
Uendelig angives som en 
grænseindikator med værdien ’true’. Uendelig i TilTidspunkt vil altid sige uendelig 
frem i tid (+oo).
Grænseindikatoren kan kun 
være ’true’.
Graenseindikator
(boolean).
true
Virkning/AktoerRef Bruger eller system som
har tilføjet eller ændret 
data i mastersystemet. 
Ofte vil det være en medarbejder (alm. bruger), 
men det kan også være 
mastersystemet selv, der 
har foretaget ændringen, 
hvis fx mastersystemet 
har foretaget en ny beregning af en ydelse.
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret.
Hvis mastersystemets bruger 
er oprettet i Fælleskommunalt Organisationssystem 
skal mastersystemet angive 
en UUID på den pågældende bruger i Fælleskommunalt Organisationssystem.
Hvis brugeren ikke er oprettet i Fælleskommunalt Organisationssystem, så angives 
en URN med følgende struktur: 
’urn:oio:<org>:<idtype>:xxxx’
Hvis ændringen ikke er foretaget af en bruger, angives 
mastersystemet med en 
URN med følgende struktur, 
hvor uuid er IT-system instansen fra administrationsmodulet: 
’urn:oio:it-systemuuid:<uuid>’.
UUID eller 
URN 
(string)
1111aaaa-11aa22bb-33cc111111aaaaaa 
eller
urn:oio:kmd:sag:administrativenhed:LOSID:012345678
eller 
urn:oio:it-systemuuid:1111aaaa-11aa22bb-33cc111111aaaaaa
Anvendelse af Økonomisk Effektueringsobjektet i Ydelsesindekset
KOMBIT A/S Halfdansgade 8 2300 København S Tlf 3334 9400 www.kombit.dk kombit@kombit.dk CVR 19 43 50 75 Side 46/46
Virkning/AktoerTypeKode
Aktørtypen for aktøren 
angivet i attributten ’AktørRef’. 
[OB5] Obligatorisk hvis data 
er tilføjet eller ændret. 
Der skal angives en af følgende værdier: 
• Bruger
• ItSystem
Værdilisten, der er defineret i 
XSD’en, indeholder flere 
værdier, men kun værdierne 
nævnt ovenfor må anvendes.
OBS: Frem til januar 2020 
skulle dette felt udfyldes med 
’Organisation’ eller ’OrganisationEnhed’, så disse værdier optræder stadig i data.
Tekst 
(string/enumeration)
Bruger
Virkning/NoteTekst Der kan kobles en note til 
virkningen af ovenstående oplysninger, som fx 
kan beskrive, på hvilken 
baggrund den Økonomiske Effektuering er ændret.
Ikke obligatorisk.
Tekstformatet er UTF8. Teksten kan indeholde linjeskift. 
Linjeskift angives Windowsstil: ”carriage-return followed 
by a newline (\r\n)”.
Tekst 
(string)
Op til 1024 
karakterer