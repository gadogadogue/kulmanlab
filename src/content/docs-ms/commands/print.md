---
title: Arahan Print — Eksport Lukisan sebagai PNG, JPEG, WebP, atau PDF
description: Arahan Print membuka Pengurus Cetak — tetingkap eksport khusus dengan pratonton langsung, pemilih format, togel monokrom, dan pemilihan kawasan pilihan. Eksport sehingga 2000×2000 px. Menyokong PNG, JPEG, WebP, dan PDF.
keywords: [CAD eksport PNG, CAD eksport PDF, cetak lukisan CAD, pengurus cetak, eksport monokrom, eksport kulmanlab]
group: file
order: 4
---

# Print

Arahan `print` membuka **Pengurus Cetak** — tetingkap eksport khusus dengan kanvas pratonton langsung, pemilih format (PNG / JPEG / WebP / PDF), togel monokrom, dan pemangkasan kawasan pilihan. Tiada apa-apa yang dihantar ke pencetak fizikal; output dimuat turun sebagai fail.

## Membuka Pengurus Cetak

Klik butang bar alat **Print** atau taip `print` dalam terminal. Pengurus Cetak terbuka serta-merta menunjukkan pratonton viewport semasa.

## Susun atur Pengurus Cetak

Tetingkap mempunyai dua panel:
- **Bar sisi kiri** — semua kawalan eksport.
- **Panel kanan** — kanvas pratonton langsung yang dikemas kini semasa anda menukar tetapan.

### Kawalan bar sisi

| Kawalan | Penerangan |
|---------|------------|
| **Change Area** | Pangkas ke segi empat tepat tersuai pada kanvas (lihat di bawah) |
| Togel **Monochrome** | Tukar semua garis berwarna kepada hitam — aktif secara lalai untuk output cetak yang bersih |
| Dropdown **Format** | PNG, JPEG, WebP, atau PDF |
| Butang **Export** | Jana dan muat turun fail |

## Kualiti dan resolusi

Menu lungsur **Quality** menetapkan DPI eksport dirender: Draft (72), Normal (150, lalai), Presentation (300), atau Max (600). Kualiti yang lebih tinggi menghasilkan imej yang lebih besar dan lebih tajam pada saiz fizikal yang sama — ketebalan garis berskala bersama resolusi, jadi garis mengekalkan ketebalan fizikal yang sama di atas kertas pada mana-mana tetapan Kualiti. Satu pengecualian ialah garis rerambut (ketebalan garis 0), yang kekal pada lebar tetap 1 piksel pada mana-mana tahap Kualiti.

Menukar Kualiti serta-merta memberikan pratonton semula, jadi anda dapat melihat ketajaman sebenar sebelum mengeksport.

## Memilih kawasan eksport tersuai

Secara lalai pratonton menunjukkan tepat apa yang kelihatan pada kanvas apabila anda membuka Pengurus Cetak. Untuk mengeksport kawasan tertentu:

1. Klik **Change Area** — Pengurus Cetak disembunyikan dan kanvas menjadi interaktif.
2. **Klik sudut pertama** segi empat tepat eksport.
3. **Klik sudut bertentangan** — Pengurus Cetak dibuka semula dengan kawasan yang dipilih dalam pratonton.

Tekan `Escape` semasa pemilihan kawasan untuk membatalkan dan memulihkan kawasan sebelumnya.

Kanvas pratonton mengubah saiz secara dinamik agar sepadan dengan **nisbah aspek tepat** kawasan yang dipilih, supaya pratonton adalah tepat piksel.

## Format eksport

| Format | Terbaik untuk | Nota |
|--------|--------------|------|
| **PNG** | Tanpa kehilangan, garis tajam | Latar belakang putih, tiada ketelusan |
| **JPEG** | Fail lebih kecil untuk berkongsi | Kualiti 95%, sedikit mampatan |
| **WebP** | Fail terkecil untuk web | Kualiti 95% yang sama, mampatan lebih baik dari JPEG |
| **PDF** | Dokumen sedia cetak | Imej terbenam pada 150 DPI dalam bekas PDF |

Fail yang dieksport dinamakan `kulman-<timestamp>.<ext>` dan dimuat turun secara automatik.

## Resolusi dan latar belakang eksport

- Resolusi maksimum: **2000 × 2000 piksel**, diskala secara berkadar kepada kawasan yang dipilih.
- Latar belakang sentiasa **putih**.
- Lapisan yang ditandai sebagai **tidak dicetak** dikecualikan dari eksport.

## Rujukan papan kekunci

| Kekunci | Tindakan |
|---------|---------|
| `Escape` (semasa pemilihan kawasan) | Batal pemilihan kawasan, pulihkan kawasan sebelumnya |
| `Escape` (dalam Pengurus Cetak) | Tutup Pengurus Cetak |
