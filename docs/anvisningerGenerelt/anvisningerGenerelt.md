# Generelle anvendelsesmønstre til indekserne

Dette dokument er et tillæg til anvisningsdokumenterne til Sags og dokumentindeks og Ydelsesindeks. I dokument angives anvendelsesmønstre til opdatering af data i indekserne.

**Christoffer Rexen**  
**2024. November 08.**  
**Version: 0.1**

---

**Indhold**
- [1. Dokumenthistorik og kontaktinformation]
  - [1.1 Dokumenthistorik](#11-change-log)
  - [1.2 Kontaktinformation](#12-kontaktinformation)
- [2. anvendelsesmønstre](#2-anvendelsesmønstre)
  - [2.1 AM-01 Angivelse af Sagstilstand ved import af sag](#21-am-01-angivelse-af-sagstilstand-ved-import-af-sag)
  - [2.2 AM-02 Slet relation fra sag – logisk slet via virkningselementet](#22-am-02-slet-relation-fra-sag--logisk-slet-via-virkningselementet)
  - [2.3 AM-03 Slet relation fra sag – fysisk sletning](#23-am-03-slet-relation-fra-sag--fysisk-sletning)
  - [2.4 AM-04 Ændring af relation i sag](#24-am-04-ændring-af-relation-i-sag)
  - [2.5 Anvendelsesmønstre i pipeline](#25-anvendelsesmønstre-i-pipeline)

---

## 1. Dokumenthistorik og kontaktinformation

### 1.1 Change Log
| Dato        | Version | Ændret af           | Beskrivelse       |
|-------------|---------|---------------------|-------------------|
| 2024.11.08  | Vers. 0.1 | Christoffer Rexen  | Wiki Created |

### 1.2 Kontaktinformation
Spørgsmål og kommentarer angående anvendelse af indekserne skal rettes til **KDI@kombit.dk** med "Anvisninger til Indekserne" i emnefeltet.

---

## 2. Anvendelsesmønstre

Formålet med anvendelsesmønstre er at supplere anvisningerne med nogle anvendelsesorienterede scenarier, hvor der med udgangspunkt i forretningsmæssige hændelser beskrives hvordan indekserne opdateres. Anvendelsesmønstrene beskriver kaldsmønstre, dvs. i overordnet form hvilke operationer i indekserne der kan anvendes i den konkrete situation. Der kan være andre måder at foretage samme forretningsmæssige opdatering af indekserne på, som kan være mere passende for den enkelte leverandør at implementere.

---

### Oversigt over beskrevne anvendelsesmønstre

| Mønster     | Anvendt service       | Operation       |
|-------------|------------------------|-----------------|
| AM-01       | SagDokumentIndeks      | Importer        |
| AM-02       | SagDokumentIndeks      | Opdater         |
| AM-03       | SagIndeks              | Kasser          |
| AM-04       | SagDokumentIndeks      | Opdater         |

---

### 2.1 AM-01 Angivelse af Sagstilstand ved import af sag

Når en sag første gang importeres i indeks, skal hele sagens fremdriftsforløb fra den er opstået til tidspunktet hvor den importeres i indekset, angives. 

**Operation:** Importer, i SagDokumentIndeks.

#### XML-eksempel
Nedenfor vises TilstandListe for registrering af aktuel og historiske tilstande for en sag med det ovenfor skitserede forløb.

| Fremdriftsstatus | Virkning fra | Virkning til |
|------------------|--------------|--------------|
| Opstaaet         | 12-05-2019   | 22-06-2019   |
| Oplyst           | 22-06-2019   | 05-08-2019   |
| Afgjort          | 05-08-2019   | +∞           |

---

### 2.2 AM-02 Slet relation fra sag – logisk slet via virkningselementet

Obligatoriske relationer kan ikke fjernes fra en sag, men kan udelukkende ændres. Dette mønster er dermed udelukkende muligt for optionelle relationer som f.eks. "Sekundær part" eller journalpost.

**Operation:** Opdater i SagDokumentIndeks.

---

### 2.3 AM-03 Slet relation fra sag – fysisk sletning

Obligatoriske relationer kan ikke fjernes fra en sag, men kan udelukkende ændres. Dette mønster er dermed udelukkende muligt for optionelle relationer som f.eks. "Sekundær part", aktøren "Andre behandlere" eller journalpost.

**Operation:** Kasser, i SagIndeks.

---

### 2.4 AM-04 Ændring af relation i sag

Ved ændring af relationer i indekserne tænkes her på en udskiftning af det objekt (angivet med ReferenceId) som relationen peger på. 

**Operation:** Opdater i SagDokumentIndeks.

---

### 2.5 Anvendelsesmønstre i pipeline

Nedenstående liste viser anvendelsesmønstre der arbejdes på at få indarbejdet i dette dokument. Hvis du har idéer eller ønsker til specifikke mønstre der skal beskrives, er du meget velkommen til at skrive til KDI@kombit.dk med "Anvisninger til Indekserne" i emnefeltet.

**Mønstre i pipeline…**
- Tilføj dokument til sag
- Fjern dokument fra sag
- Tilføj samme dokument til flere sager
- Tilføj samme journalnotat til flere sager
- Opret Sikkerhedsprofil for flere personer
