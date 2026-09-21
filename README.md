# Skripsi Writing — UNDIP Informatika

## What this skill solves

Skill ini menyediakan workflow terkontrol untuk menulis, mengaudit, dan merevisi skripsi S1 Informatika UNDIP dalam DOCX tanpa melakukan perubahan diam-diam. Ia menggabungkan pemeriksaan bahasa Indonesia/EYD, struktur argumen, validasi sumber dari PDF proyek, kalibrasi klaim penelitian, dan preservasi struktur Word.

## Why this is a skill

Tanpa workflow ini, model cenderung langsung menulis ulang paragraf atau DOCX, meratakan format run, mengarang sitasi, memiringkan semua istilah Inggris, dan membuat klaim Bab IV–V terlalu kuat. Skill ini memberi batas operasional, artefak audit/proposal/verifikasi, approval gate, dan prosedur fallback yang dapat diulang.

## Use when

Gunakan saat mengaudit atau merevisi skripsi `.docx`, menulis bagian skripsi dari bahan yang diberikan, memeriksa EYD/struktur kalimat, memvalidasi sitasi berdasarkan PDF, meninjau klaim Bab IV–V, atau menyelesaikan konflik pedoman yang kompleks.

## Expected outputs

- case record bila scope kompleks;
- `audit/*.md` sebelum edit;
- `proposals/*.md` dengan before/after, bukti, risiko, dan approval;
- DOCX output versi baru hanya untuk proposal yang disetujui;
- `audit/verification-*.md` dengan verdict PASS/PARTIAL/FAIL;
- daftar unresolved items dan tindakan pengguna.

## Context requirements

Sediakan DOCX sumber, folder PDF proyek, bab/subbab, data/metode/hasil yang relevan, template/pedoman UNDIP, dan arahan pembimbing bila ada. Jangan menebak konteks yang hilang.

## Example prompts

Lihat [`tests/prompts.md`](tests/prompts.md) untuk positive, edge-case, dan negative prompts.

## Repository layout

```text
skripsi-writing/
├── SKILL.md
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore
├── references/
│   ├── README.md
│   ├── writing-rules.md
│   ├── eyd-edisi-kelima.md
│   ├── citation-and-source-audit.md
│   ├── foreign-terms-and-italic.md
│   ├── claim-calibration.md
│   ├── undip-informatika-template.md
│   ├── docx-preservation.md
│   └── ai-expert-team-protocol.md
├── templates/
│   ├── case-record.md
│   ├── audit-report.md
│   ├── proposal-edit.md
│   └── verification-report.md
└── tests/prompts.md
```

PDF dan DOCX pengguna berada di folder kerja skripsi, bukan di repository skill.

## Installation

### Hermes local skill

Salin folder repo ke direktori skill Hermes, lalu buka sesi baru agar loader memuat versi terbaru. Folder lokal dapat digunakan tanpa ClawHub.

### GitHub public

```bash
git clone https://github.com/dartyourt/skripsi-writing.git
```

Salin folder hasil clone ke direktori skill agent yang kompatibel. Repo public sengaja hanya berisi aturan umum dan template kosong; jangan menambahkan naskah atau PDF privat.

### ClawHub

Skill ini tidak dipublikasikan ke ClawHub. Gunakan GitHub atau instalasi lokal.

## Privacy and licensing

Jangan commit DOCX, PDF jurnal berhak cipta, data penelitian, identitas mahasiswa, komentar pembimbing, audit kasus nyata, atau proposal pengguna. Isi skill dan dokumentasi memakai MIT sesuai metadata repo; referensi EYD hanya dirujuk melalui sumber dan harus mengikuti lisensi sumbernya. Periksa lisensi sebelum menyalin materi eksternal.

## Limitations

Python/docx dapat mempertahankan banyak struktur, tetapi bukan pengganti Word/LibreOffice untuk rendering final. TOC, page numbers, numbering, dan field dapat perlu recalculation. Jika visual tidak diperiksa, laporkan `PARTIAL`.

## Contributing

Perubahan aturan harus menambah contoh, acceptance criteria, atau batasan yang dapat diverifikasi; jangan hanya menambah slogan. Perbarui SKILL.md, referensi terkait, template/eval prompt bila perilaku berubah, CHANGELOG, lalu jalankan pemeriksaan link/frontmatter dan `git status` untuk memastikan tidak ada data privat.

## License

MIT. See [`LICENSE`](LICENSE).
