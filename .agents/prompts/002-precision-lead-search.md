# Prompt 002: Reboot Imagine Precision Lead Search

## Title

```text
Reboot Imagine Precision Lead Search
```

## Mission

Use the seed files from Prompt 001 to collect raw, high-fit organization leads for Reboot Imagine.

This prompt gathers organization-level leads.

Do not send emails.

Do not create outreach campaigns.

Do not treat raw leads as validated leads.

Do not guess email addresses.

Do not buy, scrape private, or use unauthorized data.

The goal is to build a clean raw lead intake file that future agents can validate, enrich, score, and prioritize.

## Required previous prompt

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
research/seeds/001-search-seed-map.md
research/seeds/002-keyword-bank.md
research/seeds/003-source-map.md
research/seeds/004-example-targets.md
research/seeds/005-negative-filters.md
research/seeds/006-precision-search-queries.md
```

If the seed files do not exist, stop and recommend running:

```text
001-seed-information-collector.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine is best matched to organizations that already believe in XR but need help operating XR reliably at scale.

Search should prioritize organizations with visible signs of:

```text
XR deployment
VR headset fleet
immersive learning lab
simulation center
medical simulation
enterprise VR training
industrial XR training
Meta Quest deployment
Meta for Work
ArborXR
ManageXR
MDM enrollment
device provisioning
XR support burden
pilot-to-scale movement
multi-site rollout
```

Avoid generic XR curiosity.

Avoid consumer VR.

Avoid one-off demos unless there is evidence of operational scale.

## Primary goal

Create a raw lead file containing organizations that appear likely to need Reboot Imagine's XR provisioning, deployment, fleet management, repair, or support services.

The output should be useful for the next prompt:

```text
003-lead-validation-gates.md
```

## Required output files

Create:

```text
intake/raw/YYYY-MM-DD_reboot-imagine_precision_org_leads_raw.csv
intake/raw/YYYY-MM-DD_reboot-imagine_precision_org_leads_raw.json
research/lead-search/002-search-run-summary.md
research/lead-search/002-rejected-or-held-sources.md
```

Use the current date in filenames.

## Search scope

Prioritize the United States and Canada unless the seed files identify a strong reason to search elsewhere.

Primary lead categories:

```text
higher education XR programs
medical schools and simulation centers
hospital innovation and clinical training teams
industrial and enterprise training fleets
XR software vendors
XR training content companies
simulation labs
workforce development organizations using immersive training
location-based entertainment XR operators
enterprise innovation labs
```

## Batch size

For the first run, collect a bounded batch.

Target:

```text
100 to 250 raw organization leads
```

Minimum acceptable batch:

```text
50 raw organization leads
```

Do not exceed:

```text
300 raw organization leads
```

Quality is more important than volume.

## Required raw lead fields

Every raw organization lead should include:

```text
lead_id
collected_at
collector_run_id
organization_name
organization_domain
organization_url
source_url
source_type
source_title
source_date
country
state_or_province
city
ICP_cluster
fit_reason
visible_XR_signal
trigger_signal
trigger_date
trigger_recency_bucket
technology_signal
likely_buyer_department
likely_buyer_titles
organization_type
estimated_size_band
deployment_scale_hint
geographic_fit
public_proof_quote_or_note
confidence_score_raw
priority_hint
status
review_notes
```

## Optional fields

Include when publicly visible:

```text
LinkedIn_company_url
news_url
event_url
grant_url
job_posting_url
procurement_url
partner_ecosystem_signal
Meta_signal
ArborXR_signal
ManageXR_signal
simulation_center_url
immersive_learning_url
training_program_url
```

Do not include personal email addresses in this prompt.

Do not include phone numbers unless they are public generic organization phone numbers.

## Source types to search

Use public sources only.

Preferred sources:

```text
organization websites
university simulation center pages
medical school simulation pages
hospital innovation pages
enterprise training program pages
workforce development program pages
grant announcements
press releases
conference speaker/session pages
job postings
public procurement pages
partner ecosystem pages
ArborXR-related pages
ManageXR-related pages
Meta for Work-related pages
XR vendor customer pages
```

Lower-confidence sources:

```text
generic blogs
old news articles
unverified directories
AI-generated listicles
thin SEO pages
```

Reject or hold if source quality is too weak.

## Search method

Use the precision queries created by Prompt 001.

Run searches in passes.

### Pass 1: High-confidence technology signals

Search for organizations already using or discussing XR operations tooling.

Use query patterns like:

```text
"ArborXR" "VR training" "university"
"ArborXR" "simulation center"
"ManageXR" "enterprise training"
"ManageXR" "VR deployment"
"Meta Quest for Business" "training"
"Meta for Work" "VR training"
"Meta Quest" "medical simulation"
"Meta Quest" "immersive learning lab"
```

### Pass 2: Vertical program signals

Search for visible XR programs by vertical.

Use query patterns like:

```text
"immersive learning lab" "university"
"medical simulation center" "virtual reality"
"clinical simulation" "VR training"
"workforce training" "virtual reality"
"industrial training" "VR"
"safety training" "virtual reality"
"enterprise VR training" "rollout"
"simulation center" "Meta Quest"
```

### Pass 3: Trigger signals

Search for recent signs of urgency.

Use query patterns like:

```text
"new immersive learning lab" "virtual reality"
"VR training program" "grant"
"XR training" "grant awarded"
"simulation center" "opens" "virtual reality"
"virtual reality training" "job posting"
"immersive learning" "director" "hiring"
"VR training" "request for proposal"
"XR" "public procurement" "headsets"
```

