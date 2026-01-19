# 🎨 Workshop 2 (halv-/heldag) – UX og agil udvikling

## 🎯 Målsætning

Dagen bruges på at forfine workflows fra et UX-perspektiv og forstå hvordan agile teams arbejder med at levere værdi til brugeren. Vi bygger videre på de workflows der blev identificeret i Workshop 1, og tilføjer brugerrejsen samt teamorganisering.

## 📦 Output

- Forfinede workflows med brugerrejse beskrevet trin for trin
- Tydelig beskrivelse af hvad brugeren ser, kan vælge, gør, og hvilken feedback de får
- Liste over data der skal være tilgængeligt i hvert trin
- Forståelse for agile roller og hvordan de samarbejder
- Skabelon: [Workflow-skema UX](skabeloner/workflow-skema-ux.md)

---

## 📅 Dagsagenda (09:00–15:30)

|Tid|Punkt|
|---|---|
|09:00–09:15|Opstart og recap af Workshop 1|
|09:15–09:45|Del 1: Introduktion til UX-perspektivet|
|09:45–10:45|Del 1: Øvelse – Forfin workflows med UX-fokus|
|10:45–11:00|Pause|
|11:00–12:00|Del 1: Gennemgang og diskussion af workflows|
|12:00–12:45|Frokost|
|12:45–13:00|Del 2: Hvad er agil udvikling?|
|13:00–13:20|Del 2: Hvorfor agilt?|
|13:20–13:45|Del 2: Agile roller og artifacts|
|13:45–14:00|Pause|
|14:00–14:30|Brug af AI til transformation af workflows|
|14:30–15:00|Øvelse: Transformer egne workflows med AI|
|15:00–15:30|Afrunding og næste skridt|

---

## 🎤 Slides til gennemgang

### Slide: Opstart og recap

#### Hvad vi opnåede i Workshop 1

- Liste over vigtigste workflows
- Systemlandskab og integrationer

#### Hvad vi tilføjer i dag

- **Del 1 – UX-perspektiv**: Brugerens rejse gennem workflowet
- **Del 2 – Agil udvikling**: Hvordan teams leverer værdi sammen

---

## Del 1: UX-perspektiv

### Slide: Introduktion til UX-perspektivet

#### Fra teknisk flow til brugerrejse

I Workshop 1 fokuserede vi på:

- Hvilke systemer der kaldes
- Input/output mellem systemer
- Teknisk infrastruktur

Nu fokuserer vi på:

- Hvad brugeren ser og oplever
- Hvilke valg brugeren træffer
- Hvilken feedback brugeren får
- Hvilke data der skal vises

#### Den simple model

For hvert trin i brugerrejsen:

1. **Du ser**: Hvad vises på skærmen?
2. **Du kan vælge**: Hvilke muligheder har du?
3. **Du gør**: Hvad klikker/udfylder du?
4. **Der sker**: Hvilken feedback får du?
5. **Hvor kommer data fra**: Hvilke systemer leverer data?

---

### Slide: Øvelse – Forfin workflows med UX-fokus

#### Formål

Tag et workflow fra Workshop 1 og beskriv brugerrejsen trin for trin.

#### Fremgangsmåde

1. Vælg et workflow (helst et I arbejdede med i Workshop 1)
2. Identificer de trin brugeren går igennem
3. For hvert trin: Udfyld "Du ser", "Du kan vælge", "Du gør", "Der sker", "Hvor kommer data fra"
4. Brug skabelonen: [Workflow-skema UX](skabeloner/workflow-skema-ux.md)
5. Se eksempler: [VLAN provisioning](eksempler/workflow-ux-1-vlan-provisionering.md), [Firewall regel](eksempler/workflow-ux-2-firewall-regel.md)

#### Tips

- Tænk som brugeren, ikke som system
- Vær konkret: "Du ser en dropdown med zoner" ikke "Du ser zoner"
- Beskriv feedback: Hvad sker der når du klikker?
- Identificer hvilke data der kommer fra hvilke systemer

#### Tid

60 minutter i grupper

---

### Slide: Gennemgang af workflows

- Hver gruppe præsenterer ét workflow (5-10 min)
- Fokus på: Er brugerrejsen tydelig?
- Diskutér: Mangler der trin eller feedback?
- Identificer: Fælles mønstre på tværs af workflows

---

## Del 2: Agil udvikling

### Slide: Hvad er agil udvikling?

Agil udvikling er en proces til at navigere i et skiftende miljø gennem korte cyklusser, løbende feedback og tilpasning.

#### At navigere i forandring

I stedet for at lave én stor plan på forhånd:

- **Planlæg kort sigt**: Fokuser på de næste 2-4 uger
- **Lever løbende**: Få funktionalitet i produktion hurtigt
- **Lær og tilpas**: Brug feedback til at justere retning
- **Gentag**: Fortsæt i korte cyklusser (sprints)

#### Ritualer der understøtter processen

- **Sprint Planning** (hver 2-4 uge): Vælg hvad der skal bygges baseret på nuværende prioriteter
- **Daily Standup** (15 min dagligt): Synkroniser team og identificer blokeringer
- **Sprint Review** (hver sprint): Demo og få feedback fra brugere
- **Sprint Retrospective** (hver sprint): Lær og forbedr processen

#### Hvordan ritualerne hjælper

