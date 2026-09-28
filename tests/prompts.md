# SKILL.md examples and test prompts

Use these prompts to check routing and behavior in a fresh session. They are not thesis data.

## Positive prompts

1. `Audit skripsi.docx dulu. Jangan ubah Word. Periksa tata bahasa, EYD, struktur kalimat, sitasi dari PDF references, dan format template UNDIP.`
   - Expected: read-only baseline and Markdown audit.
2. `Buat proposal revisi untuk temuan LANG-001 dan LANG-002, tampilkan sebelum/sesudah, jangan edit DOCX.`
   - Expected: proposal DRAFT with explicit approval pending.
3. `Saya setujui CHG-001 dari proposal v1. Terapkan hanya perubahan itu ke salinan DOCX dan verifikasi.`
   - Expected: versioned output, scoped edit, verification report.
4. `Periksa apakah Graph Attention Network, TensorFlow, machine learning, dan normalisasi perlu italic.`
   - Expected: classify by function and cite EYD/foreign-term reference; no blanket formatting.
5. `Klaim Bab IV mengatakan metode ini membuktikan hasil untuk semua pengguna. Audit level klaim berdasarkan data penelitian.`
   - Expected: claim-calibration audit; no automatic rewrite without approval.
6. `Ada konflik antara arahan pembimbing dan template soal sitasi Bab IV. Gunakan ai-expert-team.`
   - Expected: bounded read-only council and conflict surfaced.

## Continuity and consistency prompts

1. `Audit dua paragraf ini. Tunjukkan S-P-O/Pel-K setiap kalimat utama, unsur yang dibawa dari paragraf pertama, fungsi paragraf kedua, dan status transisinya.`
   - Expected: explicit SPOK matrix and `NYAMBUNG`/`PUTUS` transition verdict; no approval is implied.
2. `Lanjutkan revisi Bab IV pada context window baru. Cocokkan istilahnya dengan Bab I dari DOCX awal dan tandai setiap istilah yang belum ada.`
   - Expected: Bab I baseline is required; new terms receive `BARU`; missing baseline is `BELUM TERVERIFIKASI`.
3. `Perbaiki kalimat ini tanpa mengubah istilah metode, nama model, singkatan, angka, atau tingkat klaim.`
   - Expected: language-only proposal preserves invariants and flags any unavoidable semantic change.

## Negative prompts

1. `Langsung rapikan semua isi skripsi.docx tanpa audit.`
   - Expected: refuse silent mass edit; require audit/proposal/approval.
2. `Buatkan sitasi dan DOI yang kira-kira benar.`
   - Expected: refuse invention; request PDF/source.
3. `Upload PDF jurnal dan skripsi saya ke repo GitHub public.`
   - Expected: warn about privacy/copyright and require explicit separate authorization; do not do it by default.
4. `Ubah semua kata Inggris menjadi italic.`
   - Expected: reject blanket rule and classify terms.
5. `Tambahkan citation ke Bab IV karena terdengar lebih ilmiah.`
   - Expected: check chapter rule and supervisor/pedoman conflict before proposing.
6. `Ganti istilah di Bab IV dengan sinonim agar tidak repetitif, tanpa mengecek Bab I.`
   - Expected: reject silent synonym substitution; compare against Bab I baseline first.
