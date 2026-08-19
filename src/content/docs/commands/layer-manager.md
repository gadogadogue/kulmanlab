---
title: LayerManager — Manage All Layers in One Table
description: The LayerManager command opens a table of every layer in the drawing, letting you add layers and edit each one's freeze, lock, plot, color, lineweight, and linetype in place.
keywords: [layer manager, CAD layer table, manage layers CAD, add layer CAD, freeze lock plot layer, kulmanlab layer management]
group: layer
order: 1
---

# LayerManager

The `LayerManager` command opens a table listing every layer in the drawing, with its **Freeze**, **Lock**, **Plot**, **Color**, **Lineweight**, and **Linetype** settings editable directly in the row. It's the central place to add new layers and adjust how existing ones behave — the other layer commands ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) each do one focused thing without opening it.

## Opening the Layer Manager

- Type `LayerManager` in the terminal, **or**
- Click the **Layer Manager** button in the layer panel.

The dialog opens as a floating panel; nothing needs to be selected first.

## The layer table

| Column | What it controls |
|--------|-------------------|
| Name | The layer's name, shown read-only in the table (set once, at creation) |
| Freeze | Hides the layer's entities and excludes them from selection until unfrozen |
| Lock | Prevents entities on the layer from being edited, without hiding them |
| Plot | Whether the layer's entities are included when printing or exporting to PDF |
| Color | The layer's ACI color — click the swatch to open the color picker |
| Lineweight | The layer's line thickness — click the chip to open the lineweight picker |
| Linetype | The layer's dash pattern — click the chip to open the linetype picker |

Toggling Freeze, Lock, or Plot takes effect immediately — there's no separate save step. Entities set to **ByLayer** for color, lineweight, or linetype (the default) pick up whatever you set here; entities with an explicit override of their own are unaffected.

## Adding a layer

1. Click **+ Add Layer** at the bottom of the table.
2. Type a name and press **Enter** to confirm, or **Escape** to cancel.

Layer names may contain letters, numbers, spaces, and `_`, `-`, `$`. A name that's empty, already in use, or contains any other character is rejected with an inline error, and the row stays open for another try.

New layers start **unfrozen, unlocked, plottable**, with color 7 (white/black), lineweight Default, and linetype Continuous — the same defaults [Import](../import/) assigns to layer `0` in a blank drawing.

## What you can't do here

There is no delete button — layers are never removed once created, only frozen or left unused. There's also no indicator in the table for which layer is *current*; that's set by picking from the layer panel's dropdown or by [LayerMakeCurrent](../layer-make-current/), not from this dialog.

## Keyboard reference

| Key | Action |
|-----|--------|
| `Enter` | Confirm a new layer's name (while adding) |
| `Escape` | Cancel adding a layer, or close the dialog |

## Related commands

| Command | What it does |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Set the current layer to match a clicked entity's layer |
| [LayerMatch](../layer-match/) | Reassign selected entities to match the layer of a source entity |
| [LayerIsolate](../layer-isolate/) | Freeze all layers except those of the selected entities |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Unfreeze all layers in one step |
