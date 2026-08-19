---
title: LayerManager — Administrer Alle Lag i Én Tabell
description: LayerManager-kommandoen åpner en tabell over alle lag i tegningen, slik at du kan legge til lag og redigere direkte for hvert lag frysing, låsing, plot, farge, linjetykkelse og linetype.
keywords: [layer manager, CAD lagtabell, administrer lag CAD, legg til lag CAD, frys lås plot lag, kulmanlab lagadministrasjon]
group: layer
order: 1
---

# LayerManager

Kommandoen `LayerManager` åpner en tabell som viser alle lag i tegningen, med innstillingene **Freeze** (frys), **Lock** (lås), **Plot**, **Farge**, **Linjetykkelse** og **Linetype** redigerbare direkte i raden. Det er det sentrale stedet for å legge til nye lag og justere hvordan eksisterende lag oppfører seg — de andre lagkommandoene ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) gjør hver sin fokuserte oppgave uten å åpne den.

## Åpne Layer Manager

- Skriv `LayerManager` i terminalen, **eller**
- Klikk på **Layer Manager**-knappen i lagpanelet.

Dialogen åpnes som et flytende panel; ingenting trenger å være markert på forhånd.

## Lagtabellen

| Kolonne | Hva den styrer |
|---------|-------------------|
| Name | Lagets navn, vist skrivebeskyttet i tabellen (angitt én gang, ved opprettelse) |
| Freeze | Skjuler lagets entiteter og utelukker dem fra markering til det fjernes frysing |
| Lock | Hindrer redigering av entiteter på laget, uten å skjule dem |
| Plot | Om lagets entiteter inkluderes ved utskrift eller PDF-eksport |
| Color | Lagets ACI-farge — klikk på fargeprøven for å åpne fargevelgeren |
| Lineweight | Lagets linjetykkelse — klikk på chippen for å åpne linjetykkelsevelgeren |
| Linetype | Lagets strekmønster — klikk på chippen for å åpne linetype-velgeren |

Å slå av/på Freeze, Lock eller Plot har umiddelbar effekt — det er ikke noe eget lagringssteg. Entiteter satt til **ByLayer** for farge, linjetykkelse eller linetype (standardverdien) følger det du angir her; entiteter med sin egen eksplisitte overstyring påvirkes ikke.

## Legge til et lag

1. Klikk på **+ Add Layer** nederst i tabellen.
2. Skriv et navn og trykk **Enter** for å bekrefte, eller **Escape** for å avbryte.

Lagnavn kan inneholde bokstaver, tall, mellomrom og `_`, `-`, `$`. Et navn som er tomt, allerede i bruk, eller inneholder et annet tegn, avvises med en innebygd feilmelding, og raden forblir åpen for et nytt forsøk.

Nye lag starter som **ufrosne, ulåste, plottbare**, med farge 7 (hvit/svart), linjetykkelse Default og linetype Continuous — de samme standardverdiene som [Import](../import/) tildeler lag `0` i en tom tegning.

## Hva du ikke kan gjøre her

Det finnes ingen slett-knapp — lag fjernes aldri etter at de er opprettet, de kan bare fryses eller etterlates ubrukt. Tabellen viser heller ikke hvilket lag som er *gjeldende*; det angis via nedtrekksmenyen i lagpanelet eller via [LayerMakeCurrent](../layer-make-current/), ikke fra denne dialogen.

## Tastaturreferanse

| Tast | Handling |
|------|----------|
| `Enter` | Bekreft navnet på et nytt lag (mens du legger til) |
| `Escape` | Avbryt tillegg av et lag, eller lukk dialogen |

## Relaterte kommandoer

| Kommando | Hva den gjør |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Sett gjeldende lag til å samsvare med en klikket entitets lag |
| [LayerMatch](../layer-match/) | Tildel markerte entiteter på nytt til laget for en kildeentitet |
| [LayerIsolate](../layer-isolate/) | Frys alle lag unntatt de markerte entitetenes |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Fjern frysing av alle lag i ett steg |
