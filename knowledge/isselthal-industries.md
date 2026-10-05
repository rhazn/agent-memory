# Isselthal Industries

## Public References

- Website: https://isselthal.com/ (the previous `isselthal.industries` domain redirects here).
- Philip Heltweg CV: https://www.heltweg.org/assets/files/cv_philip_heltweg.pdf
- Georg Schwarz CV: https://georg-schwarz.com/cv/

## Positioning

- Boutique engineering firm for complex software and data problems, research-data work, platform engineering, architecture assessment, technical due diligence, and technical/product ownership.
- Focus on agency engagements and direct customer outcomes, not individual contractor placements or subcontracting pools.

## Outreach Evidence

- Philip: qualitative and quantitative software-engineering research and data engineering.
- Georg: full-stack systems, microservices, Kubernetes, observability, and research-project management.
- Consult the public CVs before making experience-specific claims.

## Website crawler policy (2026-10-05)

- User wants all search, AI search/agent, training, and generic crawlers allowed. Cloudflare settings must be automated in Pulumi, with no manual dashboard setup. Keep existing blog canonicals pointing to originals on `heltweg.org`.
- Website source is `/Users/pheltweg/development/projects/com.isselthal`. Added permissive `public/robots.txt` with the sitemap URL and `src/pages/404.astro` so Cloudflare Pages stops returning the homepage for nonexistent paths.
- Infrastructure is in `lizard-savehouse/iac` (not `lizard-safehouse`). User approved upgrading `@pulumi/cloudflare` to v6.21.0. Unrestricted crawler access is now unconditional in `DomainBuilder` for every managed zone, using native `ZoneSetting`, `BotManagement`, and apex/`www` WAF skip resources. The opt-in method and calls were removed at the user's request. West of Babel has only a Cloudflare-owned `pages.dev` hostname, with no configurable user-owned zone.
- User rejected the custom dynamic provider and requested minimal edits with no added tests or scripts. It was removed, along with the added project documentation. When a pinned library lacks needed functionality, ask about an upgrade before building a custom workaround. Memory belongs only in this separate memory repository.
- Infrastructure compilation, website build, and prose lint passed. Production preview was blocked by the missing stack encryption passphrase; the user chose to handle deployment. Website source uses its normal Pages production deployment, and infrastructure uses Pulumi. Crawler resources require Bot Management and Zone WAF permissions in addition to Zone Settings permissions. Provider v6.21.0 still lacks the separate AI Search/Agent/Training fields; the native WAF skip bypasses zone managed blocking rules on public hosts instead.
- Before deployment, live `robots.txt` returned homepage HTML. All 44 sitemap URLs were readable with a Googlebot user agent; common AI crawler user agents worked. Default Python-urllib requests returned Cloudflare 403/error 1010. Actual crawler-IP access and live account-level policies remain unverified.
- v6 production preview hit upstream issue `pulumi/pulumi-cloudflare#1637` (`account` rejected as v4 zone state). All ten stored zones still have v5 state, with schema marker `0` or absent. The reported workaround is an encrypted stack export, changing only each zone output's `__meta.schema_version` to `1`, and stack import. User chose to run the commands themselves; stack state was not modified by the agent.
- After the zone repair, preview hit PagesDomain migration (`domain` missing). All eight stored bindings actually retain legacy `domain` fields. Provided a one-time export/import transform: rename input/output `domain` to `name`, preserve old API UUID as `outputs.domainId`, use hostname for Pulumi/output `id`, and set schema version `500`, matching v6.21.0's upstream schema. Transformation checked in memory only; user still applies it. Replaced deprecated `deploymentsEnabled` with `productionDeploymentsEnabled: true` and `previewDeploymentSetting: "all"` in all five Pages projects; TypeScript check passed. New WAF skip-rule previews returned 403; token needs Zone WAF Write for all managed zones.
