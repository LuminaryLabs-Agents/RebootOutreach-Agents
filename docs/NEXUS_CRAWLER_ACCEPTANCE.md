# Nexus Crawler Acceptance Checklist

Use this checklist to decide whether the MVP is actually usable.

## Product acceptance

- [ ] The crawler is clearly scoped as public-web signal detection.
- [ ] The crawler is not positioned as a generic scraper.
- [ ] The crawler is not coupled to email sending.
- [ ] The crawler is not coupled to one CRM or enrichment vendor.
- [ ] The system can run locally.

## Source registry acceptance

- [ ] User can add a source URL.
- [ ] User can list sources.
- [ ] User can disable a source.
- [ ] Disabled sources are skipped.
- [ ] Each source has a type.
- [ ] Each source has a priority.

## Fetcher acceptance

- [ ] Fetcher can retrieve a valid public page.
- [ ] Fetcher handles bad URLs safely.
- [ ] Fetcher has timeout logic.
- [ ] Fetcher has retry limits.
- [ ] Fetcher records crawl runs.
- [ ] Fetcher records HTTP status when available.

## Parser acceptance

- [ ] Parser extracts title.
- [ ] Parser extracts normalized text.
- [ ] Parser extracts links.
- [ ] Parser extracts page metadata where available.
- [ ] Parser extracts or infers dates where reasonable.
- [ ] Parser has tests.

## Signal detector acceptance

- [ ] Detector identifies medical simulation expansion.
- [ ] Detector identifies healthcare XR language.
- [ ] Detector identifies relevant hiring roles.
- [ ] Detector identifies grant or funding language.
- [ ] Detector identifies regulatory or accreditation language.
- [ ] Detector ignores irrelevant pages.
- [ ] Detector stores evidence snippets.
- [ ] Detector stores matched keywords or reasons.

## Dedupe acceptance

- [ ] Re-crawling the same page does not create duplicate signal events.
- [ ] Similar titles are normalized.
- [ ] Event fingerprints are stored.
- [ ] Content hashes are stored.

## Scoring acceptance

- [ ] Each signal has a confidence score.
- [ ] Each signal has a relevance score.
- [ ] Each signal has an urgency score or clear urgency category.
- [ ] Vendor evaluation and procurement language ranks high.
- [ ] Generic informational language ranks lower.

## Review acceptance

- [ ] Signals can be listed.
- [ ] Signals can be filtered by type.
- [ ] Signals can be filtered by status.
- [ ] Signal detail shows source URL.
- [ ] Signal detail shows evidence snippet.
- [ ] Signal can be marked reviewed.
- [ ] Signal can be dismissed.

## Export acceptance

- [ ] Signal events can be exported as CSV.
- [ ] CSV contains source URL.
- [ ] CSV contains organization name when known.
- [ ] CSV contains signal type.
- [ ] CSV contains summary.
- [ ] CSV contains scores.
- [ ] CSV contains evidence snippet.

## Adapter acceptance

- [ ] Generic webhook adapter exists.
- [ ] Adapter payload uses the signal event schema.
- [ ] Clay, HubSpot, n8n, or CRM integrations are not hard-coded into crawler logic.

## Documentation acceptance

- [ ] README explains local setup.
- [ ] README explains environment variables.
- [ ] README explains how to seed URLs.
- [ ] README explains how to run a crawl.
- [ ] README explains how to review/export signals.
- [ ] Memory file reflects latest state.

## Validation acceptance

- [ ] Unit tests pass.
- [ ] Build passes.
- [ ] Typecheck passes if applicable.
- [ ] Lint passes if applicable.
- [ ] Known failures are logged in memory with next actions.

## Safety acceptance

- [ ] Only approved public URLs are crawled.
- [ ] Account-only or restricted areas are out of scope.
- [ ] Rate limits are present.
- [ ] Source domains can be disabled.
- [ ] Crawl logs exist.
- [ ] Stored data is limited to business signal review needs.
