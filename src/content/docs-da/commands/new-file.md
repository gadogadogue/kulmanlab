---
title: New File — Start en Tom Tegning i KulmanLab CAD
description: New File-kommandoen tømmer lærredet og åbner en ny, tom tegning. Et tidsstemplet filnavn genereres automatisk og gemmes i browserlagring.
keywords: [ny CAD-fil, ny tegning, tomt lærred CAD, opret ny tegning online, start ny DXF, KulmanLab ny fil, nulstil lærred, ryd tegning]
group: file
order: 2
---

# New File

Kommandoen **New File** tømmer lærredet og starter en ny, tom tegning. Et unikt filnavn med et tidsstempel genereres automatisk.

## Sådan opretter du en ny fil

Klik på **New File**-knappen (ny-side-ikon) i File-panelet. Lærredet tømmes med det samme — ingen prompts eller bekræftelsesdialoger.

## Hvad den nye fil indeholder

En nyoprettet fil starter med:

- **Ingen entiteter** på lærredet.
- **Ét standardlag** kaldet `0` med hvid farve og linetype `Continuous`.
- Et **genereret filnavn**, `kulman.dxf` — eller `kulman (2).dxf`, `kulman (3).dxf`, … hvis det navn allerede er taget.

Filen gemmes automatisk i browserlagring og vises i [File Manager](../file-manager/), og kan [omdøbes](../file-manager/#omdøbning-af-en-fil) når som helst.

## Advarsel — ugemt arbejde kasseres

At klikke på **New File** kasserer alle entiteter på det aktuelle lærred uden advarsel. Hvis du vil beholde den aktuelle tegning, [eksportér](../export-manager/) den først.

## Hvornår du bør bruge New File vs Import

| Situation | Anbefalet handling |
|-----------|-------------------|
| Starte en tegning fra bunden | **New File** |
| Åbne en eksisterende DXF- eller JSON-fil | [Import](../import/) |
| Kopiere en tegning for at arbejde på en variant | [Eksportér](../export-manager/) den aktuelle fil, [importér](../import/) derefter kopien |

## Relaterede kommandoer

- [Import](../import/) — åbn en eksisterende DXF- eller JSON-tegning
- [Export Manager](../export-manager/) — download tegningen, før du starter forfra
- [File Manager](../file-manager/) — gendan en tidligere tegning fra browserlagring
