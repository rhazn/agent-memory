# Personal setup reviews

## Review preferences

- Philip triggers reviews manually. Review his personal setup across projects,
  not project-local configuration. Surface any conflict with project rules.
- Invite freeform feedback at the start, but skip it if Philip wants to work
  from an existing agenda. Agree the period and sample. Inspect session
  conversations and discuss findings in small batches across all nine areas.
- Give the current step, what remains, and the next step in every reply. Advance
  only when Philip explicitly closes the current step or asks to move on.
  Agreement on a topic is not approval to close the step, including the open floor.
- Discuss the high-level picture that shared memory gives of Philip and how
  to work with him. Ask for corrections before changing that picture.
- Review the meeting itself. End by explicitly saying the review is complete
  and no steps remain. Summarize decisions, changes, sync, and commit/push status.

## Latest audit

20 November 2026. Window: 16-20 November. Inventoried local OpenCode sessions
and inspected selected conversations across writing, implementation, review,
and configuration. Pi and Agent Box sessions were outside this sample.

- Kept GPT-6.2 as the default. Philip confirmed high transcript detail works.
- Scoped ASD-STE100 to explicitly requested writing. Strengthened guidance to
  surface conflicting assumptions before acting and to write direct claims.
- Made board tracking opt-in, with explicit conflict handling and links for
  changed cards. Standardized OpenCode local file references as `path:line`.
- Moved coding guidance, writing patterns, and examples to a shared knowledge
  base. Added phased planning and `git mv` handoff guidance, architecture
  guidance, and React/frontend practices. Removed the phased procedure from
  personal memory and left `SOUL.md` unchanged.
- Added a shared note-capture procedure with `/improvement` as the OpenCode
  shortcut. Added a recurring knowledge-base discussion and an explicit
  stage-advance requirement to the review skill.
- Synced the managed configuration locally. Configuration tests passed and
  OpenCode listed `/improvement`. A live note save and Agent Box sync were not
  performed.

## Check at the next review

- **Budget agent experiment:** Keep it available and explicitly invoked.
  No use appeared in the local OpenCode sample. Philip considers that an
  early negative signal but wants to continue the experiment. Ask whether
  he used it; if so, compare invocation friction, result quality, quota
  blockers, and rework with manual model switching. If there is still no use,
  ask whether to retire it.
- **Coding guidance:** Ask whether Philip noticed the new guidance, what helped,
  and what felt rigid or added complexity. Look at examples from premise checks
  and phased Git work; state and provider ownership, connection lifecycle, and
  small co-located files; and React component boundaries, loading, semantic
  themes, and stack choices. Check the knowledge base for the actual rules.
- **Note capture:** Check whether `/improvement` or a plain request in another
  harness saved a useful note with the correct timestamp and session ID.

## Pending agenda

- **Writing:** Philip liked the light tone pass on "Roast my UI": it sounded more
  like talking among friends, with small, dry jokes at his own expense. Review
  the edits as positive examples for the writing best practices.
  2026-11-20T20:15:04+01:00, OpenCode, `ses_e05a00e82ffeDtwX4kbsJB2f9s`.
- **Writing best practices repo:** Discuss starting a dedicated repository and
  workflow for writing best practices, modeled on the one for code.
  2026-11-20T20:16:31+01:00, OpenCode, `ses_e05a00e82ffeDtwX4kbsJB2f9s`.
- **Failing checks:** Philip wants Vale, code lint, and test errors treated as
  urgent and fixed, not left unresolved. Review why the agent treated the Vale
  failures in "Roast my UI" as non-blocking and reported the work as done.
  2026-11-20T20:32:58+01:00, OpenCode, `ses_e05a00e82ffeDtwX4kbsJB2f9s`.
- **User-resolvable verification blocker:** The agent noted that Docker was
  unavailable but did not clearly ask Philip to start it, leaving the build
  and integration checks unverified. Philip could have started Docker easily
  and wanted an explicit, prominent request as soon as it blocked verification.
  2026-11-23T15:06:45+01:00, OpenCode, `ses_df76380d5ffeLdWn4gP8UXHicP`.
- **Agent personality and name:** Philip thinks it would be fun to discuss a
  personality and name for the shared agent in `SOUL.md`.
  2026-11-23T15:07:32+01:00, OpenCode, `ses_df76380d5ffeLdWn4gP8UXHicP`.
- **Code structure:** Review why the existing coding guidance did not lead the
  agent to split three Temporal workflow classes into separately named files
  in one `workflows/` package. Philip wants each file to contain one small,
  self-contained responsibility, with a filename that names it and related
  files grouped in small packages. Use his feedback in this session to discuss
  how to make the guideline apply more consistently.
  2026-11-24T18:24:12+01:00, OpenCode, `ses_df1700dd4ffewidPET6Ws61CCy`.
- **Explicit code review invocation:** Focused requests such as reviewing
  file structure have repeatedly triggered the full multi-agent code review
  when Philip wanted only the requested check. He wants the full workflow
  available only via an explicit command such as `/code-review`, not triggered
  by the word "review" in ordinary requests.
  2026-11-24T18:27:23+01:00, OpenCode, `ses_df1700dd4ffewidPET6Ws61CCy`.
