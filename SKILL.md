---
name: skripsi-writing
description: Audit and revise UNDIP thesis DOCX safely.
version: 0.4.0
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

Untuk pekerjaan lintas paragraf, lintas subbab, atau lintas context window, tambahkan:

- DOCX skripsi awal, terutama Bab I, sebagai baseline istilah dan pola penyebutan;
- daftar istilah acuan: istilah utama, bentuk lengkap–singkatan, nama variabel, nama kelas, nama metode/model, dan padanan bahasa Indonesia;
- bagian atau paragraf sebelumnya yang menjadi sumber transisi bagi bagian yang akan direvisi.

Jika konteks penting tidak tersedia, lanjutkan hanya pada audit yang dapat dibuktikan dan tandai hal lain `PERLU INFORMASI`. Jangan mengisi kekosongan dengan pengetahuan umum yang tampak masuk akal.

## Non-Negotiable Rules

1. **Audit sebelum edit.** Audit bersifat read-only terhadap DOCX sumber.
2. **Proposal sebelum perubahan.** Setiap perubahan harus memiliki ID audit dan proposal Markdown.
3. **Approval eksplisit.** Persetujuan harus merujuk file/versi proposal dan item yang disetujui. “Lanjutkan” tanpa proposal yang terlihat tidak cukup.
4. **Scope terbatas.** Terapkan hanya item yang disetujui; jangan melakukan perbaikan massal yang tidak terdaftar.
5. **Source immutable.** Default selalu menghasilkan DOCX baru, bukan menimpa file sumber.
6. **Evidence first.** Klaim dari PDF, data, atau pedoman harus dapat ditelusuri ke sumbernya.
7. **Citation per external claim.** Definisi, fakta teknis, deskripsi metode terdahulu, angka, hasil, dan klaim yang tidak berasal dari observasi/eksperimen pengguna harus dapat ditelusuri ke sumber. Sitasi tidak harus diulang pada setiap kalimat jika beberapa kalimat berturut-turut masih merujuk pada sumber dan klaim yang sama; ulangi ketika sumber, klaim, atau paragraf berubah.
8. **No silent strengthening.** Perbaikan bahasa tidak boleh menaikkan kepastian, memperluas populasi, atau mengubah hubungan korelasi menjadi sebab-akibat.
9. **No raw XML editing.** Gunakan kemampuan DOCX yang sesuai; jangan melakukan substitusi string pada ZIP/XML DOCX secara sembarangan.
10. **No publication by default.** Jangan commit, push, upload, atau publish dokumen pengguna, PDF referensi, data, atau identitas mahasiswa.
11. **Uncertainty is a result.** Gunakan `PASS`, `PARTIAL`, `FAIL`, `BELUM TERVERIFIKASI`, atau `PERLU KEPUTUSAN` bila bukti tidak cukup.
12. **SPOK harus dapat diaudit.** Untuk setiap kalimat utama, identifikasi subjek, predikat, objek/pelengkap, keterangan, hubungan klausa, dan rujukan. Jangan menerima subjek atau rujukan yang hanya dapat ditebak dari konteks.
13. **Predikat harus lengkap.** Jika predikat menuntut objek atau pelengkap, unsur tersebut harus disebutkan. Jika predikat berupa verba pasif, pastikan pelaku, sasaran, atau fokus proses tidak menjadi kabur.
14. **Satu kalimat memiliki satu pusat informasi.** Pecah kalimat jika terdapat lebih dari satu gagasan utama, perpindahan subjek tanpa penanda, rantai klausa yang mengaburkan predikat, atau hubungan sebab-akibat yang tidak jelas.
15. **Utamakan SPOK eksplisit dan verba konkret.** Hapus atau integrasikan keterangan yang hanya mengulang hubungan makna atau menyamarkan pelaku. Ganti verba abstrak atau bergaya mesin dengan verba konkret yang sesuai makna, tetapi pertahankan keterangan yang memuat waktu, tempat, cara, sebab, tujuan, syarat, atau batasan yang diperlukan.
16. **Kalimat pertama menyatakan fungsi paragraf.** Paragraf harus membuka dengan ide pokok atau klaim yang jelas, bukan konteks yang tidak mengarahkan pembaca.
17. **Transisi harus berbasis makna.** Kalimat pertama paragraf baru wajib mengambil, mempersempit, menjawab, mengembangkan, membandingkan, atau membatasi unsur yang diperkenalkan pada paragraf sebelumnya. Konjungsi saja tidak cukup.
18. **Pasangan paragraf wajib diuji dua arah.** Audit harus mencatat `unsur dibawa → fungsi paragraf berikutnya → alasan urutan`. Tandai `PUTUS` jika paragraf berikutnya dapat dipindahkan tanpa mengubah makna hubungan.
19. **Bab I menjadi baseline lintas sesi.** Jika pekerjaan berlanjut pada context window atau percakapan lain, istilah, definisi, singkatan, nama variabel, nama kelas, nama metode/model, dan pola penyebutan harus dicocokkan dengan DOCX skripsi awal, terutama Bab I.
20. **Jangan mengganti istilah acuan demi variasi.** Sinonim hanya boleh digunakan jika tidak mengubah konsep, ruang lingkup, tingkat abstraksi, atau makna operasional. Jika berpotensi mengubah identitas konsep, pertahankan istilah Bab I.
21. **Istilah baru harus ditandai.** Setiap istilah yang tidak ditemukan pada baseline Bab I diberi status `BARU`, alasan penggunaannya dicatat, dan konsistensinya diperiksa sebelum masuk ke naskah.
22. **Ketidakkonsistenan harus dicatat sebelum diperbaiki.** Catat istilah lama, istilah baru, lokasi keduanya, keputusan yang dipilih, dan risiko makna. Jangan mengganti secara diam-diam.

