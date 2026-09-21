---
name: skripsi-writing
description: Audit and revise UNDIP thesis DOCX safely.
version: 0.3.0
author: Julius Tegar, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [skripsi, undip, informatika, docx, academic-writing, eyd, citation-audit]
    related_skills: [docx, pdf, ai-expert-team]
---

# Skripsi Writing — UNDIP Informatika

## Overview

Skill ini membantu menulis, mengaudit, dan merevisi skripsi S1 Informatika Universitas Diponegoro dalam format Microsoft Word `.docx`. Fokusnya bukan menghasilkan tulisan yang terdengar ilmiah, tetapi menjaga tiga hal sekaligus: bahasa Indonesia yang jelas menurut EYD Edisi Kelima, argumen yang sesuai dengan bukti penelitian, dan struktur/format DOCX yang tidak rusak.

Skill ini bekerja dengan pola **inspect → audit → propose → approve → edit → verify**. Audit dan proposal selalu menghasilkan Markdown terlebih dahulu. File Word tidak boleh diubah sebelum pengguna menyetujui proposal yang spesifik. Skill tidak menggantikan pembimbing, penguji, pedoman UNDIP terbaru, pemeriksaan plagiarisme, atau validasi metodologi oleh peneliti.

Baca referensi hanya saat relevan:

- aturan penulisan dan struktur paragraf: `references/writing-rules.md`;
- EYD dan struktur kalimat: `references/eyd-edisi-kelima.md`;
- sitasi dan PDF sumber: `references/citation-and-source-audit.md`;
- istilah asing dan *italic*: `references/foreign-terms-and-italic.md`;
- kalibrasi klaim Bab IV–V: `references/claim-calibration.md`;
- aturan template UNDIP Informatika: `references/undip-informatika-template.md`;
- preservasi dan verifikasi DOCX: `references/docx-preservation.md`;
- eskalasi masalah kompleks: `references/ai-expert-team-protocol.md`.

## When to Use

Gunakan skill ini ketika pengguna meminta:

- menulis bagian skripsi dari kerangka, catatan, data, metode, atau hasil yang diberikan;
- memperbaiki ejaan, tata bahasa, struktur kalimat, diksi, kepaduan, dan alur paragraf;
- mengaudit skripsi `.docx` sebelum perubahan apa pun;
- memvalidasi sitasi menggunakan PDF jurnal/artikel di folder referensi;
- meninjau istilah teknis Informatika, nama metode, nama model, singkatan, dan penggunaan *italic*;
- mengaudit klaim dan generalisasi pada Bab IV dan Bab V;
- memperbaiki DOCX dengan mempertahankan style, numbering, tabel, gambar, caption, field, dan layout;
- menyelesaikan konflik pedoman, sitasi, metodologi, atau perubahan DOCX berisiko tinggi.

Jangan gunakan alur edit DOCX untuk file `.doc` lama. Jangan mengarang data, hasil, sumber, DOI, nomor halaman, metadata PDF, atau kesimpulan penelitian. Jangan memakai aturan ini untuk menyimpulkan bahwa skripsi benar secara metodologis hanya karena bahasanya sudah rapi.

## Scope and Authority

Urutan otoritas ketika aturan berbeda:

1. arahan pembimbing/penguji yang terdokumentasi dan pedoman resmi UNDIP yang berlaku;
2. template UNDIP yang disediakan pengguna, dengan versi dan tanggal dicatat;
3. EYD Edisi Kelima untuk ejaan, huruf, kata, dan tanda baca;
4. gaya sitasi yang disepakati;
5. referensi kerja skill ini.

Jika dua sumber bertentangan, jangan memilih diam-diam. Catat konflik dalam audit, tunjukkan sumber yang dibandingkan, tandai dampaknya, dan minta keputusan pengguna atau pembimbing.

## Required Inputs

Sebelum audit atau penulisan, identifikasi:

- file DOCX sumber dan apakah pengguna mengizinkan audit seluruh dokumen atau hanya bab tertentu;
- folder `references/` proyek yang berisi PDF jurnal/artikel yang benar-benar dipakai;
- bab, subbab, tujuan, dan jenis pekerjaan;
- data, metode, instrumen, sampel, hasil, tabel, gambar, dan batasan penelitian untuk Bab III–V;
- template/pedoman UNDIP yang dipakai dan tanggal versinya;
- gaya sitasi yang digunakan;
- bagian yang tidak boleh disentuh, bila ada.

Jika konteks penting tidak tersedia, lanjutkan hanya pada audit yang dapat dibuktikan dan tandai hal lain `PERLU INFORMASI`. Jangan mengisi kekosongan dengan pengetahuan umum yang tampak masuk akal.

## Non-Negotiable Rules

