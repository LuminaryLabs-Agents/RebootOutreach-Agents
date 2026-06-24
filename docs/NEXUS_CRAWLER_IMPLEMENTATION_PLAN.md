# Nexus Crawler Implementation Plan

## Overall goal

Build Nexus Crawler as a usable public-web trigger detection MVP for Reboot Outreach.

The system should find public buying signals, normalize them into structured records, score them, prevent duplicates, and make them reviewable.

## Product mentality

Build the smallest useful signal engine first.

Do not overbuild the full GTM stack.

Do not start with enrichment, email automation, or CRM automation.

The crawler must first prove that it can reliably turn public web pages into structured signal events.

## MVP architecture

```text
Nexus Crawler
  Source Registry
    approved URLs
    source type
    crawl priority
    enabled flag

  Crawler Worker
    schedule
    rate limit
    retry limit
    crawl logs

  Fetcher
    safe public page fetch
    response metadata
    failure handling

  Parser
    title
    text
    links
    metadata
    dates

  Signal Detector
    keyword rules
    phrase patterns
    source-category rules
    optional AI classifier later

  Deduper
    source URL fingerprint
    normalized title fingerprint
    evidence hash
    event fingerprint

  Scorer
    relevance score
    confidence score
    urgency score

  Storage
    sources
    pages
    crawl runs
    signal events

  Review Surface
    admin dashboard or API
    CSV export
    webhook adapter
```

## Suggested database tables

### sources

- id
- url
- domain
- source_type
- priority
- enabled
- crawl_interval_minutes
- created_at
- updated_at

### crawl_runs

- id
- source_id
- started_at
- finished_at
- status
- http_status
- error_message
- content_hash

### pages

- id
- source_id
- crawl_run_id
- url
- title
- text_excerpt
- published_at
- fetched_at
- content_hash

### signal_events

- id
- source_id
- page_id
- source_url
- organization_name
- organization_type
- source_type
- signal_type
- signal_title
- signal_summary
- detected_at
- published_at
- confidence_score
- relevance_score
- urgency_score
- matched_keywords
- evidence_snippet
- recommended_next_action
- status
- event_fingerprint

## Milestone 1: Source registry

Goal:

Allow approved URLs to be added, listed, enabled, disabled, and categorized.

Deliverables:

- Source model/table
- Add source route or command
- List sources route or command
- Enable/disable field
- Seed import support

Validation:

- Add FDA URL
- Add NIH URL
- Add hospital jobs URL
- Disable one source
- Confirm disabled source is skipped

## Milestone 2: Fetcher and crawl logs

Goal:

Fetch public pages safely and record the result.

Deliverables:

- Fetcher module
- Timeout
- Retry limit
- Rate limit
- Crawl log table
- Failure handling

Validation:

- Fetch a valid page
- Fetch a broken URL
- Confirm failure is logged without crashing

## Milestone 3: Parser

Goal:

Extract useful page content.

Deliverables:

- HTML title extraction
- Main text extraction
- Link extraction
- Metadata/date extraction where possible
- Text normalization

Validation:

- Parser test with simple HTML
- Parser test with real public page fixture

## Milestone 4: Signal detector

Goal:

Detect healthcare XR and medical simulation trigger events.

Deliverables:

- Keyword and phrase rules
- Signal type mapping
- Evidence snippet extraction
- Matched keyword list
- Signal summary generation

Validation:

- Synthetic medical simulation page creates signal
- Job page with VR healthcare role creates hiring signal
- Irrelevant page creates no signal

## Milestone 5: Dedupe and scoring

Goal:

Avoid repeated events and rank useful signals.

Deliverables:

- Event fingerprint
- Content hash
- Confidence score
- Relevance score
- Urgency score

Validation:

- Same page crawled twice does not duplicate events
- Vendor evaluation language ranks high
- Generic informational page ranks low

## Milestone 6: Review API or dashboard

Goal:

Make detected signals reviewable.

Deliverables:

- List signals
- Filter by status
- Filter by signal type
- Mark reviewed
- Mark dismissed
- Show source URL and evidence snippet

Validation:

- Signal appears after crawl
- Signal status can be changed

## Milestone 7: Export and adapter stubs

Goal:

Allow signals to leave the crawler without coupling to one vendor.

Deliverables:

- CSV export
- Generic webhook adapter
- Placeholder adapter notes for Clay, HubSpot, n8n, and CRM sync

Validation:

- Export creates CSV
- Webhook payload shape matches signal event schema

## Final MVP acceptance

The MVP is usable when:

- It runs locally.
- Sources can be managed.
- Approved public URLs can be crawled.
- Content can be parsed.
- Signals can be detected.
- Duplicates are avoided.
- Signals are scored.
- Signals are reviewable.
- CSV export works.
- Tests pass.
- Setup docs are clear.
