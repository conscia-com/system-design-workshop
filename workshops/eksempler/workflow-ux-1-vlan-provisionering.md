# Eksempel: Workflow-skema (UX) – VLAN provisioning

## Trin 1: Udfyld bestilling

**Du ser**: En formular til at bestille VLAN med felter for:

- System navn
- Zone/miljø (dropdown: Produktion, Test, Development)
- VRF (dropdown med tilgængelige VRF'er)
- Site/datacenter (dropdown)
- Forventet antal hosts
- Begrundelse for anmodning

**Du kan vælge**:

- Hvilken zone/miljø (Produktion, Test, Development)
- Hvilket VRF (fra listen af tilgængelige)
- Hvilket site/datacenter
- Antal hosts
- Gemme som kladde eller sende bestillingen

**Du gør**: Udfylder formularen og klikker "Send bestilling"

**Der sker**:

- **Undervejs**: Spinner vises "Sender bestilling..."
- **Ved success**: "Bestilling sendt! Reference: REQ-2024-1234" og du sendes til status-siden
- **Ved fejl**: "Fejl: [årsag]. Prøv igen eller kontakt support."

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Tilgængelige zoner/VRF'er | IPAM | Real-time, kun hvad du har adgang til | Nej |
| Tilgængelige sites | CMDB | Opdateret dagligt minimum | Nej |
| Din brugerinfo | AD/Identity | Real-time | Ja (i bestilling) |
| Bestillingsdata | Frontend formular | Valideret | Ja (Orchestrator DB) |

---

## Trin 2: Følg status

**Du ser**: Status-dashboard med:

- Reference-nummer øverst
- Fremskridtsindikator med trin:
  1. VLAN-ID reserveres ⏳
  2. Konfiguration til switche ⏱️
  3. Verificering ⏱️
  4. Færdig ⏱️
- Email-notifikation besked: "Du får besked når VLAN er klar"

**Du kan vælge**:

- Opdatere siden for at se fremskridt
- Gå tilbage til forsiden
- Se dine andre bestillinger

**Du gør**: Venter og ser status opdateres automatisk eller opdaterer siden

**Der sker**:

- **Undervejs**:
  - "VLAN-ID reserveres..." → grøn checkmark når færdig
  - "Konfiguration pushes til switche..." → progress bar
  - "Verificering..." → grøn checkmark når færdig
- **Ved success**: Alle trin er grønne, "VLAN oprettet!" vises
- **Ved fejl**: Rød fejlbesked med årsag og rollback-info

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Status på bestilling | Orchestrator | Real-time opdatering | Ja (historik) |
| Fremskridtstrin | Orchestrator workflow engine | Real-time | Ja (log) |

---

## Trin 3: Se resultat

**Du ser**: Resultat-side med:

- "VLAN oprettet! ✅"
- VLAN-ID: 234
- Subnet: 10.20.30.0/24
- Status: Aktiv
- Download-knap: "Download konfigurationsdetaljer"
- Link: "Se i CMDB"

**Du kan vælge**:

- Downloade konfigurationsdetaljer som PDF/tekstfil
- Åbne VLAN i CMDB
- Bestille endnu et VLAN
- Gå til forsiden

**Du gør**: Downloader konfigurationsdetaljer og/eller tjekker CMDB

**Der sker**:

- **Ved download**: PDF/tekstfil downloades med alle detaljer
- **Ved CMDB-link**: CMDB åbnes i nyt vindue med VLAN-dokumentation
- **Ved fejl**: "Kunne ikke hente detaljer, kontakt netværksteam"

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Tildelt VLAN-ID | IPAM | Garanteret reserveret | Ja (IPAM) |
| Tildelt subnet | IPAM | Garanteret reserveret | Ja (IPAM) |
| Verification resultater | Switch read-back | Real-time fra enhed | Ja (log) |
| CMDB-reference | CMDB | Persistent link | Ja (CMDB) |
| Konfigurationsdetaljer | Orchestrator + IPAM + CMDB | Samlet rapport | Ja (dokumentation) |

---

## Succeskriterium

Brugeren kan se:

- VLAN-ID og subnet er tildelt
- Status er "Aktiv"
- Verification-test er kørt og gennemført
- VLAN fremgår i CMDB med korrekte relationer
- Konfigurationsdetaljer kan downloades
