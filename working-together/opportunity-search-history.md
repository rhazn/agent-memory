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

Last run: 2026-11-12T10:02:04+01:00.
Coverage: Partial. Set and verified Welcome to the Jungle freelance-only
preferences with Paris and broad remote/experience options. Checked empty new
matches and all three Seen pages (24 cards); read eight freelance listings.
Screened both pages of the Freelancermap direct-client software search, all four
pages of the delivery-model query, and one AI-teaching query (17 results).
Read 14 full Freelancermap listings. Verified LinkedIn remote/contract filters
and screened first result pages for project delivery and AI-tool training;
read six full listings. No application recommendations; four near-misses shown.
Search was not exhaustive. No applications or messages sent.

User-reported application status, confirmed 2026-11-06:
- Fiedler Consulting, ElevenLabs training portal: Philip applied.
- usd AG, AI-enabled Security Intelligence PoC: rejected; Philip did not apply.
  Do not resurface either as a new lead. General fit guidance is in
  `business-development.md`.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-12T10:02:04+01:00 | Digital Career Institute - Kubernetes CKA training | https://www.freelancermap.de/projekt/kubernetes-cka-dozent-trainer-freelance-100-prozent-remote |
| 2026-11-12T10:02:04+01:00 | Verlag J. Maiss - Cross-product design system | https://www.freelancermap.de/projekt/ui-ux-designer-in-fuer-produktuebergreifendes-design-system-web-ios-android-windows-macos |
| 2026-11-12T10:02:04+01:00 | Cambridge Spark - GenAI and automation delivery consultant | https://www.linkedin.com/jobs/view/4424862176/ |
| 2026-11-12T10:02:04+01:00 | Komodo Consulting - AI tools trainer | https://www.linkedin.com/jobs/view/4485116355/ |
| 2026-11-06 (exact time not recorded) | Fiedler Consulting - ElevenLabs training portal | https://www.freelancermap.de/projekt/web-portal-um-fertige-elevenlabs-sprachagenten-festpreis-je-baustein |
| 2026-11-06 (exact time not recorded) | usd AG - AI-enabled Security Intelligence PoC | https://www.freelancermap.de/projekt/proof-of-concept-for-an-ai-enabled-security-intelligence-platform |
| 2026-11-06 (exact time not recorded) | COS GmbH - Fleet-management software work packages | https://www.freelancermap.de/projekt/freelancer-fuer-zuarbeiten-an-fuhrparkverwaltungs-software-gesucht |
| 2026-11-06 (exact time not recorded) | MAVI - Agency tooling and AI-agent setup | https://www.freelancermap.de/projekt/agentur-setup-fuer-vibe-coder-llm-erstellen |
| 2026-11-06 (exact time not recorded) | INTRIK - Prototype-to-production work packages | https://www.linkedin.com/jobs/view/4485352871/ |
| 2026-11-05T08:33:39+01:00 | DEK Telecom - Central Linux-management platform | https://www.freelancermap.de/projekt/konzeption-und-implementierung-einer-zentralen-linux-management-plattform-suse-umgebung |

## find-job-opportunities

