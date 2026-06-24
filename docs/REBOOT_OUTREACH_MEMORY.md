# Reboot Outreach Memory

## Product identity

Reboot Outreach is the GTM and signal-detection operating system around Nexus Crawler.

Its first implementation target is a public-web trigger detection crawler for healthcare XR, medical simulation, hospital innovation, grants, hiring, and regulatory signals.

## Core product rule

Nexus Crawler detects structured business signals from approved public pages and stores them as reviewable lead events.

It is not a generic scraper.

It is not an email sender.

It is not the full GTM stack yet.

It is the ingestion and signal-detection layer.

## Current MVP scope

- Public URL source registry
- Scheduled crawler worker
- Safe page fetcher
- Parser for text, links, title, metadata, and timestamps
- Signal detector for healthcare XR and medical simulation triggers
- Deduplication logic
- Relevance and confidence scoring
- Database storage for sources, pages, crawl runs, and signal events
- Admin review dashboard or API
- CSV export
- Webhook adapter interface
- Tests for parser, detector, deduper, and scorer

## Out of scope

- Non-public sources
- Account-only pages
- Paywalled pages
- Private systems
- Automated cold email sending
- Hard-coded Clay dependency
- Hard-coded HubSpot dependency
- Hard-coded Smartlead or Instantly dependency
- Full enrichment waterfall
- Full CRM automation

## Target source types

- Hospital career pages
- University job boards
- Medical simulation center pages
- Medical education pages
- Hospital innovation lab pages
- Grant and funding announcement pages
- FDA AR/VR medical device pages
- ACGME requirements and updates
- ClinicalTrials public study pages
- PubMed or PMC clinical evidence pages
- Public press releases
- Public newsletters or RSS feeds

## First signal types

- Hiring surge
- Simulation technician role
- Director of immersive learning role
- VR healthcare developer role
- Medical simulation expansion
- Healthcare innovation grant
- Simulation lab launch
- Regulatory or accreditation update
- Vendor evaluation or procurement timeline

## Required signal record

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

## Architecture decisions

- Keep crawler logic separate from enrichment and outreach.
- Use adapters for future integrations.
- Store evidence snippets for every detected signal.
- Dedupe by source URL, normalized title, event fingerprint, and detected content hash.
- Use deterministic scoring first.
- Add LLM classification later only after rule-based signals are stable.
- Make source domains disableable.
- Log crawl failures.
- Root `output.md` is the short status text source.
- `output-rules.md` controls the short status style.
- `.agent/output.md` is the internal run log.
- `.github/workflows/reboot-outreach-output.yml` follows the Lost Pages-style three-step loop: validate, prepare-summary, notify.

## Safety posture

The crawler must:

- Crawl approved public pages only.
- Avoid account-only or restricted areas.
- Use rate limits.
- Follow site access rules where applicable.
- Store only necessary business signal data.
- Keep crawl logs.
- Make it easy to remove or disable a source.

## Implementation status

Current milestone: Ready for Nexus Crawler MVP implementation.

Completed:

- Agent repo initialized.
- README added.
- Agent pointer added.
- Agent workflow added.
- Prompt files added.
- Workflow loop files added.
- Product memory added.
- Nexus Crawler MVP implementation plan added.
- Acceptance checklist added.
- Medical seed URL list added.
- Root `output.md` added.
- Root `output-rules.md` added.
- Lost Pages-style output workflow added.
- Old generated summary workflow removed.

In progress:

- Prepare for Nexus Crawler MVP implementation.

Blocked:

- No target application repo has been selected yet for actual crawler code.
- The status workflow requires GitHub secret `DISCORD_WEBHOOK_URL`.

Next:

- Run `.agent/prompts/002-nexus-crawler-mvp.md` against the selected implementation repo.

## Validation log

### 2026-06-24 - Bootstrap

Goal:

Create the memory-first agent repo for Reboot Outreach.

Files changed:

- README.md
- .agent/pointer.md
- .agent/workflow.md
- .agent/output.md
- .agent/prompts/001-bootstrap-reboot-outreach.md
- .agent/prompts/002-nexus-crawler-mvp.md
- .agent/prompts/003-medical-source-seed-list.md
- .agent/workflows/implementation-loop.md
- .agent/workflows/crawler-validation-loop.md
- docs/REBOOT_OUTREACH_MEMORY.md
- docs/NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md
- docs/NEXUS_CRAWLER_ACCEPTANCE.md
- docs/MEDICAL_CRAWL_SEED_URLS.md
- .github/workflows/discord-summary.yml

Validation:

- Repository file creation through GitHub contents API.

Result:

- Bootstrap files pushed to main.

Known issues:

- No application code exists in this repo yet.

Next action:

- Add actual Nexus Crawler implementation or point Codex at the target crawler app repo.

### 2026-06-24 - Lost Pages-style output loop

Goal:

Adapt the Lost Pages output pattern to Reboot Outreach.

Files changed:

- output.md
- output-rules.md
- README.md
- .agent/workflow.md
- .agent/output.md
- .agent/pointer.md
- docs/REBOOT_OUTREACH_MEMORY.md
- .github/workflows/reboot-outreach-output.yml
- .github/workflows/discord-summary.yml removed

Decisions made:

- Reboot Outreach does not use a GitHub Pages deploy step yet.
- The adapted three-step loop is validate, prepare-summary, notify.
- Root `output.md` is the short status source.
- Generated memory dumps are no longer used as the status text.

Validation:

- Required file checks are now encoded in the workflow validate job.
- Workflow creation and file updates completed through the GitHub contents API.

Result:

- Reboot Outreach now follows the Lost Pages-style output contract.

Known issues:

- The workflow only posts externally when `DISCORD_WEBHOOK_URL` is present as a repository secret.

Next action:

- Run the Nexus Crawler MVP prompt.
