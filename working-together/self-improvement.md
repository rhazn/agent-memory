# Personal setup reviews

## Review preferences

- Philip triggers periodic reviews manually. Review his personal setup and
  cross-project way of working, not the setup of each project. Freelance project
  instructions may be outside his control. Surface conflicts as evidence and
  improve his own setup's response to them.
- Start with freeform feedback, inspect session conversations, and discuss findings
  in small batches. Cover all nine areas, even when opening feedback identifies
  particular priorities. Agree the period and sample with him.
- Every reply in a guided review must give the current step, what remains to
  finish it, and the next step. Philip may leave and return after half an hour;
  status must not depend on remembering the preceding reply. At closure, state
  that the review is complete and no steps remain.
- CV publication was a valid example to highlight. Philip did not want a change
  for that incident; do not exclude similar evidence from future reviews.
- End with an explicit message that the review is over. Summarize what was
  discussed and decided, applied changes, and commit/push status.
- Explicitly review and consolidate shared memory each time, including what
  belongs in `SOUL.md` and `WORKING-TOGETHER.md`. Move important durable lessons
  to their appropriate home without forcing core-document changes at every review.
- Starting with the next review, make memory consolidation a feedback discussion:
  read the memory, describe the high-level impression it gives of Philip and how
  to work with him, then invite his corrections before adapting the memory.
  Review the resulting understanding, not just file organization.

## Latest audit

16 November 2026. Window: 11-16 November 2026.

Local OpenCode inventory found 30 root sessions updated in the window. Scanned
user-turn previews in 26 completed candidate sessions and inspected selected
assistant/tool sequences more deeply, including three coding tasks. This was a
selective review, not complete transcript coverage. Pi and Agent Box sessions
were not inspected.

Decisions and applied changes:
- Philip reports delegated memory learning works well and needless caveats
  improved. Sentence cadence remained poor. Kept ASD-STE100 recommended for direct
  harness replies, excluded it from authored prose unless explicitly requested,
  required disclosure of actual use, and added natural-rhythm writing guidance.
- Clarified goal checks before substantial or complex work without adding an
  approval gate to small tasks or blocking deliberate exploratory research.
- Preserved progress messages and model defaults. Philip reports bugs after GLM
  coding but cannot use GPT exclusively because of quota limits.
- Restored OpenCode transcript detail with `session.verbosity: "high"`. Added an
  explicitly requested `budget` subagent using GLM-5.3 max without native fallback.
  Local registration and installed-source checks passed; actual delegated work
  and visual TUI behavior were not tested in this review.
- Consolidated overlapping collaboration guidance and improved writing retrieval.
  Reviewed `SOUL.md`; its existing principles needed no change.
- Updated the review skill to explicitly inspect core-memory consolidation and
  require current-step, remaining-work, and next-step status in every reply.
  Philip otherwise judged this meeting useful, with no further unresolved feedback.
- Configuration and skills were synced locally. No Agent Box sync was requested.

## Check at the next review

Discuss context load from memory retrieval, skill loading, and shared instructions.
Philip worries that routine tasks read too much, but excess or harm is not yet
established. Inspect representative task starts and what guidance was actually
loaded before proposing guardrails. Discuss progressive disclosure, a short
baseline, selective deeper retrieval, and regular shortening, consolidation, and
deletion. Assess whether the existing structure achieves that goal. This is an
agenda item for the next review, not authorization to redesign retrieval now.

Budget-agent experiment: check whether Philip remembered to request the named
`budget` subagent, whether that was easier than manual model switching, and how
GLM-5.3 max performed on the delegated work. Look for bugs, parent review/rework,
and quota blockers. It has no automatic Luna fallback. Do not infer success from
configuration alone or add automatic delegation without discussion.

Check whether the applied writing changes improve sentence rhythm and keep
ASD-STE100 out of authored prose unless requested. Assess whether earlier goal
checks prevent wasted substantial work without over-questioning simple tasks.
The effects of these changes across later sessions are not yet established.

Revisit useless hedging, incidental timestamps and defensive documentation using
the Frigate pinning example. Philip explicitly wants these exact sentences
discussed as poor writing:

> On November 17, 2026, the registry manifests for `stable` and `0.18.2` had the same digest.
> This identifies the current stable release; it does not establish compatibility with this deployment.
> Earlier local smoke checks used `0.17.2`.

The agent knew `0.17.2` was verified but followed a request to pin current stable
to `0.18.2`, then documented the mismatch instead of challenging the decision.
It should have recommended the verified release before editing. Discuss both
the missed pushback and why the resulting prose was useless, defensive and could
make Philip look forgetful. Philip corrected the pin to `0.17.2` and required
shorter documentation without the date. Do not add dates without explicitly
telling him. Check whether existing guidance prevents this behavior rather than
merely accumulating more writing rules.
