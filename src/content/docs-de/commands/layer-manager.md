---
title: LayerManager — Alle Layer in einer Tabelle verwalten
description: Der Befehl LayerManager öffnet eine Tabelle aller Layer der Zeichnung, in der Sie Layer hinzufügen und für jeden Layer Freeze, Lock, Plot, Farbe, Linienstärke und Linientyp direkt bearbeiten können.
keywords: [layer manager, CAD layer-tabelle, layer verwalten CAD, layer hinzufügen CAD, freeze lock plot layer, kulmanlab layerverwaltung]
group: layer
order: 1
---

# LayerManager

Der Befehl `LayerManager` öffnet eine Tabelle mit allen Layern der Zeichnung, in der **Freeze**, **Lock**, **Plot**, **Farbe**, **Linienstärke** und **Linientyp** direkt in der jeweiligen Zeile bearbeitet werden können. Es ist die zentrale Stelle, um neue Layer hinzuzufügen und das Verhalten bestehender Layer anzupassen — die übrigen Layer-Befehle ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) erledigen jeweils eine einzelne Aufgabe, ohne ihn zu öffnen.

## Den Layer Manager öffnen

- Geben Sie `LayerManager` im Terminal ein, **oder**
- Klicken Sie auf die Schaltfläche **Layer Manager** im Layer-Panel.

Der Dialog öffnet sich als schwebendes Panel; vorher muss nichts ausgewählt werden.

## Die Layer-Tabelle

| Spalte | Was sie steuert |
|--------|-------------------|
| Name | Der Name des Layers, in der Tabelle nur lesbar angezeigt (einmalig bei der Erstellung festgelegt) |
| Freeze | Blendet die Entitäten des Layers aus und schließt sie von der Auswahl aus, bis er wieder aufgetaut wird |
| Lock | Verhindert die Bearbeitung von Entitäten auf dem Layer, ohne sie auszublenden |
| Plot | Ob die Entitäten des Layers beim Drucken oder beim PDF-Export enthalten sind |
| Farbe | Die ACI-Farbe des Layers — klicken Sie auf die Farbfläche, um die Farbauswahl zu öffnen |
| Linienstärke | Die Linienstärke des Layers — klicken Sie auf den Chip, um die Linienstärkenauswahl zu öffnen |
| Linientyp | Das Strichmuster des Layers — klicken Sie auf den Chip, um die Linientypauswahl zu öffnen |

Das Umschalten von Freeze, Lock oder Plot wirkt sich sofort aus — es gibt keinen separaten Speicherschritt. Entitäten, die für Farbe, Linienstärke oder Linientyp auf **ByLayer** gesetzt sind (die Vorgabe), übernehmen, was Sie hier festlegen; Entitäten mit einer eigenen expliziten Überschreibung bleiben unberührt.

## Einen Layer hinzufügen

1. Klicken Sie unten in der Tabelle auf **+ Add Layer**.
2. Geben Sie einen Namen ein und drücken Sie **Enter** zur Bestätigung, oder **Escape** zum Abbrechen.

Layernamen dürfen Buchstaben, Zahlen, Leerzeichen sowie `_`, `-`, `$` enthalten. Ein leerer, bereits vergebener oder anderweitig ungültiger Name wird mit einer Inline-Fehlermeldung abgelehnt, und die Zeile bleibt für einen weiteren Versuch geöffnet.

Neue Layer starten **nicht eingefroren, nicht gesperrt, druckbar**, mit Farbe 7 (Weiß/Schwarz), Linienstärke Default und Linientyp Continuous — dieselben Vorgaben, die [Import](../import/) dem Layer `0` in einer leeren Zeichnung zuweist.

## Was hier nicht geht

Es gibt keine Löschschaltfläche — Layer werden nach dem Erstellen nie entfernt, sondern höchstens eingefroren oder ungenutzt gelassen. Ebenso zeigt die Tabelle nicht an, welcher Layer gerade der *aktuelle* ist; das wird über das Dropdown im Layer-Panel oder über [LayerMakeCurrent](../layer-make-current/) festgelegt, nicht über diesen Dialog.

## Tastaturkürzel

| Taste | Aktion |
|-------|--------|
| `Enter` | Den Namen eines neuen Layers bestätigen (während der Eingabe) |
| `Escape` | Das Hinzufügen eines Layers abbrechen, oder den Dialog schließen |

## Verwandte Befehle

| Befehl | Funktion |
|--------|----------|
| [LayerMakeCurrent](../layer-make-current/) | Aktuelle Ebene auf die Ebene des angeklickten Elements setzen |
| [LayerMatch](../layer-match/) | Ausgewählte Elemente der Ebene eines Quellelements zuweisen |
| [LayerIsolate](../layer-isolate/) | Alle Ebenen außer denen der ausgewählten Elemente einfrieren |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Alle Ebenen in einem Schritt auftauen |
