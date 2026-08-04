---
title: New File — Mulakan Lukisan Kosong dalam KulmanLab CAD
description: Arahan New File mengosongkan kanvas dan membuka lukisan kosong baharu. Nama fail ringkas dijana secara automatik dan disimpan ke storan pelayar.
keywords: [fail CAD baharu, lukisan baharu, kanvas kosong CAD, cipta lukisan baharu dalam talian, mula DXF baharu, fail baharu KulmanLab, tetapkan semula kanvas, kosongkan lukisan]
group: file
order: 2
---

# New File

Arahan **New File** mengosongkan kanvas dan memulakan lukisan kosong baharu. Nama fail unik dijana secara automatik.

## Cara mencipta fail baharu

Klik butang bar alat **New File** (ikon halaman baharu) dalam panel Fail. Kanvas dikosongkan serta-merta — tiada gesaan atau dialog pengesahan.

## Apa yang terkandung dalam fail baharu

Fail yang baru dicipta bermula dengan:

- **Tiada entiti** pada kanvas.
- **Satu lapisan lalai** bernama `0` dengan warna putih dan linetype `Continuous`.
- **Nama fail yang dijana**, `kulman.dxf` — atau `kulman (2).dxf`, `kulman (3).dxf`, … jika nama itu sudah digunakan.

Fail disimpan ke storan pelayar secara automatik dan muncul dalam [File Manager](../file-manager/), dan boleh [dinamakan semula](../file-manager/#menamakan-semula-fail) pada bila-bila masa.

## Amaran — kerja yang tidak disimpan dibuang

Mengklik **New File** membuang semua entiti pada kanvas semasa tanpa amaran. Jika anda ingin menyimpan lukisan semasa, [eksport](../export/) dahulu.

## Bila menggunakan New File berbanding Import

| Situasi | Tindakan yang disyorkan |
|---------|------------------------|
| Memulakan lukisan dari awal | **New File** |
| Membuka fail DXF atau JSON sedia ada | [Import](../import/) |
| Menyalin lukisan untuk bekerja pada varian | [Eksport](../export/) fail semasa, kemudian [Import](../import/) salinan |

## Arahan berkaitan

- [Import](../import/) — buka lukisan DXF atau JSON sedia ada
- [Export](../export/) — muat turun lukisan sebelum memulakan baharu
- [File Manager](../file-manager/) — pulihkan lukisan sebelumnya dari storan pelayar
