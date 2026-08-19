---
title: LayerManager — Beheer Alle Lagen in Eén Tabel
description: Het LayerManager-commando opent een tabel met alle lagen van de tekening, waarmee u lagen kunt toevoegen en voor elke laag rechtstreeks bevriezing, vergrendeling, plot, kleur, lijndikte en lijntype kunt bewerken.
keywords: [layer manager, laagtabel CAD, lagen beheren CAD, laag toevoegen CAD, bevriezen vergrendelen plotten laag, kulmanlab laagbeheer]
group: layer
order: 1
---

# LayerManager

Het `LayerManager`-commando opent een tabel met alle lagen van de tekening, waarbij **Freeze** (bevriezen), **Lock** (vergrendelen), **Plot**, **Kleur**, **Lijndikte** en **Lijntype** rechtstreeks in de rij bewerkbaar zijn. Het is de centrale plek om nieuwe lagen toe te voegen en het gedrag van bestaande lagen aan te passen — de overige laagcommando's ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) doen elk één gerichte taak zonder dit dialoogvenster te openen.

## De Layer Manager openen

- Typ `LayerManager` in de terminal, **of**
- Klik op de knop **Layer Manager** in het lagenpaneel.

Het dialoogvenster opent als een zwevend paneel; er hoeft vooraf niets geselecteerd te zijn.

## De lagentabel

| Kolom | Wat het bestuurt |
|-------|---------------------|
| Name | De naam van de laag, alleen-lezen weergegeven in de tabel (eenmalig ingesteld bij het aanmaken) |
| Freeze | Verbergt de entiteiten van de laag en sluit ze uit van selectie tot ze wordt ontdooid |
| Lock | Voorkomt dat entiteiten op de laag worden bewerkt, zonder ze te verbergen |
| Plot | Of de entiteiten van de laag worden opgenomen bij afdrukken of exporteren naar PDF |
| Color | De ACI-kleur van de laag — klik op het kleurvlak om de kleurkiezer te openen |
| Lineweight | De lijndikte van de laag — klik op de chip om de lijndiktekiezer te openen |
| Linetype | Het streepjespatroon van de laag — klik op de chip om de lijntypekiezer te openen |

Freeze, Lock of Plot omschakelen heeft direct effect — er is geen aparte opslagstap. Entiteiten die voor kleur, lijndikte of lijntype op **ByLayer** staan (de standaardinstelling) nemen over wat u hier instelt; entiteiten met een eigen expliciete overschrijving worden niet beïnvloed.

## Een laag toevoegen

1. Klik op **+ Add Layer** onderaan de tabel.
2. Typ een naam en druk op **Enter** om te bevestigen, of **Escape** om te annuleren.

Laagnamen mogen letters, cijfers, spaties en `_`, `-`, `$` bevatten. Een lege naam, een naam die al in gebruik is, of een naam met een ander teken wordt afgewezen met een inline foutmelding, en de rij blijft open voor een nieuwe poging.

Nieuwe lagen starten **ontdooid, ontgrendeld, plotbaar**, met kleur 7 (wit/zwart), lijndikte Default en lijntype Continuous — dezelfde standaardwaarden die [Import](../import/) toekent aan laag `0` in een lege tekening.

## Wat u hier niet kunt doen

Er is geen verwijderknop — lagen worden nooit verwijderd nadat ze zijn aangemaakt, alleen bevroren of ongebruikt gelaten. De tabel geeft ook niet aan welke laag de *huidige* is; dat wordt ingesteld via de vervolgkeuzelijst in het lagenpaneel of via [LayerMakeCurrent](../layer-make-current/), niet vanuit dit dialoogvenster.

## Toetsenbordreferentie

| Toets | Actie |
|-------|-------|
| `Enter` | Bevestig de naam van een nieuwe laag (tijdens het toevoegen) |
| `Escape` | Annuleer het toevoegen van een laag, of sluit het dialoogvenster |

## Gerelateerde commando's

| Commando | Wat het doet |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Stel de huidige laag in op de laag van een aangeklikte entiteit |
| [LayerMatch](../layer-match/) | Wijs geselecteerde entiteiten opnieuw toe aan de laag van een bronentiteit |
| [LayerIsolate](../layer-isolate/) | Bevries alle lagen behalve die van de geselecteerde entiteiten |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Ontdooi alle lagen in één stap |
