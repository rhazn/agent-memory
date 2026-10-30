# Opportunity Search History

Philip requests this bounded exception to the usual rule against activity logs.
Use it for all three opportunity-search skills. Keep preferences and feedback
learnings in their existing domain files, not here.

## Shared Procedure

- Read the relevant section before searching and compare candidates before
  presenting the shortlist. Skip opportunities already shown unless Philip
  explicitly asks to revisit them. Return fewer new matches rather than repeats.
- Match canonical URLs or stable platform IDs. Ignore tracking parameters and
  recognize the same vacancy across portals or translated listings using the
  employer, role, and vacancy details. A repost is not automatically a new
  opportunity. For discussions, match the original post, not its feed URL.
- Use the last-run time for context, not as a hard publication-date cutoff:
  older opportunities may still be unseen and suitable.
- After each actual search, replace that skill's last-run timestamp with the
  actual run time in ISO 8601 with a timezone. Record whether coverage was
  complete, partial, or blocked; do not label an interrupted search complete.
  Update it even when no new opportunities qualify. Configuration edits and
  feedback-only conversations are not search runs.
- Add only opportunities actually shown to Philip, not everything inspected or
  rejected. Store the shown-at timestamp, a short identifying title, employer
  or organization where useful, and a canonical URL or stable ID. Do not store
  full descriptions, comments, cover letters, contact details, author profiles,
  or per-item feedback here.
- Keep at most ten distinct opportunities per skill, newest shown first.
  Merge with existing entries and trim the oldest. If an item is deliberately
  revisited, update its shown-at time rather than adding a duplicate row.
- Save the record with the search report without waiting for feedback. Follow
  `agent-memory` for focused commits and pushes. Preserve unrelated changes and
  report synchronization failures. Never claim history was saved when it was not.
- Missing history means unknown, not proof that no search happened. Do not
  invent past run times or reconstruct opportunities from guesses. This rolling
  window prevents recent repeats; it is not an all-time archive.

## find-agency-opportunities

Last run: Not recorded.
Coverage: Unknown.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |

## find-job-opportunities

Last run: 2026-10-30T12:53:41+01:00.
Coverage: Partial. Checked the first LinkedIn result pages for product, data/AI,
French-language data/research terms, and part-time software/data/product/research.
Screened all 95 France/computer-science EURAXESS results across ten pages.
Corrected Welcome to the Jungle freelance-only filters to permanent, part-time,
and temporary employment; checked experienced and early-career matching passes
and both Seen pages (19 listings). Fully reviewed 11 distinct vacancies,
including employer-page checks for Scaleway and Nuitee. Nuitee has a LinkedIn
part-time label but no employer-confirmed hours. Portal searches were not
exhaustive; supplementary web searches were cancelled and returned no results.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-10-30T12:53:41+01:00 | Scaleway - Product Manager, AI Inference | https://jobs.lever.co/scaleway/a00c86ba-e7b1-4e46-a023-d98d89ca3eb2 |
| 2026-10-30T12:53:41+01:00 | Syntrace - Software Engineer | https://www.linkedin.com/jobs/view/4481450969/ |
| 2026-10-30T12:53:41+01:00 | Nuitee - Senior Product Manager, Customer Operations | https://job-boards.eu.greenhouse.io/nuitee/jobs/5015803101 |
| 2026-10-29T13:06:18+01:00 | Mistral AI - Research Software Engineer | https://www.welcometothejungle.com/en/companies/mistral-ai/jobs/research-software-engineer_paris |
| 2026-10-29T13:06:18+01:00 | Dashdoc - Software Engineer, Shippers Team | https://www.welcometothejungle.com/en/companies/dashdoc/jobs/software-engineer |
| 2026-10-29T13:06:18+01:00 | Qonto - Staff Product Manager, Loans | https://jobs.ashbyhq.com/qonto/661f1548-8720-483d-b606-5bf58409448f |
| 2026-10-28T12:22:29+01:00 | Filigran - Senior Software Engineer, AI-Native Engineering (XTM Foundation) | https://jobs.ashbyhq.com/filigran/078b3281-6e64-4c52-82c9-c20a73dcb2fa |
| 2026-10-28T12:22:29+01:00 | Mistral AI - Data Scientist | https://www.welcometothejungle.com/en/companies/mistral-ai/jobs/data-scientist_paris_MA_wZLPoxR |
| 2026-10-28T12:22:29+01:00 | Inria - Machine Learning Engineer, DYNASTY / SIERRA | https://jobs.inria.fr/public/classic/en/offres/2026-10601 |

## find-engagement-opportunities

Last run: Not recorded.
Coverage: Unknown.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
