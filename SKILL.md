---
name: skripsi-writing
description: Audit and revise UNDIP Informatics thesis DOCX safely.
version: 0.2.0
author: Julius Tegar, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [skripsi, undip, informatika, docx, audit, sitasi]
    related_skills: [docx, pdf, ai-expert-team]
---

# Skripsi Writing — UNDIP Informatika

Gunakan skill ini untuk mengaudit, menulis, dan merevisi skripsi S1 Informatika Universitas Diponegoro dalam format `.docx`. Skill ini memisahkan audit, proposal perubahan, persetujuan pengguna, edit, dan verifikasi. Skill tidak menggantikan pembimbing, penguji, pedoman resmi terbaru, atau validasi ilmiah.

## When to Use

Gunakan ketika pengguna meminta:

- audit bahasa, struktur, sitasi, klaim, atau format skripsi `.docx`;
- revisi bertahap pada naskah Word dengan format template UNDIP Informatika;
- validasi sitasi berdasarkan PDF jurnal/artikel di folder `references/`;
- penulisan atau penyuntingan Bab I–V dengan bahasa Indonesia akademik yang jelas;
- pemeriksaan istilah teknis, italic, tabel, gambar, persamaan, source code, daftar isi, atau daftar pustaka;
- bantuan menyelesaikan konflik pedoman atau masalah metodologis yang kompleks.

Jangan gunakan skill ini untuk mengedit `.doc` lama, mengarang data/hasil penelitian/sitasi, atau menerbitkan naskah dan sumber pengguna ke publik.

## Prerequisites

Sebelum bekerja, minta atau temukan:

- satu file skripsi `.docx` sumber;
- folder kerja skripsi yang memuat `references/` untuk PDF jurnal/artikel yang benar-benar digunakan;
- bab/subbab dan tujuan pekerjaan bila audit tidak mencakup seluruh dokumen;
- data, metode, hasil, dan keputusan pengguna yang menjadi dasar Bab III–V;
- pedoman/template UNDIP Informatika yang berlaku. Gunakan `references/undip-informatika-2024.md` sebagai ringkasan kerja, bukan pengganti dokumen resmi.

Jika PDF tidak ada, tidak terbaca, atau hanya berupa scan tanpa OCR, tandai sitasi sebagai `BELUM TERVERIFIKASI`; jangan menebak metadata atau isi sumber.

## Non-negotiable Safety and Approval Rules

1. **Audit dahulu.** Audit tidak boleh mengubah DOCX.
2. **Proposal dahulu.** Setiap perubahan ditulis dalam Markdown sebelum edit, dengan lokasi, teks/masalah, usulan, alasan, sumber aturan, dampak, dan risiko.
3. **Persetujuan eksplisit.** Jangan mengubah DOCX sebelum pengguna menyetujui proposal tertentu. Persetujuan umum tanpa proposal yang terlihat tidak cukup.
4. **Satu perubahan atau batch kecil.** Kerjakan item proposal satu per satu atau dalam batch kecil yang disetujui; jangan melakukan rewrite menyeluruh secara diam-diam.
5. **Jangan menimpa sumber.** Default output adalah file baru, misalnya `skripsi-revised-01.docx`.
6. **Tidak ada publikasi otomatis.** Jangan commit, push, upload, atau publish tanpa persetujuan terpisah dan eksplisit.
7. **Jaga provenance.** Naskah, identitas mahasiswa, data penelitian, komentar pembimbing, dan PDF berhak cipta tetap berada di folder kerja privat.

## Workflow

### 1. Inventaris dan baseline

Catat nama file, ukuran, versi, tanggal audit, dan file yang akan disentuh. Periksa apakah DOCX dapat dibuka sebagai paket Word yang sehat. Baca struktur sebelum isi: bagian, heading, paragraf, tabel, gambar, caption, daftar, header/footer, style, komentar, dan tracked changes.

Gunakan kemampuan `docx` skill yang tersedia. Jangan mengedit XML mentah atau menggunakan substitusi teks pada file `.docx`. Jika alat DOCX tidak tersedia, berhenti pada audit atau laporkan keterbatasan; jangan membuat file Word palsu.

### 2. Audit dan laporan Markdown

Buat `audit/audit-YYYYMMDD-HHmm.md`. Setiap temuan wajib memiliki:

- ID stabil, misalnya `LANG-001`;
- tingkat: `BLOCKER`, `HIGH`, `MEDIUM`, atau `LOW`;
- lokasi: bab, subbab, nomor paragraf/tabel, atau kutipan pendek;
- kategori: bahasa, struktur, sitasi, klaim, format, atau integritas DOCX;
- masalah yang teramati;
- aturan/evidence yang dipakai;
- usulan tindakan atau `PERLU KEPUTUSAN`;
- status: `OPEN`, `DEFERRED`, atau `READY_FOR_PROPOSAL`.