## Operating Modes

### Mode A — Writing from supplied material

Gunakan ketika pengguna memberi kerangka atau bahan teks, bukan meminta perubahan DOCX. Tetapkan bab dan subbab, rumuskan ide pokok, susun paragraf, periksa EYD, struktur kalimat, istilah teknis, sitasi, dan tingkat klaim. Untuk pendahuluan, petakan setiap paragraf ke fungsi piramida: pentingnya topik, masalah umum, masalah khusus, pendekatan yang ada, keterbatasan/gap, atau tujuan/solusi. Tampilkan hasil dengan format output yang sesuai; jangan menambahkan fakta yang tidak ada di bahan.

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
6. Jika pekerjaan lintas paragraf atau lintas bab, buat baseline istilah Bab I dan peta kesinambungan paragraf.

**Completion criterion:** scope, sumber, batasan, status informasi, baseline istilah, dan kebutuhan transisi tercatat sebelum ada perubahan.

### Phase 0A — Build the language and continuity baseline

Untuk pekerjaan yang melibatkan lebih dari satu paragraf atau lebih dari satu bab, buat baseline berikut sebelum mengusulkan revisi:

- **Peta fungsi paragraf:** pembuka, definisi, konteks masalah, penjelasan, bukti, perbandingan, metode, hasil, pembatasan, atau implikasi;
- **Matriks SPOK:** subjek, predikat, objek/pelengkap, keterangan, hubungan klausa, dan rujukan untuk setiap kalimat utama;
- **Matriks transisi:** kalimat/konsep penutup paragraf A, unsur yang dibawa, fungsi paragraf B, dan status `NYAMBUNG` atau `PUTUS`;
- **Kamus istilah Bab I:** bentuk baku, singkatan, kapitalisasi, bentuk tunggal/jamak, padanan bahasa Indonesia, dan lokasi penggunaan pertama;
- **Daftar invariants:** angka, sitasi, nama metode/model, nama kelas, definisi, batasan, dan klaim yang tidak boleh berubah tanpa proposal terpisah.

Jika DOCX skripsi awal atau Bab I tidak tersedia, status konsistensi lintas bab harus `BELUM TERVERIFIKASI`. Jangan menganggap istilah yang tampak serupa sebagai istilah yang sama.

**Completion criterion:** baseline SPOK, transisi, istilah, dan invariants tersedia atau setiap bagian yang belum tersedia diberi status `BELUM TERVERIFIKASI`.

### Phase 1 — Inspect baseline

Untuk DOCX, baca body, tabel, header/footer, heading, style yang digunakan, numbering, captions, gambar, field, komentar, dan tracked changes. Untuk pekerjaan lintas sesi, baca Bab I terlebih dahulu dan ekstrak istilah acuan sebelum membaca bagian target. Periksa package health. Jangan menyimpulkan layout visual hanya dari ekstraksi teks.

**Completion criterion:** baseline dapat dibaca ulang dan objek yang akan dibandingkan sudah dihitung/dicatat.

### Phase 2 — Audit

Audit dalam urutan: (1) bahasa dan EYD, (2) SPOK dan struktur klausa, (3) fungsi paragraf, (4) transisi antarparagraf, (5) konsistensi istilah lintas bab/sesi, (6) kesinambungan argumen, (7) sitasi dan sumber, (8) level klaim, (9) struktur/format UNDIP, (10) integritas DOCX. Buat satu temuan untuk satu masalah yang dapat ditindaklanjuti; gabungkan hanya masalah yang memiliki penyebab dan perubahan sama.

Setiap temuan harus mencantumkan ID, level, lokasi, kutipan, kategori, masalah, aturan/bukti, usulan, dampak, dan status. Jangan menulis “perbaiki bahasa” tanpa menjelaskan bagian yang salah dan bentuk perbaikannya.

Untuk temuan SPOK dan alur, audit wajib menyebutkan:

- struktur `S-P-O/Pel-K` aktual dan unsur yang hilang, kabur, atau berganti;
- pusat informasi kalimat dan alasan kalimat dipertahankan, dipecah, atau disusun ulang;
- anteseden setiap kata rujukan seperti “ini”, “itu”, “tersebut”, “hal tersebut”, dan “mereka”;
- konsep yang dibawa dari paragraf sebelumnya, fungsi paragraf berikutnya, dan alasan hubungan tersebut logis;
- istilah Bab I yang menjadi acuan serta setiap penyimpangan bentuk, singkatan, kapitalisasi, atau makna.

