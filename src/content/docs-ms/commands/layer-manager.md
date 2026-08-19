---
title: LayerManager — Urus Semua Lapisan dalam Satu Jadual
description: Arahan LayerManager membuka jadual semua lapisan dalam lukisan, membolehkan anda menambah lapisan dan mengedit terus status beku, kunci, plot, warna, ketebalan garis, dan jenis garis untuk setiap lapisan.
keywords: [layer manager, jadual lapisan CAD, urus lapisan CAD, tambah lapisan CAD, beku kunci plot lapisan, pengurusan lapisan kulmanlab]
group: layer
order: 1
---

# LayerManager

Arahan `LayerManager` membuka jadual yang menyenaraikan semua lapisan dalam lukisan, dengan tetapan **Freeze** (beku), **Lock** (kunci), **Plot**, **Warna**, **Ketebalan garis**, dan **Jenis garis** yang boleh disunting terus dalam baris. Ia adalah tempat utama untuk menambah lapisan baharu dan menyesuaikan cara lapisan sedia ada berfungsi — arahan lapisan lain ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) masing-masing melakukan satu tugas tertumpu tanpa membukanya.

## Membuka Layer Manager

- Taip `LayerManager` dalam terminal, **atau**
- Klik butang **Layer Manager** pada panel lapisan.

Dialog dibuka sebagai panel terapung; tiada apa yang perlu dipilih terlebih dahulu.

## Jadual lapisan

| Lajur | Apa yang dikawal |
|-------|---------------------|
| Name | Nama lapisan, dipaparkan hanya-baca dalam jadual (ditetapkan sekali, semasa penciptaan) |
| Freeze | Menyembunyikan entiti lapisan dan mengecualikannya daripada pemilihan sehingga dinyahbeku |
| Lock | Menghalang penyuntingan entiti pada lapisan, tanpa menyembunyikannya |
| Plot | Sama ada entiti lapisan disertakan semasa mencetak atau eksport ke PDF |
| Color | Warna ACI lapisan — klik contoh untuk membuka pemilih warna |
| Lineweight | Ketebalan garis lapisan — klik chip untuk membuka pemilih ketebalan |
| Linetype | Corak garis putus lapisan — klik chip untuk membuka pemilih jenis garis |

Menogol Freeze, Lock, atau Plot berkuat kuasa serta-merta — tiada langkah simpan berasingan. Entiti yang ditetapkan kepada **ByLayer** untuk warna, ketebalan garis, atau jenis garis (nilai lalai) mengikut apa yang anda tetapkan di sini; entiti dengan pengatasan eksplisit mereka sendiri tidak terjejas.

## Menambah lapisan

1. Klik **+ Add Layer** di bahagian bawah jadual.
2. Taip nama dan tekan **Enter** untuk mengesahkan, atau **Escape** untuk membatalkan.

Nama lapisan boleh mengandungi huruf, nombor, ruang, dan `_`, `-`, `$`. Nama yang kosong, sudah digunakan, atau mengandungi aksara lain akan ditolak dengan ralat sebaris, dan baris kekal terbuka untuk cubaan lain.

Lapisan baharu bermula sebagai **tidak dibekukan, tidak dikunci, boleh diplot**, dengan warna 7 (putih/hitam), ketebalan garis Default, dan jenis garis Continuous — nilai lalai yang sama yang [Import](../import/) berikan kepada lapisan `0` dalam lukisan kosong.

## Apa yang anda tidak boleh lakukan di sini

Tiada butang padam — lapisan tidak pernah dibuang selepas dicipta, hanya boleh dibekukan atau dibiarkan tidak digunakan. Jadual juga tidak menunjukkan lapisan mana yang *semasa*; itu ditetapkan melalui menu lungsur pada panel lapisan atau melalui [LayerMakeCurrent](../layer-make-current/), bukan daripada dialog ini.

## Rujukan papan kekunci

| Kekunci | Tindakan |
|---------|----------|
| `Enter` | Sahkan nama lapisan baharu (semasa menambah) |
| `Escape` | Batalkan penambahan lapisan, atau tutup dialog |

## Arahan berkaitan

| Arahan | Fungsinya |
|--------|-----------|
| [LayerMakeCurrent](../layer-make-current/) | Tetapkan lapisan semasa agar sepadan dengan lapisan entiti yang diklik |
| [LayerMatch](../layer-match/) | Tugaskan semula entiti yang dipilih untuk memadankan lapisan entiti sumber |
| [LayerIsolate](../layer-isolate/) | Bekukan semua lapisan kecuali lapisan entiti yang dipilih |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Nyahbeku semua lapisan dalam satu langkah |