1. **Audit sebelum edit.** Audit bersifat read-only terhadap DOCX sumber.
2. **Proposal sebelum perubahan.** Setiap perubahan harus memiliki ID audit dan proposal Markdown.
3. **Approval eksplisit.** Persetujuan harus merujuk file/versi proposal dan item yang disetujui. “Lanjutkan” tanpa proposal yang terlihat tidak cukup.
4. **Scope terbatas.** Terapkan hanya item yang disetujui; jangan melakukan perbaikan massal yang tidak terdaftar.
5. **Source immutable.** Default selalu menghasilkan DOCX baru, bukan menimpa file sumber.
6. **Evidence first.** Klaim dari PDF, data, atau pedoman harus dapat ditelusuri ke sumbernya.
7. **No silent strengthening.** Perbaikan bahasa tidak boleh menaikkan kepastian, memperluas populasi, atau mengubah hubungan korelasi menjadi sebab-akibat.
8. **No raw XML editing.** Gunakan kemampuan DOCX yang sesuai; jangan melakukan substitusi string pada ZIP/XML DOCX secara sembarangan.
9. **No publication by default.** Jangan commit, push, upload, atau publish dokumen pengguna, PDF referensi, data, atau identitas mahasiswa.
10. **Uncertainty is a result.** Gunakan `PASS`, `PARTIAL`, `FAIL`, `BELUM TERVERIFIKASI`, atau `PERLU KEPUTUSAN` bila bukti tidak cukup.

## Operating Modes

### Mode A — Writing from supplied material

Gunakan ketika pengguna memberi kerangka atau bahan teks, bukan meminta perubahan DOCX. Tetapkan bab dan subbab, rumuskan ide pokok, susun paragraf, periksa EYD, struktur kalimat, istilah teknis, sitasi, dan tingkat klaim. Tampilkan hasil dengan format output yang sesuai; jangan menambahkan fakta yang tidak ada di bahan.

### Mode B — Read-only DOCX audit

Inventaris DOCX, baca struktur dan isi, periksa aturan bahasa/sumber/format, lalu buat laporan audit Markdown. Jangan membuat salinan hasil edit atau menyimpan perubahan pada DOCX.

### Mode C — Proposal revision

Ubah temuan audit menjadi proposal yang dapat disetujui satu per satu atau per batch kecil. Proposal harus menampilkan sebelum/sesudah, alasan, bukti, risiko, dan dampak format.

### Mode D — Approved DOCX revision

Jalankan hanya setelah approval eksplisit. Salin sumber menjadi output versi baru, terapkan perubahan terbatas, lalu verifikasi terhadap baseline dan proposal.

### Mode E — Complex issue escalation

Gunakan `ai-expert-team` hanya untuk masalah yang benar-benar membutuhkan beberapa perspektif: konflik pedoman, klaim kausal/generalisasi, validasi sitasi yang ambigu, struktur argumen Bab IV–V, atau operasi DOCX berisiko. Hasil council menjadi masukan proposal, bukan izin edit.

## Procedure

### Phase 0 — Establish the case

1. Tentukan mode kerja dan scope.
2. Catat file input, versi, ukuran, dan waktu pemeriksaan.
3. Catat sumber aturan: template UNDIP, EYD, arahan pembimbing, PDF, data penelitian.
4. Tandai informasi yang hilang dan bagian yang tidak boleh diubah.
5. Buat case record bila pekerjaan lebih dari pemeriksaan satu paragraf.

**Completion criterion:** scope, sumber, batasan, dan status informasi tercatat sebelum ada perubahan.

### Phase 1 — Inspect baseline

Untuk DOCX, baca body, tabel, header/footer, heading, style yang digunakan, numbering, captions, gambar, field, komentar, dan tracked changes. Periksa package health. Jangan menyimpulkan layout visual hanya dari ekstraksi teks.

**Completion criterion:** baseline dapat dibaca ulang dan objek yang akan dibandingkan sudah dihitung/dicatat.

### Phase 2 — Audit

Audit dalam urutan: (1) bahasa dan EYD, (2) struktur kalimat/paragraf, (3) kesinambungan argumen, (4) sitasi dan sumber, (5) level klaim, (6) struktur/format UNDIP, (7) integritas DOCX. Buat satu temuan untuk satu masalah yang dapat ditindaklanjuti; gabungkan hanya masalah yang memiliki penyebab dan perubahan sama.

Setiap temuan harus mencantumkan ID, level, lokasi, kutipan, kategori, masalah, aturan/bukti, usulan, dampak, dan status. Jangan menulis “perbaiki bahasa” tanpa menjelaskan bagian yang salah dan bentuk perbaikannya.

**Completion criterion:** semua temuan yang masuk scope memiliki ID stabil dan status.

### Phase 3 — Proposal

Buat proposal berdasarkan audit. Untuk perubahan teks, tampilkan teks sebelum, teks usulan, dan alasan. Untuk perubahan format, tampilkan properti yang akan diubah dan properti yang dipertahankan. Pisahkan P1 bahasa, P2 struktur, P3 sumber/klaim, dan P4 format DOCX bila risiko atau approval-nya berbeda.

**Completion criterion:** pengguna dapat menyetujui atau menolak setiap perubahan tanpa harus menebak scope.

### Phase 4 — Approval