- **Korte cyklusser**: Gør det let at ændre retning
- **Daglig synkronisering**: Fanger problemer tidligt
- **Løbende feedback**: Sikrer vi bygger det rigtige
- **Kontinuerlig forbedring**: Lærer af hver sprint

---

### Slide: Hvorfor agilt?

#### Verden forandrer sig

- **Brugerkrav ændrer sig konstant**: Hvad brugerne vil have i dag, er anderledes om 6 måneder
- **Teknologien udvikler sig hurtigt**: Nye muligheder opstår løbende som vi skal kunne udnytte
- **Konkurrencen skærpes**: Andre aktører lancerer nye løsninger hurtigere end før
- **Forretningen skal kunne tilpasse sig**: Regulatoriske krav, marked og strategier ændrer sig
- **Kompleksiteten stiger**: Vi kan ikke forudsige alle krav på forhånd

#### Derfor har vi brug for agilitet

- **Hurtigere respons på ændringer**: Når verden ændrer sig, skal vi kunne følge med
- **Løbende validering**: Tjek om vi bygger det rigtige, inden vi har brugt for mange ressourcer
- **Reduceret risiko**: Undgå at bruge 12 måneder på noget der ikke længere er relevant
- **Større værdi**: Lever funktionalitet der giver værdi nu, ikke om et år
- **Tættere på brugerne**: Forstå hvad de faktisk har brug for gennem løbende feedback

#### Traditionel vs Agil

| Traditionel | Agil |
|---|---|
| Lange projekter (6-12 mdr) | Korte sprints (2-4 uger) |
| Alt planlægges på forhånd | Tilpasses løbende |
| Få store leverancer | Mange små leverancer |
| Tester til sidst | Tester løbende |
| Dokumentation-fokus | Fungerende software-fokus |

---

### Slide: Agile roller

#### Kerneteamet

- **Product Owner (PO)**: Ansvarlig for produktvision og prioritering
  - Definerer *hvad* der skal bygges og *hvorfor*
  - Prioriterer backlog baseret på forretningsværdi
  - Er stemmen fra kunden/brugeren

- **Scrum Master/Agile Coach**: Faciliterer teamets arbejde
  - Sikrer at teamet følger agile praksis
  - Fjerner forhindringer
  - Faciliterer møder og retrospektiver

- **Udviklere**: Leverer funktionalitet
  - Designer og implementerer brugergrænseflader (frontend)
  - Bygger forretningslogik og API'er (backend)
  - Opretter integrationer mellem systemer
  - Skriver tests og sikrer kvalitet
  - Deployer til produktion
  - Sikrer teknisk sammenhæng i løsningen

---

### Slide: Artifacts – Hvad arbejder vi med?

#### De tre centrale artifacts

- **Product Backlog**: Liste af alt der skal bygges
  - Prioriteret af Product Owner
  - Ændres løbende baseret på feedback og nye behov
  - Toppen af backlog er mest detaljeret

- **Sprint Backlog**: Hvad teamet arbejder på lige nu
  - Udvalgte opgaver fra Product Backlog
  - Gælder for nuværende sprint (2-4 uger)
  - Teamet ejer planen

- **Increment**: Fungerende software ved slutningen af hver sprint
  - Skal være klar til at gå i produktion
  - Bygger ovenpå tidligere increments
  - Konkret værdi som kan vises til brugere

---

## 📋 Leverancer efter dagen (Conscia)

Inden for 1–3 arbejdsdage samles og deles:

- Opdaterede workflow-skemaer med UX-perspektiv
- Oversigt over datakrav på tværs af workflows
- Anbefaling til teamorganisering baseret på workflows
- Forslag til første sprint og prioritering

---

## 🤖 Brug AI til at transformere workflows til UX

### Trin 1: Hent workflow fra Teams Planner

1. Åbn dit workflow i Teams Planner (fra Workshop 1)
2. Kopier indholdet fra noter feltet

### Trin 2: Download materialer

Download UX-eksempler og skabelon fra repo

### Trin 3: Upload til Copilot

Åbn Copilot og træk materialer ind i chatten:

- [workflow-ux-1-vlan-provisionering.md](eksempler/workflow-ux-1-vlan-provisionering.md)
- [workflow-ux-2-firewall-regel.md](eksempler/workflow-ux-2-firewall-regel.md)
- [workflow-skema-ux.md](skabeloner/workflow-skema-ux.md)
- Dit kopierede workflow fra Teams Planner

### Trin 4: Prompt Copilot

Skriv en prompt ala:

```
Transformer mit workflow fra arkitektur-perspektiv til UX-perspektiv.
Brug workflow-skema-ux.md som skabelon.
Fokuser på brugerrejsen: hvad brugeren ser, kan vælge, gør, og hvilken feedback de får.

Mit workflow:
[indsæt dit workflow fra Teams Planner]
```

### Trin 5: Forfin med Copilot

Stil opfølgende spørgsmål:

```
- Hvad mangler der af feedback til brugeren?
- Hvilke data skal vises i hvert trin?
- Er der trin i brugerrejsen vi har glemt?
```

### Trin 6: Eksporter resultatet

Når I er færdig, så prompt:

```
Output som en markdown md fil
```

### Trin 7: Gem i Teams Planner

1. Download markdown filen
2. Opdater dit workflow i Teams Planner med det nye UX-fokuserede indhold
3. Tilføj label "UX" til opgaven

---

## 📝 Skabeloner

- [Skabelon: Workflow-skema UX](skabeloner/workflow-skema-ux.md)
