# Citation and Source Audit

## Scope

Gunakan untuk Bab I–II dan bagian lain jika pedoman pembimbing mengharuskan sitasi. Sumber utama harus berasal dari PDF jurnal/artikel yang pengguna tempatkan di folder `references/` proyek skripsi, atau sumber lain yang secara eksplisit diberikan.

## Source inventory

Buat inventaris PDF sebelum menyatakan sitasi valid:

| Source ID | File | Metadata yang tersedia | Bab/subbab | Lisensi/akses | Text layer/OCR | Status |
|---|---|---|---|---|---|---|
| REF-001 | ... | penulis/tahun/judul/DOI | ... | ... | ... | ... |

Jika PDF scan, gagal dibaca, terenkripsi, atau metadata tidak lengkap, catat keadaan itu. `Tidak ada teks hasil ekstraksi` bukan bukti bahwa sumber tidak memiliki isi.

## Claim-to-source matrix

Untuk setiap klaim bersitasi, buat baris:

| Claim ID | Lokasi | Klaim naskah | Sitasi | Source ID | Bukti langsung | Inferensi | Status |
|---|---|---|---|---|---|---|---|

Status yang diperbolehkan: `SESUAI`, `SEBAGIAN`, `TIDAK SESUAI`, `BELUM TERVERIFIKASI`, `SUMBER HILANG`, `PERLU KEPUTUSAN`.

## Rules

- Jangan membuat penulis, tahun, judul, DOI, URL, volume, halaman, atau hasil.
- Bedakan pernyataan eksplisit dari sumber dan kesimpulan yang dibuat dari sumber.
- Jangan memperluas populasi, konteks, metode, atau hasil paper.
- Jika paper hanya mendukung korelasi, jangan menulis kausalitas.
- Jika metadata dalam naskah berbeda dengan PDF, laporkan konflik; jangan memperbaiki berdasarkan tebakan.
- Daftar pustaka harus ditelusuri balik ke sitasi dan sumber yang tersedia.
- Sumber di folder kerja privat tidak otomatis boleh disalin ke repo publik.

## Chapter handling

### Bab I–II

Validasi klaim bersitasi terhadap PDF. Jika tidak tersedia, gunakan `[perlu validasi sumber]` atau status audit, bukan sitasi buatan.

### Bab III–V

Aturan kerja skripsi ini tidak menambahkan sitasi baru pada Bab III, Bab IV, dan Bab V; gunakan metode, data, hasil, analisis, dan kesimpulan penelitian. Jika pedoman atau pembimbing meminta sitasi, catat sebagai konflik dan minta keputusan. Jangan menghapus sitasi lama diam-diam.

## Verification

Sitasi baru hanya boleh masuk proposal jika source ID, bukti, dan statusnya tercatat. Sitasi dianggap terverifikasi hanya setelah PDF atau sumber yang diberikan benar-benar diperiksa.