Prioritaskan tata bahasa dan kejelasan, lalu struktur argumen, validasi sumber, kalibrasi klaim, dan format. Jangan menyatakan temuan sebagai fakta jika hanya inferensi.

### 3. Proposal perubahan

Buat `proposals/proposal-YYYYMMDD-NN.md` memakai `templates/proposal-edit.md`. Status awal harus `DRAFT`. Proposal harus memetakan setiap perubahan ke ID audit dan mencantumkan teks sebelum/sesudah atau operasi yang jelas.

Kelompokkan proposal berdasarkan risiko:

- **P1 bahasa:** ejaan, tanda baca, diksi, kalimat, kesinambungan;
- **P2 struktur:** paragraf, heading, urutan penjelasan, tabel/gambar;
- **P3 sumber/klaim:** sitasi, interpretasi, generalisasi, klaim kausal;
- **P4 format DOCX:** style, caption, numbering, TOC, margin, dan layout.

Jangan menggabungkan P3 atau P4 ke dalam revisi bahasa tanpa persetujuan terpisah jika dampaknya tidak jelas.

### 4. Approval gate

Tampilkan atau laporkan proposal kepada pengguna. Tunggu persetujuan yang merujuk pada ID/versi proposal, misalnya `setujui P1 proposal-...`; simpan status `APPROVED` dan waktu persetujuan di Markdown. Jika scope berubah, buat versi proposal baru dan minta persetujuan ulang.

### 5. Edit DOCX secara konservatif

Setelah disetujui:

- salin sumber ke output versi baru;
- ubah hanya lokasi yang ada di proposal;
- pertahankan style paragraf, run formatting, heading hierarchy, numbering, tabel, gambar, caption, header/footer, field, komentar, dan tracked changes sejauh alat mendukung;
- gunakan operasi find/replace yang menjaga format untuk teks yang tidak terpecah; jika teks terpecah antar-run, lakukan pemeriksaan khusus sebelum perubahan;
- jangan mengubah seluruh paragraf dengan `cell.text` atau operasi yang mereset format kecuali proposal menyetujui dampaknya;
- jangan memperbarui TOC/nomor halaman secara manual sebagai klaim final; Word/LibreOffice mungkin perlu membuka dan memperbarui field.

Jika perlu menulis ulang paragraf, pertahankan makna, sitasi, istilah teknis, dan struktur style. Perubahan substansial harus ditampilkan dalam proposal sebelum diterapkan.

### 6. Verifikasi pasca-edit

Buat `audit/verification-YYYYMMDD-NN.md` dan lakukan semua pemeriksaan berikut:

- file output dapat dibuka dan lolos health check DOCX;
- teks lama hilang hanya pada lokasi yang ditargetkan dan teks baru ada;
- heading, jumlah tabel/gambar, caption, daftar, style, header/footer, komentar, dan tracked changes dibandingkan dengan baseline;
- tidak ada perubahan di luar proposal yang disetujui;
- sitasi dan daftar pustaka tetap utuh;
- output dibaca ulang sebagai DOCX, bukan hanya dari teks proposal;
- layout visual diverifikasi dengan Word/LibreOffice jika tersedia; jika tidak, status layout adalah `PARTIAL`, bukan `PASS`.

Gunakan verdict `PASS`, `PARTIAL`, atau `FAIL`. Jangan menyebut pekerjaan selesai bila ada blocker yang belum diberi keputusan.

## UNDIP Informatika Rules

Detail kerja ada di `references/undip-informatika-2024.md`. Terapkan dengan status sumber yang jelas:

- abstrak Indonesia dan Inggris satu paragraf, satu spasi, tanpa indentasi baris pertama, maksimal 300 kata;
- isi utama umumnya spasi 1,5; heading maksimal sampai level 4;
- daftar isi, daftar tabel, dan daftar gambar sebaiknya memakai field otomatis;
- tabel, gambar, flowchart, bagan, dan komponen lain harus disebut oleh paragraf;
- caption dan penomoran mengikuti bab serta urutan kemunculan;
- tabel satu spasi, tidak melewati margin, header diulang jika tabel bersambung;
- pemerian menggunakan nomor atau huruf, bukan bullet;
- source code memakai tabel 2 baris 1 kolom, Courier New 10 pt, tanpa caption/daftar source code di bagian depan;
- persamaan rata kiri dan semua simbol dijelaskan;
- daftar pustaka menggunakan APA 7 atau format setara yang diwajibkan template;
- jangan menghapus tabel petunjuk/template tanpa memastikan bagian tersebut memang bukan isi naskah pengguna.

### Istilah Inggris dan italic

Jangan memiringkan istilah hanya karena berbahasa Inggris. Klasifikasikan dahulu:

