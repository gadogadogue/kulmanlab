---
title: Hatch Manager Command — Browse and Upload .pat Patterns
description: The Hatch Manager command opens a dialog for browsing hatch patterns with a live swatch preview, and for uploading your own .pat pattern files. Uploaded files are saved in the browser and shadow built-in patterns of the same name.
keywords: [hatch manager, custom hatch pattern CAD, upload pat file, acad.pat, hatch pattern library, ANSI31, kulmanlab]
group: style
order: 4
---

# Hatch Manager

The `HatchManager` command opens a dialog for browsing hatch patterns with a live swatch preview, and for uploading your own `.pat` pattern files for use with [Hatch](../hatch/).

## Opening the Hatch Manager

Type `HatchManager` in the terminal. This is separate from the pattern picker that opens when you click a hatch's **Pattern** chip — the picker chooses a pattern for one hatch, the Hatch Manager is where you add or remove `.pat` files.

## Pattern groups

| Group | Contents |
|-------|----------|
| **User** | Patterns from your own uploaded `.pat` files, sub-grouped by which file each came from (only shown once you've uploaded one) |
| **Standard** | `SOLID` plus this drawing's own pattern table — every new drawing starts with the same built-in library, the way its layers and linetypes do |

Click any pattern in the list (or use `↑`/`↓`) to preview it on the right — a swatch drawn by the same code the canvas fills with, so it's exactly what the drawing will show, plus the pattern's name, description, and line count.

## Uploading a custom pattern file

1. Click **Add .pat File** in the dialog footer.
2. Choose a `.pat` file — the standard hatch pattern format. A single file commonly defines many named patterns at once; all of them appear as separate entries grouped under that file's name.
3. Uploaded files are saved permanently in the browser (IndexedDB), sorted most-recently-added first, and reload automatically the next time you open KulmanLab CAD.

Uploading a file that defines a pattern with the same name as a built-in one **shadows** the default — this is the supported way to get Autodesk's authoritative pattern definitions: upload a real `acad.pat` and its versions of ANSI31 and the other standard names take over from KulmanLab's own approximations.

If a drawing references a pattern name that isn't in your library — imported from a DXF that used a pattern from an `acad.pat` you haven't uploaded — the hatch still renders, using `ANSI31` as a stand-in, rather than falling back to a flat, patternless fill.

## Removing a pattern file

Click the **×** next to a file name in the **User** group to remove it and every pattern it defined. Any hatch already using one of those patterns falls back to `ANSI31` immediately. Built-in **Standard** patterns can't be removed.

## Keyboard reference

| Key | Action |
|-----|--------|
| `↑` / `↓` | Move the selection up or down the pattern list |
| `Escape` | Close the Hatch Manager |

## Related commands

- [Hatch](../hatch/) — fills a picked area using the pattern currently selected
- [Font Manager](../font-manager/) — the same upload/browse pattern, for custom fonts instead of hatch patterns
