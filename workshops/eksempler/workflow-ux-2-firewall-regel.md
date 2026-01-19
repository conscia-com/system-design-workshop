# Eksempel: Workflow-skema (UX) – Firewall regelændring

## Trin 1: Anmod om regel

**Du ser**: En formular til at anmode om firewall-regel med:

- Source system/IP (dropdown eller søgefelt)
- Destination system/IP (dropdown eller søgefelt)
- Service/port (dropdown: HTTP, HTTPS, SSH, Custom...)
- Begrundelse (tekstfelt - påkrævet)
- Udløbsdato (datovælger - valgfri, standard: 90 dage)

**Du kan vælge**:

- Vælge source og destination fra liste eller søge
- Vælge en standard service eller indtaste custom port
- Sætte udløbsdato eller bruge standard
- Gemme som kladde eller sende anmodning

**Du gør**: Udfylder formularen og klikker "Send anmodning"

**Der sker**:

- **Undervejs**: Spinner vises "Sender anmodning..."
- **Ved success**: "Anmodning sendt til godkendelse! Reference: FW-REQ-2024-5678"
- **Ved fejl**: "Fejl: [årsag]. Tjek dine valg og prøv igen."

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Tilgængelige systemer | CMDB | Opdateret dagligt, inkl. IP-adresser | Nej |
| Common services | Firewall manager | Statisk liste | Nej |
| Zone-mapping | CMDB | Real-time, korrekt zone tildeling | Nej |
| Din brugerinfo | AD/Identity | Real-time | Ja (anmodning) |
| Anmodningsdata | Frontend formular | Valideret | Ja (Orchestrator DB) |

---

## Trin 2: Vent på godkendelse

**Du ser**: Godkendelses-dashboard med:

- Reference-nummer: FW-REQ-2024-5678
- Status: "Venter på godkendelse"
- Godkender: "Security team (Morten Jensen)"
- Tidsstempel: "Sendt 19. jan 2026 10:45"
- Din begrundelse vises
- Knap: "Træk anmodning tilbage"

**Du kan vælge**:

- Opdatere siden for at se status
- Trække anmodningen tilbage
- Se dine andre anmodninger
- Få notifikation når godkendt

**Du gør**: Venter på godkendelse (får email når der sker noget)

**Der sker**:

- **Undervejs**: "Venter på godkendelse hos Morten Jensen..."
- **Ved godkendelse**: "✅ Godkendt af security team! Regel deployes nu..."
- **Ved afvisning**: "❌ Afvist af security: [begrundelse]" + mulighed for at redigere og genindsende

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Godkendere i security team | AD/Identity system | Real-time, kun aktive brugere | Nej |
| Status på godkendelse | Orchestrator | Real-time | Ja (workflow log) |
| Godkendelsesflow | Orchestrator workflow engine | Real-time | Ja (audit trail) |

---

## Trin 3: Se deployment

**Du ser**: Deployment-status med:

- "Regel deployes til firewall..." med progress bar
- "Verificering af trafik..."
- Real-time log:
  - 10:52: Policy opdateres på firewall
  - 10:53: Regel aktiveret
  - 10:54: Trafik verificeres i logs

**Du kan vælge**:

- Se detaljeret log
- Opdatere status
- Notifikation når færdig

**Du gør**: Følger deployment i real-time

**Der sker**:

- **Undervejs**: Progress bar og real-time log-opdateringer
- **Ved success**: "✅ Regel aktiveret og verificeret!"
- **Ved fejl**: "❌ Deploy fejlede: [årsag] - rollback gennemført" + kontaktinfo

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Deployment status | Firewall manager | Real-time | Ja (log) |
| Verification logs | SIEM/Logging | Senest 5 min gamle | Ja (arkiv) |

---

## Trin 4: Se resultat

**Du ser**: Resultat-side med:

- "✅ Regel aktiveret!"
- Rule ID: FW-2024-1234
- Status: Aktiv
- Trafik verificeret: Ja (3 connections i logs)
- Udløber: 19. april 2026
- Download-knap: "Download regeldetaljer"
- Link: "Se i firewall manager"
- Knap: "Forlæng udløbsdato"

**Du kan vælge**:

- Downloade regeldetaljer
- Se regel i firewall manager
- Forlænge udløbsdato
- Oprette lignende regel
- Gå til forsiden

**Du gør**: Downloader regeldetaljer til dokumentation

**Der sker**:

- **Ved download**: PDF/tekstfil med alle regeldetaljer
- **Ved forlængelse**: Modal åbnes hvor du kan vælge ny dato
- **Ved fejl**: "Kunne ikke hente detaljer, kontakt security team"

**Hvor kommer data fra**:

| Data | Kommer fra | Skal være | Gemmes |
|---|---|---|---|
| Rule ID | Firewall manager | Persistent | Ja (firewall) |
| Verification logs | SIEM/Logging | Real-time hits | Ja (arkiv) |
| Udløbsdato | Firewall manager | Automatisk cleanup | Ja (scheduler) |
| Eksisterende regler | Firewall manager | Real-time, relaterede regler | Nej |
| Change reference | CMDB | Link til change | Ja (CMDB) |

---

## Succeskriterium

Brugeren kan se:

- Regel status er "Aktiv"
- Verification viser at trafik flyder (connection hits i logs)
- Rule ID er tildelt
- Regel fremgår i firewall manager
- Udløbsdato er sat
