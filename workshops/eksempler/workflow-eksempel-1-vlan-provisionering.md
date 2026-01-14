# Eksempel: Workflow-skema – VLAN provisioning

## Workflow-navn

VLAN provisioning til ny zone

## Formål

Oprette en ny VLAN i det rigtige netværksdomæne og få den aktiv på relevante switche med korrekt segmentering og dokumentation.

## Start

Bestilling i frontend: "Ny VLAN til system X".

## Udføres af

Netværksteam + automatisering (med godkendelse fra netværksansvarlig)

## Mål og færdig

VLAN-ID/subnet er reserveret, konfig er lagt på relevante switche, routing/ACL er på plads, og ændringen er registreret i IPAM/CMDB.

## Infrastrukturændring

Ny VLAN + tilknytning til zone/VRF + trunk/access konfiguration på udvalgte switche.

## Systemer og integrationer

1. Frontend

    - Input: Bestilling fra bruger
    - Output: Bestilling til orkestrator med zone, VRF, site og VLAN-navn

2. Orchestrator

    - Input: Bestilling fra frontend
    - Output: Kald til IPAM, netværksudstyr og CMDB samt samlet status

3. IPAM

    - Input: Request om reservation af VLAN-ID og subnet
    - Output: Reserveret VLAN-ID og subnet

4. Switches

    - Input: VLAN, trunk/access og interface-liste
    - Output: Status for konfig og read-back til verifikation

5. CMDB

    - Input: VLAN, subnet, relationer og change reference
    - Output: Opdateret registrering

## Trin (oversigt)

1. Modtag bestilling og valider zone/VRF og scope.
1. Slå op i IPAM, reserver VLAN-ID og subnet.
1. Push konfiguration til switche (VLAN + trunk/access).
1. Verificer (read-back + basic connectivity).
1. Opdater CMDB/IPAM og afslut opgaven.

## Fejl/rollback

Hvis push fejler: rollback til sidste kendte config på berørte enheder og frigiv reservation i IPAM hvis den ikke skal bruges.

## Åbne spørgsmål/risici

- Hvilken kilde er "source of truth" for zone/VRF: IPAM eller CMDB?
- Hvem godkender ændringer i segmenteringspolitik for nye VLANs?
