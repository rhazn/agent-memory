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

Last run: 2026-11-06T08:40:10+01:00.
Coverage: Partial. Checked three first LinkedIn result pages covering AI product,
software/data/AI engineering, and French research/data/part-time terms. Employment
filters did not persist; verified terms in vacancies instead. Verified Welcome
to the Jungle permanent/part-time/temporary, Paris, remote and junior-to-senior
preferences, expanded role titles to personal-job tracks, checked empty new
matches and ten Seen cards. Targeted search led to the matching landing page.
Screened EURAXESS France/computer-science results 1-10 and 21-60 of 83. Read 12
full vacancies plus one incomplete syndicated listing. Verified all five shown
roles on employer pages and inspected four application forms; Inria's form
requires sign-in. No suitable explicit part-time role found. Search was not
exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-06T08:40:10+01:00 | Dotfile - Senior Fullstack Engineer | https://jobs.ashbyhq.com/dotfile/bb5e660f-3b60-4d72-9e44-986f0850afc5 |
| 2026-11-06T08:40:10+01:00 | Swile - Senior Data Platform Engineer | https://jobs.lever.co/swile/2883d123-bbd8-4cce-93b3-04b8e387bca8 |
| 2026-11-06T08:40:10+01:00 | Alan - Product Builder, Mo AI health companion | https://jobs.ashbyhq.com/alan/3c8dfcd2-822e-419e-8c06-1cae00e08aa2 |
| 2026-11-06T08:40:10+01:00 | Inria - Machine Learning Engineer, DYNASTY | https://jobs.inria.fr/public/classic/en/offres/2026-10601 |
| 2026-11-06T08:40:10+01:00 | amo - Location Data engineer | https://jobs.ashbyhq.com/amo/6cb7a130-d790-4712-b098-953515c2eb2d |
| 2026-11-05T08:34:18+01:00 | Brevo - AI Native Product Engineer | https://jobs.lever.co/brevo/13cc40a9-97ed-46e5-a7ac-2e0b1aa99654 |
| 2026-11-05T08:34:18+01:00 | Click&Boat - Data Product Manager | https://clickboat.teamtailor.com/jobs/8456791-data-product-manager |
| 2026-11-05T08:34:18+01:00 | Current AI - Product Manager: Partnerships | https://aicurrent.bamboohr.com/careers/38 |
| 2026-11-05T08:34:18+01:00 | Scaleway - Product Manager, Storage | https://jobs.lever.co/scaleway/12086374-35bc-49e4-9fa3-63b9df97da0b |
| 2026-11-05T08:34:18+01:00 | Beamy - Applied AI Engineer | https://jobs.lever.co/Beamy/5defdfbe-8ec1-4279-94d7-279c840c2c29 |

## find-engagement-opportunities

Last run: 2026-11-06T08:45:14+01:00.
Coverage: Partial. Screened 64 post results across eleven queries with the past-week
filter, covering software operations, data engineering, laboratory workflows,
esports software/data/AI, and exploratory European open-source rollout/adoption.
Read five direct post threads, four author profiles and one company activity page.
Returned five opportunities. The exploratory direction produced no strong match;
results were mainly announcements or promotional posts. Searches were not exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-06T08:45:14+01:00 | Arabhardware - Live fantasy league built in one week | https://www.linkedin.com/posts/mirnaihab_ahwesports-pubgmobile-pmgo2026-ugcPost-7523777821224194048-V-Dn/ |
| 2026-11-06T08:45:14+01:00 | LabMODO - Tracking method detection limits | https://www.linkedin.com/posts/michaelgaumer_lab-managers-and-qa-professionals-how-are-share-7523435188966662146-ysPK/ |
| 2026-11-06T08:45:14+01:00 | Wolters Kluwer - Technical debt with AI-assisted development | https://www.linkedin.com/posts/morettilorenzo_safe-agenticai-safe-ugcPost-7523631166806016000-ph19/ |
| 2026-11-06T08:45:14+01:00 | Benchmark Scientific - Simulation and instrument APIs for lab automation | https://www.linkedin.com/posts/labautomation-robotics-accurisinstruments-ugcPost-7523417674270584832-zTPH/ |
| 2026-11-06T08:45:14+01:00 | Smash Bros analytics - AI-assisted building and learning | https://www.linkedin.com/posts/jsavaryn_i-vibe-coded-my-first-project-it-was-really-share-7522290767143526402-NVHK/ |
| 2026-11-03T10:01:50+01:00 | Process workarounds - Bitte nicht noch ein Flussdiagramm | https://www.linkedin.com/posts/florian-fink-25912a17a_bitte-nicht-noch-ein-flussdiagramm-das-share-7523285849271259136-22rh/ |
| 2026-11-03T10:01:50+01:00 | AI due diligence beyond the demo | https://www.linkedin.com/posts/hugo-carreira-31b18a29_ai-duediligence-privateequity-share-7522693726809530368-kMgv/ |
