---
title: New File — Memulai Gambar Kosong di KulmanLab CAD
description: Perintah New File membersihkan kanvas dan membuka gambar kosong yang baru. Nama file sederhana dibuat secara otomatis dan disimpan ke penyimpanan browser.
keywords: [file CAD baru, gambar baru, kanvas kosong CAD, buat gambar baru online, mulai DXF baru, KulmanLab new file, reset kanvas, hapus gambar, kulmanlab]
group: file
order: 2
---

# New File

Perintah **New File** membersihkan kanvas dan memulai gambar kosong yang baru. Nama file unik dibuat secara otomatis.

## Cara membuat file baru

Klik tombol toolbar **New File** (ikon halaman baru) di panel File. Kanvas langsung dibersihkan — tidak ada prompt atau dialog konfirmasi.

## Apa yang ada dalam file baru

File yang baru dibuat dimulai dengan:

- **Tidak ada entitas** di kanvas.
- **Satu layer default** bernama `0` dengan warna putih dan tipe garis `Continuous`.
- **Nama file yang dihasilkan**, `kulman.dxf` — atau `kulman (2).dxf`, `kulman (3).dxf`, … jika nama tersebut sudah digunakan.

File secara otomatis disimpan ke penyimpanan browser dan muncul dalam [File Manager](../file-manager/), dan dapat [diganti namanya](../file-manager/#mengganti-nama-file) kapan saja.

## Peringatan — pekerjaan yang belum disimpan akan dibuang

Mengklik **New File** membuang semua entitas di kanvas saat ini tanpa peringatan. Jika Anda ingin menyimpan gambar saat ini, [ekspor](../export-manager/) terlebih dahulu.

## Kapan menggunakan New File vs Import

| Situasi | Tindakan yang disarankan |
|-----------|-------------------|
| Memulai gambar dari awal | **New File** |
| Membuka file DXF atau JSON yang ada | [Import](../import/) |
| Menyalin gambar untuk bekerja pada varian | [Ekspor](../export-manager/) file saat ini, kemudian [Impor](../import/) salinannya |

## Perintah terkait

- [Import](../import/) — buka gambar DXF atau JSON yang ada
- [Export Manager](../export-manager/) — unduh gambar sebelum memulai yang baru
- [File Manager](../file-manager/) — pulihkan gambar sebelumnya dari penyimpanan browser
