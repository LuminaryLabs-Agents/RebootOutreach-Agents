# Prompt 002: Nexus Crawler MVP

## Title

Nexus Crawler MVP Implementation

## Goal

Turn Nexus Crawler into a usable public-web trigger detection MVP.

## Product definition

Nexus Crawler is not a generic scraper.

It is a public-web signal detection engine that crawls approved public sources, detects business trigger events, stores evidence, dedupes repeated findings, scores relevance, and exposes structured signal records for review or export.

## Scope

Implement the crawler as an ingestion and signal-detection layer only.

Do not implement full enrichment, outbound email, or CRM automation yet.

Adapter stubs are allowed.

## MVP requirements

- Source registry for approved public URLs
- Safe crawler worker with rate limits
- Parser for page title, text, links, metadata, and timestamps
- Signal detector for healthcare XR and medical simulation triggers
- Deduplication logic
- Confidence and relevance scoring
- Database schema for sources, pages, crawl runs, and signal events
- Admin dashboard or API for reviewing signals
- CSV export
- Webhook adapter interface
- Local setup instructions
- Tests for parser, detector, deduper, and scorer

## Safety requirements

- Crawl public pages only.
- Do not bypass login.
- Do not bypass paywalls.
- Do not bypass CAPTCHAs.
- Respect robots.txt where applicable.
- Add retry limits.
- Add rate limits.
- Add domain-level enable/disable.
- Store only necessary business signal data.
- Keep crawl logs.

## Signal types

The MVP should detect these first:

- Hiring surge
- Simulation technician role
- Director of immersive learning role
- VR healthcare developer role
- Medical simulation expansion
- Healthcare innovation grant
- Simulation lab launch
- Regulatory or accreditation update
- Vendor evaluation or procurement timeline

## Expected signal event shape

```json
{
  "source_url": "",
  "organization_name": "",
  "organization_type": "",
  "source_type": "",
  "signal_type": "",
  "signal_title": "",
  "signal_summary": "",
  "detected_at": "",
  "published_at": "",
  "confidence_score": 0,
  "relevance_score": 0,
  "matched_keywords": [],
  "evidence_snippet": "",
  "recommended_next_action": "",
  "status": "new"
}
```

## Implementation process

1. Read `docs/REBOOT_OUTREACH_MEMORY.md`.
2. Read `docs/NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md`.
3. Read `docs/NEXUS_CRAWLER_ACCEPTANCE.md`.
4. Inspect the target application repo if one is provided.
5. Implement one milestone only.
6. Update the memory with decisions, files changed, validation, and next action.
7. Run tests or log why validation could not run.

## Completion criteria

The batch is complete only when:

- The implementation remains scoped to the current milestone.
- The memory is updated.
- Validation results are logged.
- The next action is clear.
