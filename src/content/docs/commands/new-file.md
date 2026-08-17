---
title: New File — Start a Blank Drawing in KulmanLab CAD
description: The New File command clears the canvas and opens a fresh blank drawing. A plain file name is generated automatically and saved to browser storage.
keywords: [new CAD file, new drawing, blank canvas CAD, create new drawing online, start new DXF, KulmanLab new file, reset canvas, clear drawing]
group: file
order: 2
---

# New File

The **New File** command clears the canvas and starts a fresh blank drawing. A unique file name is generated automatically.

## How to create a new file

Click the **New File** toolbar button (new-page icon) in the File panel. The canvas clears immediately — no prompts or confirmation dialogs.

## What the new file contains

A freshly created file starts with:

- **No entities** on the canvas.
- **One default layer** named `0` with color white and linetype `Continuous`.
- A **generated file name**, `kulman.dxf` — or `kulman (2).dxf`, `kulman (3).dxf`, … if that name is already taken.

The file is saved to browser storage automatically and appears in the [File Manager](../file-manager/), and can be [renamed](../file-manager/#renaming-a-file) at any time.

## Warning — unsaved work is discarded

Clicking **New File** discards all entities on the current canvas without warning. If you want to keep the current drawing, [export](../export-manager/) it first.

## When to use New File vs Import

| Situation | Recommended action |
|-----------|-------------------|
| Starting a drawing from scratch | **New File** |
| Opening an existing DXF or JSON file | [Import](../import/) |
| Copying a drawing to work on a variant | [Export Manager](../export-manager/) the current file, then [Import](../import/) the copy |

## Related commands

- [Import](../import/) — open an existing DXF or JSON drawing
- [Export Manager](../export-manager/) — download the drawing before starting fresh
- [File Manager](../file-manager/) — restore a previous drawing from browser storage
