---
title: New File — Start en Tom Tegning i KulmanLab CAD
description: New File-kommandoen tømmer lerretet og åpner en ny, tom tegning. Et enkelt filnavn genereres automatisk og lagres i nettleserlagring.
keywords: [ny CAD-fil, ny tegning, tomt lerret CAD, opprett ny tegning online, start ny DXF, KulmanLab ny fil, tilbakestill lerret, tøm tegning]
group: file
order: 2
---

# New File

Kommandoen **New File** tømmer lerretet og starter en ny, tom tegning. Et unikt filnavn genereres automatisk.

## Slik oppretter du en ny fil

Klikk på **New File**-knappen (ny-side-ikon) i File-panelet. Lerretet tømmes umiddelbart — ingen ledetekster eller bekreftelsesdialoger.

## Hva den nye filen inneholder

En nyopprettet fil starter med:

- **Ingen entiteter** på lerretet.
- **Ett standardlag** kalt `0` med hvit farge og linetype `Continuous`.
- Et **generert filnavn**, `kulman.dxf` — eller `kulman (2).dxf`, `kulman (3).dxf`, … hvis det navnet allerede er i bruk.

Filen lagres automatisk i nettleserlagring, vises i [File Manager](../file-manager/), og kan [omdøpes](../file-manager/#omdøpe-en-fil) når som helst.

## Advarsel — ulagret arbeid forkastes

Å klikke på **New File** forkaster alle entiteter på gjeldende lerret uten advarsel. Hvis du vil beholde gjeldende tegning, [eksporter](../export-manager/) den først.

## Når du bør bruke New File vs Import

| Situasjon | Anbefalt handling |
|-----------|-------------------|
| Starte en tegning fra bunnen av | **New File** |
| Åpne en eksisterende DXF- eller JSON-fil | [Import](../import/) |
| Kopiere en tegning for å jobbe med en variant | [Eksporter](../export-manager/) gjeldende fil, [importer](../import/) deretter kopien |

## Relaterte kommandoer

- [Import](../import/) — åpne en eksisterende DXF- eller JSON-tegning
- [Export Manager](../export-manager/) — last ned tegningen før du starter på nytt
- [File Manager](../file-manager/) — gjenopprett en tidligere tegning fra nettleserlagring
