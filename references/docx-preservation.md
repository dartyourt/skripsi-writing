# DOCX Preservation and Verification

## Principle

A DOCX is a package containing XML parts, relationships, styles, numbering, media, and fields. A text extraction success does not prove that Word layout or package behavior remains correct.

## Before edit

Record:

- source path, filename, size, hash if required by project;
- package health;
- section/page settings if available;
- paragraph/heading/style counts;
- table and image counts;
- captions and numbering;
- headers/footers and fields;
- comments and tracked changes;
- target paragraphs/runs and exact scope.

## Safe editing rules

- Use the available `docx` skill scripts or a library that preserves the required structures.
- Keep source immutable and write a versioned output.
- Preserve paragraph styles rather than replacing content with plain text.
- Preserve run-level bold/italic/underline, language, and formatting when changing a phrase.
- Normalize fragmented runs only when needed and after checking that it will not alter formatting.
- Avoid `cell.text = ...` for cells whose formatting matters.
- Do not unzip and perform raw search/replace in XML.
- Treat changes to headings, captions, numbering, fields, tables, section breaks, headers/footers, and images as higher risk.
- Do not claim that TOC or page numbers are updated until Word/LibreOffice recalculates them.

## Verification layers

### Layer 1 — Package

Run the DOCX health check if available. Confirm the output opens as a ZIP/package and required relationships/styles are intact.

### Layer 2 — Text and scope

Re-read output. Confirm approved replacement exists, old text is removed only at approved locations, and non-target text is unchanged. Compare headings, paragraphs, tables, captions, and list markers.

### Layer 3 — Object preservation

Compare counts and identities of tables, figures, embedded media, comments, tracked changes, fields, headers/footers, and styles. Unexpected changes are `FAIL` or `PERLU KEPUTUSAN`, not silently accepted.

### Layer 4 — Visual

Open/render with Word or LibreOffice when layout matters. Check margins, page breaks, table overflow, captions, heading spacing, image size, equation alignment, source-code font, and TOC. If no renderer is available, report `PARTIAL`.

## Change ledger

| Operation ID | Proposal ID | Location | Operation | Expected effect | Actual verification | Verdict |
|---|---|---|---|---|---|---|
| OP-001 | P1-001 | ... | ... | ... | ... | ... |

## Failure handling

- If the output fails package validation, do not deliver it as revised; return the error and preserve the source.
- If formatting changes outside scope, revert the output and narrow the edit method.
- If visual verification is unavailable, do not use `PASS` for layout.
- If Word recalculation is needed, state the exact manual step the user must perform.
