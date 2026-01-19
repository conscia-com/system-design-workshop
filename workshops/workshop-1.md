# Workshop 1 (heldag) – Workflows til arkitektur

## Målsætning

Dagen bruges på at få de vigtigste workflows beskrevet ensartet, så de kan bruges direkte som input til systemarkitektur.

## Output

- 1 udfyldt workflow-skema pr. workflow
- Liste over systemer og integrationer der går igen på tværs af workflows

---

## Dagsagenda (09:00–15:30)

|Tid|Punkt|
|---|---|
|09:00–09:15|Opstart|
|09:15–10:30|Workflows runde 1 – Brainstorming|
|10:30–10:45|Pause|
|10:45–12:00|Workflows runde 2 – Uddybning|
|12:00–12:45|Frokost|
|12:45–14:15|Workflows runde 3 – Prioritering|
|14:15–14:30|Pause|
|14:30–15:15|Systemer, integrationer og afhængigheder|
|15:15–15:30|Afrunding|

---

## Slides til gennemgang

### Slide: Opstart

#### Sådan gør vi i dag

- Runde 1: Brainstorming i Teams Planner, hver for sig
- Runde 2: Uddybning i makkerpar med workflow-skemaet
- Runde 3: Prioritering og færdiggørelse af de vigtigste workflows
- Snakke der tager for lang tid parkerer vi

#### Det vi skal have pr. workflow

- Workflow-navn
- Formål
- Start
- Udføres af
- Mål og færdig
- Infrastrukturændring
- Systemer og integrationer i rækkefølge med input/output pr. system
- Trin (oversigt)
- Fejl/rollback
- Åbne spørgsmål/risici
- Skabelon: [Workflow-skema](skabeloner/workflow-skema-arkitektur.md)

---

### Slide: Workflows runde 1 – Brainstorming

- Vi får så mange workflows på bordet som muligt
- Vi skriver workflows ind i Teams Planner som opgaver
- Én opgave pr. workflow
- Stop når vi begynder at gentage os

---

### Slide: Workflows runde 2 – Uddybning

- Vi arbejder i makkerpar
- Hvert par tager ét workflow ad gangen og udfylder workflow-skemaet
- Udfyld kun det der er sikkert
- Brug én linje pr. punkt
- Skabelon: [Workflow-skema](skabeloner/workflow-skema-arkitektur.md)

---

### Slide: Workflows runde 3 – Prioritering

- Vi vælger de vigtigste workflows at gøre færdige
- Vi sikrer at formål, udføres af, systemrækkefølge og input/output er tydeligt
- Åbne spørgsmål skrives under Åbne spørgsmål/risici
- Skabelon: [Workflow-skema](skabeloner/workflow-skema-arkitektur.md)

---

### Slide: Systemer og integrationer

#### Lav en kort liste

- Skriv de systemer og integrationer der går igen
- Notér kun det nødvendige for at kunne tegne arkitektur
- Skabelon: [Workflow-skema](skabeloner/workflow-skema-arkitektur.md)

---

## Leverancer efter dagen (Conscia)

Inden for 1–3 arbejdsdage samles og deles:

- Samlet oversigt over udfyldte workflow-skemaer
- Samlet liste over systemer og integrationer

---

## 🤖 Brug AI til at lave workflows

### Trin 1: Download materialer

Download eksempler og skabelon fra repo

### Trin 2: Upload til Copilot

Åbn Copilot og træk eksempler og skabelon ind i chatten:

- [workflow-ark-1-vlan-provisionering.md](eksempler/workflow-ark-1-vlan-provisionering.md)
- [workflow-ark-2-firewall-regel.md](eksempler/workflow-ark-2-firewall-regel.md)
- [workflow-skema-arkitektur.md](skabeloner/workflow-skema-arkitektur.md)

### Trin 3: Prompt Copilot

Skriv en prompt ala:

```
Udfyld workflow-skema-arkitektur.md med indholdet: [beskriv dit workflow]
```

### Trin 4: Eksporter resultatet

Når I er færdig med at rette i indholdet med Copilot, så prompt:

```
Output som en markdown md fil
```

### Trin 5: Gem i Teams Planner

1. Download markdown filen
2. Gå ind i Teams Planner og vælg **"Tilføj opgave"** med workflow overskrift
3. Åbn opgaven og kopier md-fil indholdet ind i noter feltet

---

## Skabeloner

- [Skabelon: Workflow-skema (arkitektur)](skabeloner/workflow-skema-arkitektur.md)

## Til næste gang

1. Workflows skal refineres færdig og manglende workflows skal tilføjes til MVP
2. Arkitekturdiagrammer med de integrationspunkter i scope
