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

Last run: 2026-11-05T08:33:39+01:00.
Coverage: Partial. Verified Welcome to the Jungle freelance preferences, checked
new matches (none) and all three Seen pages (29 cards). Screened both pages of
the Freelancermap saved direct-client search (40 unapplied results), then the
first three broader direct-client pages and an architecture/audit query without
the direct-client filter. Checked LinkedIn software-delivery and architecture
assessment result pages; contract filtering did not work reliably. Read 16 full
listings across the three sources. Returned one possible Linux-management
delivery lead and four non-recommended leads. Search was not exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-05T08:33:39+01:00 | DEK Telecom - Central Linux-management platform | https://www.freelancermap.de/projekt/konzeption-und-implementierung-einer-zentralen-linux-management-plattform-suse-umgebung |
| 2026-11-05T08:33:39+01:00 | Skapa Agency - Agentic SDLC platform validation | https://www.linkedin.com/jobs/view/4485747758/ |
| 2026-11-05T08:33:39+01:00 | amnia digital - API integration and AI development workflows | https://www.freelancermap.de/projekt/backend-entwickler-fuer-api-anbindung-und-ki-integration-gesucht |
| 2026-11-05T08:33:39+01:00 | Ticket Tickers - Ticketing platform work packages | https://www.freelancermap.de/projekt/senior-full-stack-entwickler-in-next-js-supabase-stripe-ticketing-plattform-teilzeit-remote |
| 2026-11-05T08:33:39+01:00 | Simon - SaaS marketing and outbound automation | https://www.freelancermap.de/projekt/automation-gtm-engineer-n8n-clay-llm-apis-komplettes-marketing-und-outbound-system-fuer-b2b-saas |

## find-job-opportunities

Last run: 2026-11-04T11:17:02+01:00.
Coverage: Partial. Checked first LinkedIn result pages for AI product, data and
research engineering, part-time roles, and French-language data/research terms.
LinkedIn AI search did not reliably retain employment-type filters, so actual
vacancy terms took precedence. Corrected Welcome to the Jungle freelance-only
preferences to permanent, part-time and temporary employment; checked experienced
matches, both Seen pages (18 listings), and the first early-career data/AI page.
Screened all 81 France/computer-science EURAXESS results across nine pages.
Fully reviewed 16 distinct plausible vacancies, with employer-page checks for
PayFit and the ENS-PSL part-time research assistant role. The latter requires
current Master's enrollment and was excluded. Search was not exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-04T11:17:02+01:00 | Joko - Product Manager, AI Platform | https://www.linkedin.com/jobs/view/4459689758/ |
| 2026-11-04T11:17:02+01:00 | PayFit - Senior AI Product Engineer | https://careers.payfit.com/jobs/8643460-senior-ai-product-engineer |
| 2026-11-04T11:17:02+01:00 | Modash - Senior Software Engineer, Data Search | https://www.linkedin.com/jobs/view/4474766269/ |
| 2026-11-04T11:17:02+01:00 | AQEMIA - Senior Data Engineer | https://www.linkedin.com/jobs/view/4480757003/ |
| 2026-11-04T11:17:02+01:00 | Ledger - Data Scientist & Analytics Engineer | https://www.welcometothejungle.com/en/companies/ledger/jobs/analytics-engineer_paris |
| 2026-10-30T12:53:41+01:00 | Scaleway - Product Manager, AI Inference | https://jobs.lever.co/scaleway/a00c86ba-e7b1-4e46-a023-d98d89ca3eb2 |
| 2026-10-30T12:53:41+01:00 | Syntrace - Software Engineer | https://www.linkedin.com/jobs/view/4481450969/ |
| 2026-10-30T12:53:41+01:00 | Nuitee - Senior Product Manager, Customer Operations | https://job-boards.eu.greenhouse.io/nuitee/jobs/5015803101 |
| 2026-10-29T13:06:18+01:00 | Mistral AI - Research Software Engineer | https://www.welcometothejungle.com/en/companies/mistral-ai/jobs/research-software-engineer_paris |
| 2026-10-29T13:06:18+01:00 | Dashdoc - Software Engineer, Shippers Team | https://www.welcometothejungle.com/en/companies/dashdoc/jobs/software-engineer |

## find-engagement-opportunities

Last run: 2026-11-03T10:01:50+01:00.
Coverage: Partial. Screened 54 post results across eight queries covering software
operations, data integration, laboratory workflows, and exploratory technical due
diligence. Fully inspected three direct post threads, one linked article, and
three author profiles. Excluded the self-hosting thread already commented on by
Philip. Returned one process discussion and one exploratory AI diligence discussion;
the process post had no visible engagement yet. Searches were not exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-03T10:01:50+01:00 | Process workarounds - Bitte nicht noch ein Flussdiagramm | https://www.linkedin.com/posts/florian-fink-25912a17a_bitte-nicht-noch-ein-flussdiagramm-das-share-7523285849271259136-22rh/ |
| 2026-11-03T10:01:50+01:00 | AI due diligence beyond the demo | https://www.linkedin.com/posts/hugo-carreira-31b18a29_ai-duediligence-privateequity-share-7522693726809530368-kMgv/ |
