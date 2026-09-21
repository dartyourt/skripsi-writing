# References folder policy

Folder `references/` di **proyek skripsi pengguna** adalah tempat PDF jurnal/artikel yang benar-benar dipakai. Jangan mencampurnya dengan referensi umum di folder skill.

## Per-PDF provenance

Catat:

- filename;
- judul, penulis, tahun, DOI/URL jika tersedia;
- bab/subbab yang menggunakan sumber;
- claim ID yang didukung;
- lisensi/status akses;
- text layer/OCR status;
- tanggal validasi;
- status: verified/partial/unverified.

## Privacy

Jangan memasukkan DOCX skripsi, PDF berhak cipta, skripsi contoh, data penelitian, identitas, komentar pembimbing, audit, atau proposal pengguna ke repo skill publik. `.gitignore` root skill mengecualikan tipe file umum, tetapi periksa `git status` sebelum commit; ignore bukan pengganti audit.

## Public skill repository

Repo publik hanya berisi instruksi umum, referensi tautan yang boleh dibagikan, ringkasan aturan, template kosong, dan dokumentasi. PDF EYD atau PDF jurnal tidak perlu disalin jika tautan sumber sudah cukup dan lisensinya tidak mengizinkan redistribusi.