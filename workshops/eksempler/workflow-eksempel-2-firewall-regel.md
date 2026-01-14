# Eksempel: Workflow-skema – Firewall regelændring

## Workflow-navn

Firewall regel til ny applikationsintegration

## Formål

Oprette/ændre en firewall-regel mellem to zoner med sporbarhed, godkendelse og sikker verifikation.

## Start

Bestilling via API: "Åbn TCP 443 fra App A til API B".

## Udføres af

Automatisering (med godkendelse fra security team)

## Mål og færdig

Regel er implementeret på korrekt firewall/policy-set, change er dokumenteret, og trafik er verificeret (eller bekræftet via logs).

## Infrastrukturændring

Ny firewall policy-regel (source/destination/service) + evt. NAT.

## Systemer og integrationer

1. Orchestrator

    - Input: Bestilling via API med source, destination, service, zones og expiry
    - Output: Change request til firewall manager og reference id

2. Firewall manager

    - Input: Rule draft, approver og change reference
    - Output: Deploy status, rule id og audit log

3. Logging/SIEM

    - Input: Rule id, tidsvindue, source og destination
    - Output: Log-hit eller verifikationsresultat

## Trin (oversigt)

1. Valider bestilling: zones, kilde/destination, port/protokol, tidsbegrænsning.
1. Slå policy-opslag op: hvor skal reglen ligge.
1. Opret change: rule draft + godkendelse.
1. Deploy og verificer.
1. Dokumenter og luk.

## Fejl/rollback

Rollback ved at disable/restore change-set i firewall manager.

## Åbne spørgsmål/risici

- Hvad er minimumskrav til godkendelse: security-only eller også netværk?
- Skal regler have automatisk udløb (expiry) som standard?
