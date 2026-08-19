---
title: LayerManager — Administrer Alle Lag i Én Tabel
description: LayerManager-kommandoen åbner en tabel over alle lag i tegningen, så du kan tilføje lag og redigere direkte for hvert lag frysning, låsning, plot, farve, linjetykkelse og linjetype.
keywords: [layer manager, CAD lagtabel, administrer lag CAD, tilføj lag CAD, frys lås plot lag, kulmanlab lagadministration]
group: layer
order: 1
---

# LayerManager

Kommandoen `LayerManager` åbner en tabel, der viser alle lag i tegningen, med indstillingerne **Freeze** (frys), **Lock** (lås), **Plot**, **Farve**, **Linjetykkelse** og **Linjetype** redigerbare direkte i rækken. Det er det centrale sted til at tilføje nye lag og justere, hvordan eksisterende lag opfører sig — de øvrige lagkommandoer ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) udfører hver især én fokuseret opgave uden at åbne den.

## Åbne Layer Manager

- Skriv `LayerManager` i terminalen, **eller**
- Klik på knappen **Layer Manager** i lagpanelet.

Dialogen åbner som et flydende panel; intet behøver at være markeret på forhånd.

## Lagtabellen

| Kolonne | Hvad den styrer |
|---------|--------------------|
| Name | Lagets navn, vist som skrivebeskyttet i tabellen (angivet én gang, ved oprettelse) |
| Freeze | Skjuler lagets entiteter og udelukker dem fra markering, indtil det ophæves |
| Lock | Forhindrer redigering af entiteter på laget, uden at skjule dem |
| Plot | Om lagets entiteter medtages ved udskrivning eller PDF-eksport |
| Color | Lagets ACI-farve — klik på farveprøven for at åbne farvevælgeren |
| Lineweight | Lagets linjetykkelse — klik på chippen for at åbne tykkelsesvælgeren |
| Linetype | Lagets stregmønster — klik på chippen for at åbne linjetypevælgeren |

At slå Freeze, Lock eller Plot til/fra virker med det samme — der er intet separat gemme-trin. Entiteter, der er sat til **ByLayer** for farve, linjetykkelse eller linjetype (standardværdien), følger det, du angiver her; entiteter med deres egen eksplicitte tilsidesættelse påvirkes ikke.

## Tilføje et lag

1. Klik på **+ Add Layer** nederst i tabellen.
2. Skriv et navn, og tryk på **Enter** for at bekræfte, eller **Escape** for at annullere.

Lagnavne må indeholde bogstaver, tal, mellemrum samt `_`, `-`, `$`. Et navn, der er tomt, allerede i brug, eller indeholder et andet tegn, afvises med en indbygget fejlmeddelelse, og rækken forbliver åben til endnu et forsøg.

Nye lag starter som **ufrosne, ulåste, plotbare**, med farve 7 (hvid/sort), linjetykkelse Default og linjetype Continuous — de samme standardværdier, som [Import](../import/) tildeler lag `0` i en tom tegning.

## Hvad du ikke kan gøre her

Der er ingen slet-knap — lag fjernes aldrig, når de er oprettet, de kan kun fryses eller efterlades ubrugte. Tabellen viser heller ikke, hvilket lag der er det *aktuelle*; det angives via rullelisten i lagpanelet eller via [LayerMakeCurrent](../layer-make-current/), ikke fra denne dialog.

## Tastaturreference

| Tast | Handling |
|------|----------|
| `Enter` | Bekræft navnet på et nyt lag (mens du tilføjer) |
| `Escape` | Annullér tilføjelse af et lag, eller luk dialogen |

## Relaterede kommandoer

| Kommando | Hvad den gør |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Sæt aktuelt lag til at matche en klikket entitets lag |
| [LayerMatch](../layer-match/) | Tildel markerede entiteter på ny til laget for en kildeentitet |
| [LayerIsolate](../layer-isolate/) | Frys alle lag undtagen de markerede entiteters |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Fjern frysning af alle lag i ét trin |