### Pass 4: Vendor-side targets

Search for XR software vendors that may need deployment and support help.

Use query patterns like:

```text
"VR training platform" "enterprise"
"XR software vendor" "deployment"
"immersive training platform" "customer success"
"VR training software" "implementation"
"simulation software" "Meta Quest"
"enterprise VR software" "support"
"XR implementation partner" "white label support"
```

### Pass 5: Calibration expansion

Use high-confidence examples from:

```text
research/seeds/004-example-targets.md
```

Find similar organizations by searching:

```text
similar organizations
partner pages
conference peers
program directories
grant cohorts
vendor customer pages
```

Do not blindly scrape every similar result.

Apply the validation gates below.

## Negative filters

Apply negative filters from:

```text
research/seeds/005-negative-filters.md
```

Reject or deprioritize results dominated by:

```text
consumer VR gaming
headset reviews
Steam games
Oculus store apps
Beat Saber
VR arcades with no B2B or operational scale
student-only projects
old metaverse hype
NFT or crypto metaverse content
gameplay videos
generic AR filters
adult entertainment
```

Do not over-filter legitimate location-based entertainment, simulation, or enterprise training operators.

## Raw fit scoring

Assign a preliminary raw confidence score from 0 to 100.

This is not the final outreach score.

Use this raw scoring model:

```text
ICP match: 30
visible XR signal: 20
trigger strength: 20
operational pain likelihood: 15
source quality: 10
geographic fit: 5
```

Priority hints:

```text
80-100 = raw_priority_A
65-79 = raw_priority_B
50-64 = raw_priority_C
below 50 = hold_or_reject
```

## Trigger recency buckets

Use these buckets:

```text
0-90_days
91-180_days
181-365_days
older_than_365_days
unknown
```

Prefer leads with triggers in:

```text
0-90_days
91-180_days
```

Hold leads where the only evidence is older than 18 months unless there is current activity elsewhere.

## Validation gates

Every raw lead must pass Gate 1 and Gate 2 before being written to the raw lead file.

### Gate 1: Public source validity

Pass if:

```text
source is public
source URL resolves
organization exists
source shows relevant context
source can be reviewed later
```

Fail if:

```text
source is private
source requires unauthorized access
source cannot be cited or reviewed
source is unrelated to XR, training, simulation, education, healthcare, enterprise operations, or vendor support
```

### Gate 2: Organization fit

Pass if:

```text
organization matches at least one ICP cluster
there is a visible XR, VR, simulation, training, or deployment signal
there is a plausible operational reason Reboot Imagine could help
```

Fail if:

```text
no clear XR relevance
only consumer entertainment context
only student project context
no organization buyer can be inferred
no visible operational need
```

### Gate 3: Trigger strength

Use this gate for priority, not rejection.

Strong trigger examples:

```text
new lab
new program
new deployment
new grant
new partnership
new job posting
new procurement
new conference session
new vendor customer story
```

Weak trigger examples:

```text
generic innovation language
old article
one-off demo
stale program page
```

### Gate 4: Duplicate check

Before writing a lead, check for duplicates by:

```text
organization_domain
organization_name
organization_url
```

If duplicate exists, merge evidence into the stronger record instead of creating a second row.

## Status values

Use these status values:

```text
raw_collected
raw_priority_A
raw_priority_B
raw_priority_C
hold_needs_more_research
rejected_low_fit
rejected_stale
rejected_consumer_only
rejected_duplicate
rejected_source_quality
```

## Rejected and held sources

Do not ignore rejected searches.

Write rejected or held sources to:

```text
research/lead-search/002-rejected-or-held-sources.md
```

For each rejected or held source, include:

```text
source_url
organization_name
reason_rejected_or_held
search_query_used
notes
```

This helps future agents avoid repeating bad search paths.

## CSV formatting rules

The CSV must:

```text
use UTF-8
include a header row
use one organization per row
quote fields that contain commas
leave unknown fields blank instead of guessing
avoid multiline cells where possible
```

## JSON formatting rules

The JSON must:

```text
be an array of objects
match the CSV field names
preserve source URLs
preserve evidence notes
use null for unknown values
```

## Search-run summary

Create:

```text
research/lead-search/002-search-run-summary.md
```

Include:

```text
date
agent run summary
seed files reviewed
queries used
source types searched
number of raw leads collected
number rejected
number held
top ICP clusters found
best-performing query patterns
worst-performing query patterns
risks
recommended next prompt
```

## Quality bar

A good result is:

```text
smaller but clearly relevant
source-backed
deduplicated
trigger-aware
organized by ICP cluster
easy to validate in the next stage
```

A bad result is:

```text
large but noisy
consumer VR-heavy
missing source URLs
filled with guessed claims
stale
not tied to Reboot Imagine's operational offer
```

## Stop conditions

Stop and mark blocked if:

```text
seed files are missing
Reboot Imagine positioning cannot be confirmed
search results are mostly consumer VR noise
source URLs cannot be captured
fewer than 50 qualified raw organization leads can be found after multiple query passes
the search starts collecting emails before organization-level fit is established
compliance risk appears unresolved
```

## Final response format

Return:

```text
1. Raw lead search summary
2. Number of raw leads collected
3. Number of rejected or held sources
4. Best ICP clusters found
5. Best-performing search queries
6. Weak or noisy search queries
7. Files created
8. Risks or blocked items
9. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
003-lead-validation-gates.md
```

That prompt should validate, enrich, deduplicate, score, and prepare the raw leads for human-reviewed outreach readiness.
