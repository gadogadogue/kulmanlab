---
title: LayerManager — Hantera alla lager i en enda tabell
description: LayerManager-kommandot öppnar en tabell med alla lager i ritningen, där du kan lägga till lager och redigera direkt för varje lager dess frysning, låsning, plot, färg, linjebredd och linjetyp.
keywords: [layer manager, CAD lagertabell, hantera lager CAD, lägg till lager CAD, frys lås plotta lager, kulmanlab lagerhantering]
group: layer
order: 1
---

# LayerManager

`LayerManager`-kommandot öppnar en tabell som listar alla lager i ritningen, med inställningarna **Freeze** (frys), **Lock** (lås), **Plot**, **Färg**, **Linjebredd** och **Linjetyp** redigerbara direkt i raden. Det är den centrala platsen för att lägga till nya lager och justera hur befintliga beter sig — de övriga lagerkommandona ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) gör var och en en enda fokuserad sak utan att öppna det.

## Öppna Layer Manager

- Skriv `LayerManager` i terminalen, **eller**
- Klicka på knappen **Layer Manager** i lagerpanelen.

Dialogrutan öppnas som en flytande panel; inget behöver vara markerat i förväg.

## Lagertabellen

| Kolumn | Vad den styr |
|--------|----------------|
| Name | Lagrets namn, visas skrivskyddat i tabellen (anges en gång, vid skapandet) |
| Freeze | Döljer lagrets entiteter och utesluter dem från markering tills det fryses upp |
| Lock | Förhindrar redigering av entiteter på lagret, utan att dölja dem |
| Plot | Om lagrets entiteter inkluderas vid utskrift eller PDF-export |
| Color | Lagrets ACI-färg — klicka på färgrutan för att öppna färgväljaren |
| Lineweight | Lagrets linjebredd — klicka på chippen för att öppna linjebreddsväljaren |
| Linetype | Lagrets streckmönster — klicka på chippen för att öppna linjetypsväljaren |

Att slå på/av Freeze, Lock eller Plot får omedelbar effekt — det finns inget separat sparsteg. Entiteter som är satta till **ByLayer** för färg, linjebredd eller linjetyp (standardvärdet) följer det du ställer in här; entiteter med en egen explicit override påverkas inte.

## Lägga till ett lager

1. Klicka på **+ Add Layer** längst ner i tabellen.
2. Skriv ett namn och tryck på **Enter** för att bekräfta, eller **Escape** för att avbryta.

Lagernamn får innehålla bokstäver, siffror, mellanslag samt `_`, `-`, `$`. Ett namn som är tomt, redan används, eller innehåller något annat tecken avvisas med ett infogat felmeddelande, och raden förblir öppen för ett nytt försök.

Nya lager börjar som **ofrysta, olåsta, plottbara**, med färg 7 (vit/svart), linjebredd Default och linjetyp Continuous — samma standardvärden som [Import](../import/) tilldelar lager `0` i en tom ritning.

## Vad du inte kan göra här

Det finns ingen raderaknapp — lager tas aldrig bort efter att de skapats, de kan bara frysas eller lämnas oanvända. Tabellen visar inte heller vilket lager som är *aktuellt*; det ställs in via rullgardinsmenyn i lagerpanelen eller via [LayerMakeCurrent](../layer-make-current/), inte från denna dialogruta.

## Snabbreferens tangentbord

| Tangent | Åtgärd |
|---------|--------|
| `Enter` | Bekräfta namnet på ett nytt lager (medan du lägger till) |
| `Escape` | Avbryt att lägga till ett lager, eller stäng dialogrutan |

## Relaterade kommandon

| Kommando | Vad det gör |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Ställ in det aktuella lagret till samma lager som en klickad entitet |
| [LayerMatch](../layer-match/) | Omtilldela markerade entiteter till lagret för en källentitet |
| [LayerIsolate](../layer-isolate/) | Frys alla lager utom de för de markerade entiteterna |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Frys upp alla lager i ett steg |