- istilah asing umum yang belum terserap dan bukan nama khusus: dapat menggunakan *italic*;
- nama metode, algoritma, model, arsitektur, framework, library, software, dan singkatan: umumnya tidak italic;
- kepanjangan teknis dalam kurung: tidak otomatis italic;
- istilah yang sudah diserap: gunakan bentuk Indonesia tanpa italic;
- `ABSTRACT` dan isinya mengikuti aturan template, tidak dimiringkan hanya karena berbahasa Inggris.

Jika status istilah tidak pasti, tandai untuk keputusan pengguna atau cek pedoman/sumber yang tersedia.

### Sitasi dan sumber

- Bab I–II: cocokkan setiap klaim bersitasi dengan PDF di `references/`; bedakan isi eksplisit sumber dari inferensi.
- Bab III–V: jangan menambah sitasi berdasarkan aturan kerja ini; gunakan metode, data, hasil, analisis, dan kesimpulan penelitian. Jika aturan institusi atau pembimbing berbeda, tandai konflik dan minta keputusan.
- Jangan membuat penulis, tahun, judul, DOI, URL, hasil, atau nomor halaman yang tidak tersedia.
- Daftar pustaka harus ditelusuri balik ke sitasi dan sumber yang tersedia; item tanpa provenance diberi status `BELUM TERVERIFIKASI`.

### Kalibrasi klaim Bab IV–V

Bedakan deskripsi temuan, interpretasi, dan implikasi. Sesuaikan kekuatan kata kerja dengan desain, sampel, variabel, instrumen, analisis, dan batasan penelitian. Hindari `membuktikan`, `memastikan`, `selalu`, `pasti`, generalisasi universal, dan `menyebabkan` bila desain tidak mendukung kausalitas. Utamakan `menunjukkan`, `menggambarkan`, `mengindikasikan`, `ditemukan bahwa`, dan `dalam konteks penelitian ini`.

## AI Expert Team Escalation

Gunakan `ai-expert-team` hanya bila masalahnya kompleks: konflik pedoman, masalah metodologi, klaim kausal/generalisasi, konflik sitasi, atau perubahan DOCX berisiko tinggi. Untuk typo atau aturan format yang jelas, jangan memanggilnya.

Handoff harus read-only dan memuat scope, out-of-scope, evidence yang wajib, alat yang diizinkan, larangan edit/commit/push, dan acceptance criteria. Pilih satu decision owner, 3–5 spesialis yang tidak tumpang tindih, serta verifier. Hasilnya hanya masukan: masukkan temuan terverifikasi ke proposal Markdown dan tetap minta approval. Expert consensus bukan bukti.

## Output Contract

Audit:

```markdown
# Audit Skripsi
Status: DRAFT
Baseline: ...

## Temuan
| ID | Level | Lokasi | Kategori | Masalah | Bukti/aturan | Tindakan | Status |
```

Proposal:

```markdown
# Proposal Revisi
Status: DRAFT
Scope: ...

## Perubahan
### [ID] [P1/P2/P3/P4]
- Sebelum:
- Sesudah/usulan:
- Alasan dan sumber:
- Dampak/risiko:
- Approval: MENUNGGU
```

Final report wajib menyebut file sumber, file output, proposal yang disetujui, verdict verifikasi, perubahan yang dibuat, dan keterbatasan layout atau sumber.

## Pitfalls

- Jangan menganggap DOCX sehat hanya karena teks berhasil diekstrak.
- Jangan mengedit sumber langsung.
- Jangan mengubah style menjadi plain text demi memudahkan find/replace.
- Jangan menyimpulkan PDF kosong berarti tidak memiliki isi; mungkin berupa scan.
- Jangan menganggap template contoh sebagai aturan terbaru tanpa mencatat sumber dan versinya.
- Jangan memindahkan klaim Bab IV–V ke tingkat yang lebih kuat hanya karena kalimatnya menjadi lebih formal.
- Jangan memasukkan PDF jurnal berhak cipta, skripsi, data, atau identitas ke repo publik.
- Jangan menyatakan layout sempurna tanpa verifikasi visual.

## Verification Checklist

- [ ] Baseline DOCX dan input references dicatat.
- [ ] Audit Markdown selesai sebelum edit.
- [ ] Setiap perubahan punya ID audit dan proposal.
- [ ] Proposal disetujui eksplisit sebelum edit.
- [ ] Sumber asli tidak tertimpa.
- [ ] Edit terbatas pada scope proposal.
- [ ] Output DOCX lolos health check dan dibaca ulang.
- [ ] Struktur, style, tabel, gambar, caption, field, komentar, dan revisi dibandingkan.
- [ ] Sitasi dan provenance PDF diberi status.
- [ ] Klaim Bab IV–V dikalibrasi.
- [ ] Keterbatasan layout dilaporkan.
- [ ] Tidak ada commit/push/publish tanpa persetujuan terpisah.
