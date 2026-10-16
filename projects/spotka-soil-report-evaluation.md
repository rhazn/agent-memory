# Spotka soil-report evaluation

- Repository: `/Users/pheltweg/development/projects/diffforge/spotka/2026-spotka-baugrundgutachten`.
- 2026-10-16: User wants an offline, self-contained HTML editor for manually authoring evaluation ground truth without sending private laboratory PDFs to an LLM.
- Schemas live under `evals/schemas/`; first report is an array of soil samples with one `id` field each. Every extracted leaf uses `{ value: string|null, confidence: number, error: boolean, errorMessage: string|null, witness: array }`. Successful values are raw strings, including numbers; conversion happens downstream. Errors require null values.
- Initial UI asks only for values. New readings use confidence 1, error false, errorMessage null, witness []. Imported metadata must be preserved.
- Editor opens supported JSON Schemas plus referenced local schema files, and optionally existing ground truth. Save back when browser file access permits; otherwise download or copy. No PDF viewer or metadata-entry UI in the first version.
- Editor: `evals/tools/ground-truth-editor.html`; regenerate from template/core/schema sources with `pnpm eval:editor:build`. Existing table evaluation remains separate.
