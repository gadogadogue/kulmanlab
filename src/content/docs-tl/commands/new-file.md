---
title: New File — Simulan ang Isang Blangkong Drawing sa KulmanLab CAD
description: Nililinis ng New File command ang canvas at nagbubukas ng bagong blangkong drawing. Awtomatikong nabubuo ang isang simpleng pangalan ng file at na-save sa browser storage.
keywords: [bagong CAD file, bagong drawing, blangkong canvas CAD, gumawa ng bagong drawing online, simulan ang bagong DXF, KulmanLab new file, i-reset ang canvas, linisin ang drawing]
group: file
order: 2
---

# New File

Nililinis ng **New File** command ang canvas at sinisimulan ang isang bagong blangkong drawing. Awtomatikong nabubuo ang isang natatanging pangalan ng file.

## Paano gumawa ng bagong file

I-click ang **New File** toolbar button (new-page icon) sa File panel. Agad na naglilinis ang canvas — walang prompts o confirmation dialogs.

## Ano ang nilalaman ng bagong file

Ang isang bagong gawang file ay nagsisimula nang mayroong:

- **Walang entities** sa canvas.
- **Isang default na layer** na pinangalanang `0` na may kulay na puti at linetype na `Continuous`.
- Isang **generated na pangalan ng file**, `kulman.dxf` — o `kulman (2).dxf`, `kulman (3).dxf`, … kung nagamit na ang pangalang iyon.

Awtomatikong na-save ang file sa browser storage, lilitaw sa [File Manager](../file-manager/), at maaaring [palitan ang pangalan](../file-manager/#pagpapalit-ng-pangalan-ng-file) anumang oras.

## Babala — natatanggal ang hindi na-save na trabaho

Ang pag-click sa **New File** ay tinatanggal ang lahat ng entities sa kasalukuyang canvas nang walang babala. Kung gusto mong panatilihin ang kasalukuyang drawing, [i-export](../export/) muna ito.

## Kailan gagamitin ang New File kumpara sa Import

| Sitwasyon | Inirerekumendang aksyon |
|-----------|-------------------|
| Magsisimula ng drawing mula sa wala | **New File** |
| Magbubukas ng umiiral na DXF o JSON file | [Import](../import/) |
| Kokopyahin ang isang drawing para gawan ng variant | [Export](../export/) ang kasalukuyang file, pagkatapos ay [i-import](../import/) ang kopya |

## Kaugnay na commands

- [Import](../import/) — buksan ang umiiral na DXF o JSON drawing
- [Export](../export/) — i-download ang drawing bago magsimula ng panibago
- [File Manager](../file-manager/) — i-restore ang naunang drawing mula sa browser storage
