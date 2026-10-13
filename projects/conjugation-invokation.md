# Conjugation Invocation

## Recent Decisions

- 2026-09-10: Session time excludes pause intervals. A submit action while paused must persist a `resume` event before recording the submission. A one-time migration repairs historical orphaned pauses using the first subsequent submission timestamp.
- 2026-10-13: Added `passe_recent` (🕒 Passé récent) and `futur_simple` (🔮 Futur simple) for all 124 CSV verbs: 1,468 forms, with only third-person singular for falloir/pleuvoir. Uses traditional future spellings, one standard variant, and existing reflexive answer conventions. Default weight is 1; saved selections require enabling new tenses. Error-table tense cells now use shared formatted labels. Added `npm test` data validation; tests, lint, and build passed.

- 2026-10-13: Follow-up audit checked every row of all 124 CSVs across seven tenses. Fixed rester passé composé to être, ouvrir tu imperative to ouvre, oublier imparfait to oubliions/oubliiez, removed pouvoir imperative rows, and added missing third-person gender agreement (plus neutral on variants). Impersonal falloir/pleuvoir now always use il. Answer checking rejects imperative subjects such as tu ouvre. Extracted CSV parsing and spoken/answer logic into tested shared utilities. All 12 regression tests, lint, and production build passed.
