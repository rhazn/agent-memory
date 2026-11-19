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

Discuss project-management activation and visible task tracking. Philip wants
ad hoc work to stay off the board unless he explicitly refers to a board task
at the start of the working session or asks to use the board. Review the shared
project-management skill, global activation instructions, and project-local
rules together; current com.isselthal instructions require board tracking and
conflict with this intended default. This is an agenda item, not authorization
to change skills or project instructions now.

Bad example: OpenCode session `ses_e15a1d0c8ffeUnN3Enuu3jStDU`, the Desktop PDF
blog-feedback conversation moved from lizard-savehouse to com.isselthal. During
ad hoc article revisions, the agent reopened completed cards
[#4, lasting-investment article](https://tinquiete-pas.apps.heltweg.org/cards/com-isselthal-4-n1s08q96i7mfy382joae6s53)
and [#5, automation articles](https://tinquiete-pas.apps.heltweg.org/cards/com-isselthal-5-d14t9sghfeuqu0ji2w25mxhqq),
added revision notes and moved them through DOING to FOR HUMAN REVIEW. Philip
had not asked to work from the board, and the final replies did not identify or
link the affected cards. Discuss avoiding unsolicited tracking and reopening of
completed work. Require final responses to identify and link every task changed
and summarize the actual operation, including description updates, moves,
reopening and completion.

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

Evaluate the switch to OpenAI GPT-6.2 on Wednesday morning, 18 November 2026.
Compare representative sessions before and after the switch. Check answer
quality, adherence to instructions, and how much correction or rework Philip
needed. Ask Philip what differences he noticed before drawing a conclusion.

Check whether the applied writing changes improve sentence rhythm and keep
ASD-STE100 out of authored prose unless requested. Assess whether earlier goal
checks prevent wasted substantial work without over-questioning simple tasks.
The effects of these changes across later sessions are not yet established.

Revisit ASD-STE100 activation. Philip clarified that the skill is only for
writing when he explicitly asks for it, not for replies to him. The previous
audit and `WORKING-TOGETHER.md` still recommend it for direct replies. Review
that conflict and the skill's own scope at the next review.

Example from OpenCode session `ses_e11989fa6ffeeS0RCcd9WzPv3H`, recorded on
18 November 2026 at 14:47 CET: the agent followed the standing memory guidance,
loaded ASD-STE100 without a request, and disclosed using it in a direct reply
about the Mac mini setup. Philip flagged that reply as an example to discuss.

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

Discuss file references in OpenCode review replies. In session
`ses_e0d00f14cffe5agKVMzPU3CGfW`, recorded on 19 November 2026 at 09:58 CET,
the Frigate cleanup review linked to local files and line numbers using relative
Markdown links. Philip could not open them in OpenCode, which said only HTTP
and HTTPS links could be opened. Check whether the review skill calls for this
format or the agent chose it, then discuss how to present usable file references.
This is an agenda item, not a request to change OpenCode or the review skill now.

Two Git workflow examples from OpenCode session
`ses_e0ce7ade4ffeEN3nhCmjhWufP7`, recorded on 19 November 2026 at 10:29 CET:

- **Corrected move.** The agent moved the tracked Frigate notifier files with
  plain `mv` and edited Compose and docs. It handed off a working tree that showed
  deletions and an untracked destination instead of staged renames. Philip said
  it should have used `git mv` to keep the move legible in Git history. The agent
  redid the move with `git mv` and verified eight 100% renames. Discuss adding
  guidance to the version-control skill for intentional moves of tracked files,
  including how to handle the staging that `git mv` performs. Git detects
  renames from the committed content either way; the issue was the move and
  handoff, not demonstrated loss of history.
  Follow-up in the same session, recorded at 10:34 CET: in the next phase,
  `git mv` staged the test moves automatically, but the agent left the related
  test and config edits unstaged. Committing just the index would have left
  out edits needed for the new layout. Philip did not know that `git mv` stages
  moves and staged the full phase himself. Discuss making the staging side
  effect explicit and agreeing on who stages the complete phase before using
  `git mv` in a human-commit workflow.
- **Keep commit phases in plans.** Philip liked splitting the Frigate testing
  work into a notifier move, existing test cleanup, new behavior tests,
  integration tests, and CI. When planning substantial work together, offer
  semantically coherent commit boundaries. After each phase, recap what changed,
  say what's next, and wait for Philip to commit before continuing when he chooses
  step-by-step execution. He can instead ask to run all phases in one pass.

Unauthorized commit example: OpenCode session `ses_e0cb7fbd5ffex2lKHUCGCKsX7K`,
recorded on 19 November 2026 at 11:25 CET. The agent treated "go for number one"
in the phased Frigate linting plan as permission to commit the first phase
(`7c552d1`). Philip clarified that he wants to review and commit each phase
himself. Discussion point: distinguish agreement on commit boundaries and
authorization to implement from explicit authorization to stage or commit.
