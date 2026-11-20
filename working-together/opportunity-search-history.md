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

Last run: 2026-11-20T09:26:12+01:00.
Coverage: Partial. Screened four first LinkedIn result pages and checked vacancy
terms individually after LinkedIn dropped the employment filter. Reviewed targeted
Welcome to the Jungle listings without changing the saved freelance-only filters
in Plan mode. Screened all 80 EURAXESS France/computer-science job offers across
eight pages and checked public HelloWork AI engineering and part-time development
results. Read the three shortlisted vacancies and inspected two application forms.
Inria's form required sign-in. No confirmed part-time match. Search was not
exhaustive. Saved after Plan mode ended.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-20 (exact report time not recorded) | Alan - Fullstack Software Engineer, Agentic Platform | https://jobs.ashbyhq.com/Alan/3b78382c-b243-46c1-a22e-a67850b21821 |
| 2026-11-20 (exact report time not recorded) | Tsuga - Senior Product Manager | https://jobs.gem.com/tsuga/am9icG9zdDow7m3Oit8ySIykqKUZe2XZ |
| 2026-11-20 (exact report time not recorded) | Inria ARAMIS - Research Engineer, Medical Foundation Model Alignment | https://recrutement.inria.fr/public/classic/en/offres/2026-10648 |
| 2026-11-16 (exact time not recorded) | Armature - Founding Engineer, Applied AI Research | https://www.ycombinator.com/companies/armature/jobs/Coplfpy-founding-engineer-applied-ai-research |
| 2026-11-16 (exact time not recorded) | Modash - Senior Software Engineer, Data Search | https://apply.workable.com/modash/j/5761CCE8F8/ |
| 2026-11-16 (exact time not recorded) | Mozza - Tech Builder, AI Software Engineer | https://www.welcometothejungle.com/fr/companies/mozza-1/jobs/tech-lead-full-stack-genai_paris_MOZZA_RKxoxVo |
| 2026-11-12 (exact time not recorded) | Akur8 - Product Engineer | https://jobs.ashbyhq.com/akur8/bd289e12-03cd-4fc2-96ec-698adc490b3a |
| 2026-11-12 (exact time not recorded) | Cozycozy - AI Product Builder | https://jobs.cozycozy.com/o/ai-product-builder |
| 2026-11-12 (exact time not recorded) | Inria WILLOW - Research engineer, perspective-grounded spatial reasoning | https://recrutement.inria.fr/public/classic/en/offres/2026-10630 |
| 2026-11-10T14:55:46+01:00 | PayFit - Senior AI Product Engineer | https://careers.payfit.com/jobs/8643460-senior-ai-product-engineer |

## find-engagement-opportunities

Last run: 2026-11-20 (exact run timestamp not recorded).
Coverage: Partial. Screened 60 result cards across ten past-week LinkedIn
searches covering software operations, data integration, labs, esports,
parking, and maintenance reporting. Read seven direct posts and checked author
activity and relevant replies. Four suggestions shown. Search was not exhaustive.
Saved after read-only mode ended.

| Shown at | Opportunity | Canonical URL or stable ID |
| --- | --- | --- |
| 2026-11-20 (exact time not recorded) | Lalli Consulting Engineers - Dashboard plans weekly work | https://www.linkedin.com/feed/update/urn:li:activity:7528092784864587776/ |
| 2026-11-20 (exact time not recorded) | Zeon - Unitick open-source esports replay analysis | https://www.linkedin.com/feed/update/urn:li:activity:7527298290678403072/ |
| 2026-11-20 (exact time not recorded) | Socar Cape - Operations and finance build internal tools | https://www.linkedin.com/feed/update/urn:li:activity:7528868304313151488/ |
| 2026-11-20 (exact time not recorded) | Presco Plc - Factory maintenance reporting and overlapping job cards | https://www.linkedin.com/feed/update/urn:li:activity:7527736879669092352/ |
| 2026-11-16 (exact time not recorded) | Equipment manual becomes a training simulator | https://www.linkedin.com/feed/update/urn:li:activity:7527665344954408960/ |
| 2026-11-16 (exact time not recorded) | GRID esports - Official Riot match data open access | https://www.linkedin.com/feed/update/urn:li:activity:7526678934999142400/ |
| 2026-11-16 (exact time not recorded) | Property occupancy growth and reserved parking | https://www.linkedin.com/feed/update/urn:li:activity:7525542839603113984/ |
| 2026-11-12T10:01:22+01:00 | PHABIOC - Automation exposes manual workflow adjustments | https://www.linkedin.com/feed/update/urn:li:activity:7525869914562207744/ |
| 2026-11-12T10:01:22+01:00 | ClearFeed - Self-hosted agent investigates production alerts | https://www.linkedin.com/feed/update/urn:li:activity:7524399250961666048/ |
| 2026-11-12T10:01:22+01:00 | Nordstrom - Pipeline migration exposes silent errors and short vendor retention | https://www.linkedin.com/feed/update/urn:li:activity:7525683040375885824/ |
