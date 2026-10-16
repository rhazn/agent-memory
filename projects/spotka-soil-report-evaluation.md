# Spotka soil-report evaluation

- Repository: `/Users/pheltweg/development/projects/diffforge/spotka/2026-spotka-baugrundgutachten`.
- 2026-10-16: User wants an offline, self-contained HTML editor for manually authoring evaluation ground truth without sending private laboratory PDFs to an LLM.
- Schemas live under `evals/schemas/`; reports are arrays of soil samples. Every extracted leaf uses `{ value: string|null, confidence: number, error: boolean, errorMessage: string|null, witness: array }`. Successful values are raw strings, including numbers; conversion happens downstream. Errors require null values.
- 2026-10-16: Full schema replaces placeholder `id` with `probenbezeichnung`, then `entnahmestelle`, `entnahmetiefe`, `schlaemkornanteil`, `tonanteil`, `massenanteil` (sand, kies, schluff, steine), `gruppensymbol-din-18196`, `kornkennzahl`, `durchlaessigkeit-beyer` (locker, mitteldicht, dicht). All 14 leaves use the reading wrapper.
- Initial UI asks only for values. New readings use confidence 1, error false, errorMessage null, witness []. Imported metadata must be preserved.
- Editor opens supported JSON Schemas plus referenced local schema files, and optionally existing ground truth. Save back when browser file access permits; otherwise download or copy. No PDF viewer or metadata-entry UI in the first version.
- Editor: `evals/tools/ground-truth-editor.html`; regenerate from template/core/schema sources with `pnpm eval:editor:build`. Existing table evaluation remains separate.
