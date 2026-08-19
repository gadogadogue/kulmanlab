---
title: FontAdd Command — Upload a Custom TTF Font from the Terminal
description: The FontAdd command opens your system's file picker to upload a .ttf font, without opening the Font Manager dialog first. It's the same upload the Font Manager's Add Font button triggers, available as its own terminal command.
keywords: [CAD font add command, fontadd command, upload ttf terminal, custom font CAD, kulmanlab]
group: style
order: 3
---

# FontAdd

The `FontAdd` command opens your system's file picker to upload a custom `.ttf` font, without opening the [Font Manager](../font-manager/) dialog first. It's the same upload the Font Manager's **Add Font** button triggers — FontAdd is just a direct way to reach it from the terminal.

## Uploading a font

1. Type `FontAdd` in the terminal, or click **Add Font** in the [Font Manager](../font-manager/) dialog footer.
2. Choose a `.ttf` file in the system picker. Only TrueType fonts are supported — `.otf` and `.woff`/`.woff2` are not.

The command finishes as soon as the file picker opens — there's no further prompt, click, or terminal input. The font is registered and appears in the **User** group as soon as the file is selected.

## What happens on upload

- The file name (without the extension) becomes the font's name. Uploading `MyFont.ttf` adds a font named `MyFont`.
- Uploading a file whose name matches an existing custom font **replaces** it.
- The font is saved permanently in the browser (IndexedDB) and reloads automatically the next time you open KulmanLab CAD — it is not tied to the current drawing.

## Keyboard reference

FontAdd has no keyboard interaction of its own — the entire command is the browser's native file-picker dialog. Cancelling that dialog (or picking no file) leaves the font list unchanged.

## Related commands

| Command | What it does |
|---------|-------------|
| [Font Manager](../font-manager/) | Browse, preview, select, and remove fonts, including custom uploads |
| [Text](../text/) | Places the text labels that font choices apply to |
