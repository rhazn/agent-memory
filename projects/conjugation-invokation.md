# Conjugation Invocation

## Recent Decisions

- 2026-09-10: Session time excludes pause intervals. A submit action while paused must persist a `resume` event before recording the submission. A one-time migration repairs historical orphaned pauses using the first subsequent submission timestamp.