Last run: 2026-11-12 (exact run timestamp not recorded).
Coverage: Partial. Screened three first LinkedIn result pages for AI product,
software/data/AI engineering, and French research/data/part-time terms. LinkedIn
filters did not persist reliably; checked vacancy terms individually. Welcome
to the Jungle's shared preferences changed during the search, limiting coverage.
Screened all 80 EURAXESS France/computer-science job offers across eight pages.
Read seven full vacancies and three accessible application forms. Inria's Apply
link stopped at a login gate, so its application questions were not inspected.
No confirmed part-time recommendation. Search was not exhaustive. This record
was saved after the report because that turn was read-only.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-12 (exact time not recorded) | Akur8 - Product Engineer | https://jobs.ashbyhq.com/akur8/bd289e12-03cd-4fc2-96ec-698adc490b3a |
| 2026-11-12 (exact time not recorded) | Cozycozy - AI Product Builder | https://jobs.cozycozy.com/o/ai-product-builder |
| 2026-11-12 (exact time not recorded) | Inria WILLOW - Research engineer, perspective-grounded spatial reasoning | https://recrutement.inria.fr/public/classic/en/offres/2026-10630 |
| 2026-11-10T14:55:46+01:00 | PayFit - Senior AI Product Engineer | https://careers.payfit.com/jobs/8643460-senior-ai-product-engineer |
| 2026-11-10T14:55:46+01:00 | Joko - Lead Product Manager, AI Platform | https://jobs.ashbyhq.com/joko/ad0f0110-4081-4242-9a18-cfcc91a98bde |
| 2026-11-10T14:55:46+01:00 | Overstory - Staff Product Manager, Machine Learning | https://jobs.ashbyhq.com/overstory/11d1c613-10f4-44a8-8973-44f2f1f710b0 |
| 2026-11-06T08:40:10+01:00 | Dotfile - Senior Fullstack Engineer | https://jobs.ashbyhq.com/dotfile/bb5e660f-3b60-4d72-9e44-986f0850afc5 |
| 2026-11-06T08:40:10+01:00 | Swile - Senior Data Platform Engineer | https://jobs.lever.co/swile/2883d123-bbd8-4cce-93b3-04b8e387bca8 |
| 2026-11-06T08:40:10+01:00 | Alan - Product Builder, Mo AI health companion | https://jobs.ashbyhq.com/alan/3c8dfcd2-822e-419e-8c06-1cae00e08aa2 |
| 2026-11-06T08:40:10+01:00 | Inria - Machine Learning Engineer, DYNASTY | https://jobs.inria.fr/public/classic/en/offres/2026-10601 |

## find-engagement-opportunities

Last run: 2026-11-12T10:01:22+01:00.
Coverage: Partial. Screened 54 post-result cards across nine queries with the
past-week filter, covering software operations, data engineering, laboratory
workflows, esports software/data/AI, and exploratory parking/mobility data
integration. Read three direct post threads, three author profiles and one linked
article. Returned three opportunities, including a newer migration account found
through an author's profile. No strong esports or exploratory parking match.
Searches were not exhaustive.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-12T10:01:22+01:00 | PHABIOC - Automation exposes manual workflow adjustments | https://www.linkedin.com/feed/update/urn:li:activity:7525869914562207744/ |
| 2026-11-12T10:01:22+01:00 | ClearFeed - Self-hosted agent investigates production alerts | https://www.linkedin.com/feed/update/urn:li:activity:7524399250961666048/ |
| 2026-11-12T10:01:22+01:00 | Nordstrom - Pipeline migration exposes silent errors and short vendor retention | https://www.linkedin.com/feed/update/urn:li:activity:7525683040375885824/ |
| 2026-11-06T08:45:14+01:00 | Arabhardware - Live fantasy league built in one week | https://www.linkedin.com/posts/mirnaihab_ahwesports-pubgmobile-pmgo2026-ugcPost-7523777821224194048-V-Dn/ |
| 2026-11-06T08:45:14+01:00 | LabMODO - Tracking method detection limits | https://www.linkedin.com/posts/michaelgaumer_lab-managers-and-qa-professionals-how-are-share-7523435188966662146-ysPK/ |
| 2026-11-06T08:45:14+01:00 | Wolters Kluwer - Technical debt with AI-assisted development | https://www.linkedin.com/posts/morettilorenzo_safe-agenticai-safe-ugcPost-7523631166806016000-ph19/ |
| 2026-11-06T08:45:14+01:00 | Benchmark Scientific - Simulation and instrument APIs for lab automation | https://www.linkedin.com/posts/labautomation-robotics-accurisinstruments-ugcPost-7523417674270584832-zTPH/ |
| 2026-11-06T08:45:14+01:00 | Smash Bros analytics - AI-assisted building and learning | https://www.linkedin.com/posts/jsavaryn_i-vibe-coded-my-first-project-it-was-really-share-7522290767143526402-NVHK/ |
| 2026-11-03T10:01:50+01:00 | Process workarounds - Bitte nicht noch ein Flussdiagramm | https://www.linkedin.com/posts/florian-fink-25912a17a_bitte-nicht-noch-ein-flussdiagramm-das-share-7523285849271259136-22rh/ |
| 2026-11-03T10:01:50+01:00 | AI due diligence beyond the demo | https://www.linkedin.com/posts/hugo-carreira-31b18a29_ai-duediligence-privateequity-share-7522693726809530368-kMgv/ |
