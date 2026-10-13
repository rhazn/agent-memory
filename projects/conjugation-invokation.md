# Conjugation Invocation

## Recent Decisions

- 2026-09-10: Session time excludes pause intervals. A submit action while paused must persist a `resume` event before recording the submission. A one-time migration repairs historical orphaned pauses using the first subsequent submission timestamp.
- 2026-10-13: Added `passe_recent` (🕒 Passé récent) and `futur_simple` (🔮 Futur simple) for all 124 CSV verbs: 1,468 forms, with only third-person singular for falloir/pleuvoir. Uses traditional future spellings, one standard variant, and existing reflexive answer conventions. Default weight is 1; saved selections require enabling new tenses. Error-table tense cells now use shared formatted labels. Added `npm test` data validation; tests, lint, and build passed.

## Known Data Issues

- 2026-10-13: Existing `rester.csv` passé composé incorrectly uses avoir; `ouvrir.csv` tu imperative is `ouvres` instead of `ouvre`. Reported to user; not changed in the tense-addition task.