**Completion criterion:** semua temuan yang masuk scope memiliki ID stabil dan status.

### Phase 3 — Proposal

Buat proposal berdasarkan audit. Untuk perubahan teks, tampilkan teks sebelum, teks usulan, dan alasan. Untuk perubahan format, tampilkan properti yang akan diubah dan properti yang dipertahankan. Untuk perubahan paragraf, tampilkan juga fungsi paragraf, hubungan transisi sebelum–sesudah, dan istilah acuan Bab I yang dipertahankan. Pisahkan P1 bahasa, P2 struktur, P3 sumber/klaim, dan P4 format DOCX bila risiko atau approval-nya berbeda.

**Completion criterion:** pengguna dapat menyetujui atau menolak setiap perubahan tanpa harus menebak scope.

### Phase 4 — Approval

Tampilkan proposal atau ringkasan lengkapnya. Tunggu approval eksplisit yang menyebut proposal dan item, misalnya `setujui proposal-2026-001 P1-001 dan P1-002`. Simpan keputusan, waktu, dan catatan. Jika pengguna hanya menyetujui sebagian, status item lain tetap `MENUNGGU`.

**Completion criterion:** hanya item berstatus `APPROVED` yang masuk edit plan.

### Phase 5 — Conservative edit

Gunakan kemampuan `docx` yang tersedia. Kerjakan perubahan kecil, jaga run formatting dan style, dan simpan ke nama output baru. Jika target teks terpecah antar-run, lakukan pemeriksaan run sebelum mengganti. Jangan menggunakan operasi cell/paragraph yang mereset format tanpa proposal yang menyebut dampaknya.

**Completion criterion:** output dibuat, sumber tetap utuh, dan setiap operasi dapat dipetakan ke item proposal.

### Phase 6 — Verify

Baca ulang output sebagai DOCX. Bandingkan teks target, teks non-target, heading, style, numbering, tabel, gambar, captions, field, komentar, tracked changes, dan package health. Ulangi pemeriksaan matriks SPOK, pasangan transisi, kamus istilah Bab I, dan daftar invariants. Perbarui field/TOC hanya sesuai persetujuan; field mungkin baru dihitung ketika Word/LibreOffice membuka dokumen. Lakukan pemeriksaan visual jika tersedia.

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
- Fungsi paragraf dalam alur umum-ke-khusus: pentingnya topik / masalah umum / masalah khusus / pendekatan / gap / tujuan
- Ide pokok:
- Struktur kalimat: Subjek / Predikat / Objek-Pelengkap / Keterangan
- Istilah teknis: apa objeknya / kapan digunakan / informasi yang diberikan / penggunaannya dalam penelitian
- Transisi antarparagraf:
- EYD dan tanda baca:
- Struktur paragraf:
- Status sitasi:
- Status klaim:

## Catatan Batasan
...
```

Untuk pendahuluan, jangan melompat dari definisi istilah langsung ke model. Pastikan masalah umum dan masalah khusus sudah dijelaskan, metode konvensional sudah dibandingkan dengan pendekatan otomatis, dan alasan pemilihan setiap arsitektur terlihat. Jika pengguna hanya meminta teks jadi, berikan teks terlebih dahulu dan catatan hanya untuk risiko kebenaran, sumber, atau scope.

## References and Templates

Seluruh aturan panjang, contoh, tabel keputusan, dan format artefak berada di `references/` dan `templates/`. Baca file yang relevan; jangan menjejalkan semua referensi ke setiap tugas. Folder `references/` proyek skripsi adalah tempat PDF pengguna, sedangkan `references/` dalam repo skill berisi pedoman umum dan template kerja.

## Verification Checklist

- [ ] Mode, scope, input, dan batasan tercatat.
- [ ] Baseline Bab I tersedia atau status `BELUM TERVERIFIKASI` dinyatakan.
- [ ] Audit selesai sebelum edit.
- [ ] Setiap perubahan mempunyai ID audit dan proposal.
- [ ] Approval eksplisit tercatat per item.
- [ ] DOCX sumber tidak tertimpa.
- [ ] Output hanya mengubah scope yang disetujui.
- [ ] EYD dan struktur kalimat diperiksa.
- [ ] Setiap kalimat utama memiliki subjek dan predikat yang jelas.
- [ ] Objek/pelengkap diperiksa sesuai tuntutan predikat.
- [ ] Kata rujukan memiliki anteseden yang jelas.
- [ ] Setiap pasangan paragraf memiliki unsur yang dibawa dan fungsi lanjutan yang dapat dijelaskan.
- [ ] Kalimat pertama paragraf baru tersambung secara makna, bukan hanya memakai konjungsi.
- [ ] Istilah, singkatan, nama model, nama kelas, dan definisi konsisten dengan Bab I.
- [ ] Istilah baru ditandai `BARU` dan tidak masuk diam-diam.
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
