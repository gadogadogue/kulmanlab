---
title: LayerManager — Kelola Semua Layer dalam Satu Tabel
description: Perintah LayerManager membuka tabel semua layer dalam gambar, memungkinkan Anda menambah layer dan mengedit langsung status beku, kunci, plot, warna, ketebalan garis, dan tipe garis untuk setiap layer.
keywords: [layer manager, tabel layer CAD, kelola layer CAD, tambah layer CAD, bekukan kunci plot layer, manajemen layer kulmanlab]
group: layer
order: 1
---

# LayerManager

Perintah `LayerManager` membuka tabel yang mencantumkan semua layer dalam gambar, dengan pengaturan **Freeze** (bekukan), **Lock** (kunci), **Plot**, **Warna**, **Ketebalan garis**, dan **Tipe garis** yang dapat diedit langsung di baris. Ini adalah tempat utama untuk menambah layer baru dan menyesuaikan perilaku layer yang sudah ada — perintah layer lainnya ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) masing-masing melakukan satu tugas terfokus tanpa membukanya.

## Membuka Layer Manager

- Ketik `LayerManager` di terminal, **atau**
- Klik tombol **Layer Manager** di panel layer.

Dialog terbuka sebagai panel mengambang; tidak ada yang perlu dipilih terlebih dahulu.

## Tabel layer

| Kolom | Yang dikendalikan |
|-------|----------------------|
| Name | Nama layer, ditampilkan hanya-baca di tabel (diatur sekali, saat pembuatan) |
| Freeze | Menyembunyikan entitas layer dan mengecualikannya dari seleksi hingga dicairkan |
| Lock | Mencegah pengeditan entitas pada layer, tanpa menyembunyikannya |
| Plot | Apakah entitas layer disertakan saat mencetak atau mengekspor ke PDF |
| Color | Warna ACI layer — klik contoh warna untuk membuka pemilih warna |
| Lineweight | Ketebalan garis layer — klik chip untuk membuka pemilih ketebalan |
| Linetype | Pola garis putus-putus layer — klik chip untuk membuka pemilih tipe garis |

Mengalihkan Freeze, Lock, atau Plot berlaku segera — tidak ada langkah penyimpanan terpisah. Entitas yang diatur ke **ByLayer** untuk warna, ketebalan garis, atau tipe garis (nilai default) mengikuti apa yang Anda atur di sini; entitas dengan override eksplisit mereka sendiri tidak terpengaruh.

## Menambah layer

1. Klik **+ Add Layer** di bagian bawah tabel.
2. Ketik nama dan tekan **Enter** untuk konfirmasi, atau **Escape** untuk batal.

Nama layer dapat berisi huruf, angka, spasi, dan `_`, `-`, `$`. Nama yang kosong, sudah digunakan, atau berisi karakter lain akan ditolak dengan kesalahan inline, dan baris tetap terbuka untuk percobaan lagi.

Layer baru dimulai sebagai **tidak beku, tidak terkunci, dapat diplot**, dengan warna 7 (putih/hitam), ketebalan garis Default, dan tipe garis Continuous — nilai default yang sama yang diberikan [Import](../import/) ke layer `0` dalam gambar kosong.

## Yang tidak bisa Anda lakukan di sini

Tidak ada tombol hapus — layer tidak pernah dihapus setelah dibuat, hanya bisa dibekukan atau dibiarkan tidak digunakan. Tabel juga tidak menunjukkan layer mana yang *aktif saat ini*; itu diatur melalui dropdown di panel layer atau melalui [LayerMakeCurrent](../layer-make-current/), bukan dari dialog ini.

## Referensi keyboard

| Tombol | Aksi |
|--------|------|
| `Enter` | Konfirmasi nama layer baru (saat menambah) |
| `Escape` | Batal menambah layer, atau tutup dialog |

## Perintah terkait

| Perintah | Fungsi |
|---------|-------------|
| [LayerMakeCurrent](../layer-make-current/) | Mengatur layer saat ini agar sesuai dengan layer entitas yang diklik |
| [LayerMatch](../layer-match/) | Menetapkan ulang entitas yang dipilih agar sesuai dengan layer entitas sumber |
| [LayerIsolate](../layer-isolate/) | Membekukan semua layer kecuali layer entitas yang dipilih |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Mencairkan semua layer dalam satu langkah |