Tampilkan proposal atau ringkasan lengkapnya. Tunggu approval eksplisit yang menyebut proposal dan item, misalnya `setujui proposal-2026-001 P1-001 dan P1-002`. Simpan keputusan, waktu, dan catatan. Jika pengguna hanya menyetujui sebagian, status item lain tetap `MENUNGGU`.

**Completion criterion:** hanya item berstatus `APPROVED` yang masuk edit plan.

### Phase 5 — Conservative edit

Gunakan kemampuan `docx` yang tersedia. Kerjakan perubahan kecil, jaga run formatting dan style, dan simpan ke nama output baru. Jika target teks terpecah antar-run, lakukan pemeriksaan run sebelum mengganti. Jangan menggunakan operasi cell/paragraph yang mereset format tanpa proposal yang menyebut dampaknya.

**Completion criterion:** output dibuat, sumber tetap utuh, dan setiap operasi dapat dipetakan ke item proposal.

### Phase 6 — Verify

Baca ulang output sebagai DOCX. Bandingkan teks target, teks non-target, heading, style, numbering, tabel, gambar, captions, field, komentar, tracked changes, dan package health. Perbarui field/TOC hanya sesuai persetujuan; field mungkin baru dihitung ketika Word/LibreOffice membuka dokumen. Lakukan pemeriksaan visual jika tersedia.

**Completion criterion:** verification report berisi verdict per acceptance criterion dan tidak menyembunyikan keterbatasan.

## Output Contracts

### Audit report

Gunakan `templates/audit-report.md` dan simpan di `audit/`. Minimum:

```markdown
# Audit Skripsi
Status: DRAFT
DOCX sumber: ...
Scope: ...
Pedoman/sumber: ...

## Ringkasan
...

## Temuan
| ID | Level | Lokasi | Kategori | Masalah teramati | Bukti/aturan | Usulan | Dampak | Status |
|---|---|---|---|---|---|---|---|---|
```

### Proposal

Gunakan `templates/proposal-edit.md`. Status awal `DRAFT`; setiap item memiliki `Approval: MENUNGGU`.

### Verification report

Gunakan `templates/verification-report.md`. Wajib menyebut sumber, output, proposal/version, operasi, target/non-target comparison, DOCX health, visual status, verdict, dan unresolved items.

### Writing response

Jika pengguna meminta teks, gunakan:

```markdown
## Teks Revisi
...

## Diagnosis
- Bab/subbab:
- Ide pokok:
- Struktur kalimat: Subjek / Predikat / Objek-Pelengkap / Keterangan
- EYD dan tanda baca:
- Struktur paragraf:
- Status sitasi:
- Status klaim:

## Catatan Batasan
...
```

Jangan memaksa format 4–5 kalimat jika membuat isi berulang. Jika pengguna hanya meminta teks jadi, berikan teks terlebih dahulu dan catatan hanya untuk risiko kebenaran, sumber, atau scope.

## References and Templates

Seluruh aturan panjang, contoh, tabel keputusan, dan format artefak berada di `references/` dan `templates/`. Baca file yang relevan; jangan menjejalkan semua referensi ke setiap tugas. Folder `references/` proyek skripsi adalah tempat PDF pengguna, sedangkan `references/` dalam repo skill berisi pedoman umum dan template kerja.

## Verification Checklist

- [ ] Mode, scope, input, dan batasan tercatat.
- [ ] Audit selesai sebelum edit.
- [ ] Setiap perubahan mempunyai ID audit dan proposal.
- [ ] Approval eksplisit tercatat per item.
- [ ] DOCX sumber tidak tertimpa.
- [ ] Output hanya mengubah scope yang disetujui.
- [ ] EYD dan struktur kalimat diperiksa.
- [ ] Sitasi ditelusuri ke PDF atau ditandai belum terverifikasi.
- [ ] Klaim Bab IV–V sesuai bukti dan batas desain.
- [ ] Aturan UNDIP diperiksa.
- [ ] DOCX dibaca ulang dan package health diverifikasi.
- [ ] Struktur/style/objek non-target dibandingkan.
- [ ] Layout visual diberi status PASS/PARTIAL/FAIL.
- [ ] Semua unresolved item dilaporkan.

## Pitfalls

- Bahasa formal bukan otomatis bahasa yang jelas.
- Jumlah kalimat bukan alasan untuk menambah kalimat tanpa isi.
- Consensus expert bukan bukti.
- PDF yang gagal diekstrak mungkin scan; jangan menganggap isinya kosong.
- DOCX yang berhasil diekstrak belum tentu layout-nya aman.
- Perubahan pada field, numbering, atau caption dapat mengubah banyak halaman; perlakukan sebagai P4.
- Nama metode/model/software tidak otomatis *italic* hanya karena berbahasa Inggris.
- Klaim yang terdengar lebih ilmiah dapat menjadi lebih salah jika terlalu kuat.
- Repo publik hanya boleh memuat skill umum; jangan memasukkan materi skripsi atau PDF berhak cipta.
