# Prompt 003: Reboot Imagine Lead Validation Gates

## Title

```text
Reboot Imagine Lead Validation Gates
```

## Mission

Validate, enrich, deduplicate, and score raw organization leads collected for Reboot Imagine.

This prompt turns raw organization leads into a clean, reviewed, prioritized lead-validation file.

Do not send emails.

Do not create outreach campaigns.

Do not mark any lead as send-ready without human review.

Do not guess missing data.

Do not use private, purchased, or unauthorized sources.

The goal is to decide which raw leads deserve deeper contact research and which should be rejected, held, or prioritized.

## Required previous prompts

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
.agents/prompts/002-precision-lead-search.md
```

Also review the latest raw lead files from:

```text
intake/raw/
```

Expected raw files:

```text
YYYY-MM-DD_reboot-imagine_precision_org_leads_raw.csv
YYYY-MM-DD_reboot-imagine_precision_org_leads_raw.json
```

If raw lead files do not exist, stop and recommend running:

```text
002-precision-lead-search.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine is strongest for organizations that already have XR activity and need operational support.

Validate leads against operational XR fit, not generic innovation interest.

Strong-fit signs include:

```text
XR deployment
VR headset fleet
headset provisioning need
MDM enrollment need
Meta for Work signal
ArborXR signal
ManageXR signal
simulation lab
immersive learning program
medical simulation program
enterprise VR training
industrial training rollout
multi-site training
XR software vendor support burden
pilot-to-scale transition
```

Weak-fit signs include:

```text
consumer VR gaming only
one-off demo
student-only project
old XR mention with no recent activity
metaverse hype without deployment
no clear buyer or operational owner
```

## Primary goal

Create a validated lead file that future agents can use for contact research and outreach-prioritization.

This prompt should answer:

```text
Which raw leads are real?
Which are duplicates?
Which match Reboot Imagine's ICP?
Which have visible operational XR need?
Which have strong timing triggers?
Which are worth contact research next?
Which should be rejected or held?
```

## Required output files

Create:

```text
processed/validated/YYYY-MM-DD_reboot-imagine_validated_org_leads.csv
processed/validated/YYYY-MM-DD_reboot-imagine_validated_org_leads.json
processed/validated/YYYY-MM-DD_reboot-imagine_rejected_org_leads.csv
research/validation/003-validation-run-summary.md
research/validation/003-field-completeness-report.md
research/validation/003-duplicate-resolution-log.md
```

Use the current date in filenames.

## Input fields to review

Read all raw lead fields from Prompt 002.

Minimum expected fields:

```text
lead_id
organization_name
organization_domain
organization_url
source_url
source_type
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

Do not discard raw fields.

Preserve them and add validation fields.

## New validation fields to add

Add these fields to every validated lead:

```text
validation_status
validation_notes
duplicate_status
canonical_organization_name
canonical_domain
organization_exists_status
website_resolves_status
ICP_fit_score
XR_signal_score
trigger_score
operational_pain_score
buyer_department_score
source_quality_score
geography_score
compliance_risk_score
final_org_score
final_priority_band
recommended_next_action
contact_research_needed
contact_research_persona_targets
human_review_required
```

## Validation status values

Use these values:

```text
validated_priority_A
validated_priority_B
validated_priority_C
hold_needs_more_research
rejected_duplicate
rejected_low_fit
rejected_no_xr_signal
rejected_stale
rejected_consumer_only
rejected_source_quality
rejected_geographic_mismatch
rejected_compliance_risk
```

## Recommended next actions

Use these values:

```text
advance_to_contact_research
hold_for_more_evidence
merge_duplicate
reject
manual_review_required
```

## Gate 1: File integrity

Check that the raw input file is usable.

Pass if:

```text
file exists
file opens cleanly
headers are present
rows are readable
source URLs are preserved
```

Fail if:

```text
file is missing
file is malformed
headers are absent
source URLs are missing
```

If Gate 1 fails, stop and report the issue.

## Gate 2: Organization existence

Verify that the organization appears to exist.

Pass if:

```text
organization has a working website or credible public page
organization name matches the source context
organization is not only a product, event, or article title
```

Fail if:

```text
organization cannot be verified
website does not resolve and no credible alternative source exists
source refers only to a product, blog post, or event
```

## Gate 3: Deduplication

Deduplicate leads before scoring.

Check duplicates by:

```text
organization_domain
canonical_domain
organization_name
organization_url
LinkedIn_company_url
```

Rules:

```text
same domain = duplicate unless clearly different subsidiaries
same organization name + same location = likely duplicate
same source URL = duplicate
same LinkedIn company URL = duplicate
```

When duplicates are found:

```text
choose the record with the strongest source evidence
merge useful notes and triggers into the canonical record
log the duplicate in duplicate-resolution-log.md
do not create duplicate validated rows
```

## Gate 4: ICP fit

Score ICP fit from 0 to 30.

High score:

```text
clear match to one target ICP
organization publicly runs XR, VR, simulation, immersive learning, or enterprise training
Reboot Imagine's operational offer is plausibly relevant
```

Medium score:

```text
adjacent ICP
some training, simulation, or innovation relevance
XR signal is present but weak
```

Low score:

```text
generic organization
unclear XR relevance
consumer or student-only context
```

Reject if:

```text
no ICP match
no plausible Reboot Imagine fit
consumer-only or student-only context
```

## Gate 5: XR signal strength

Score XR signal from 0 to 20.

Strong signals:

```text
Meta Quest deployment
Meta for Work mention
ArborXR mention
ManageXR mention
headset fleet
VR training rollout
simulation center using VR
immersive learning lab
XR procurement
XR RFP
device management reference
```

Medium signals:

```text
general immersive learning page
VR training article
conference talk
program description
old case study with possible ongoing relevance
```

Weak signals:

```text
one-off demo
student showcase
generic innovation page
VR mentioned only once with no program context
```

Reject if there is no visible XR, VR, immersive, simulation, or deployment signal.

## Gate 6: Trigger and recency

Score trigger strength from 0 to 20.

Use the trigger date if available.

Strong recent triggers:

```text
0-90 days: 18-20 points
91-180 days: 14-17 points
181-365 days: 8-13 points
older than 365 days with current program evidence: 4-7 points
unknown date but strong current page: 4-7 points
```

Trigger examples:

```text
new lab
new program
new deployment
grant award
job posting
public procurement
new partnership
conference session
customer story
new training rollout
```

Hold if the only evidence is older than 18 months.

Reject if the evidence is stale and no current activity is visible.

## Gate 7: Operational pain likelihood

Score operational pain likelihood from 0 to 15.

High score:

```text
multi-site deployment
headset fleet
regulated setting
simulation center
classroom or lab deployment
enterprise training rollout
vendor selling XR software to customers
public mention of scale, support, deployment, or operations
```

Medium score:

```text
single lab or single program with likely device usage
program appears active but scale is unclear
```

Low score:

```text
one-off demo
small project
no visible scale
no support or deployment complexity
```

## Gate 8: Buyer department clarity

Score buyer department fit from 0 to 10.

High score:

```text
clear department owns simulation, training, innovation, IT, operations, customer success, or implementation
likely buyer titles can be inferred
```

Medium score:

```text
department visible but buyer title unclear
```

Low score:

```text
no clear department
only generic organization page
```

Do not collect personal contacts in this prompt unless they are already present in the raw file.

Only identify likely persona targets for the next prompt.

## Gate 9: Source quality

Score source quality from 0 to 10.

High-quality sources:

```text
organization website
official program page
official press release
public procurement page
grant announcement
credible conference page
official partner/customer page
```

Medium-quality sources:

```text
credible news article
industry publication
conference recap
public job posting
```

Low-quality sources:

```text
thin directory
AI-generated listicle
unverified blog
social post with no supporting source
```

Reject if the only source is low-quality and cannot be verified elsewhere.

## Gate 10: Geography and service-region fit

Score geography from 0 to 5.

Default priority:

```text
United States
Canada
```

Score high if:

```text
organization is in the United States or Canada
organization has North American operations
```

Hold if:

```text
organization is outside the likely service region but otherwise high-fit
```

Reject only if geography clearly makes service irrelevant.

## Gate 11: Compliance risk

Score compliance risk from 0 to 5.

High score means low risk.

Low-risk signs:

```text
B2B organization
clear business relevance
public organization context
role-based future contact research is plausible
```

Risk flags:

```text
sensitive health context with unclear business basis
minors or student-only context
consumer-only targeting
personal contact data without clear business relevance
jurisdiction uncertainty
```

Do not reject healthcare or education leads automatically.

Flag them for human review when needed.

## Final organization score

Calculate:

```text
ICP_fit_score: 30
XR_signal_score: 20
trigger_score: 20
operational_pain_score: 15
buyer_department_score: 10
source_quality_score: 10
geography_score: 5
compliance_risk_score: 5
```

Normalize to 100 if needed.

Priority bands:

```text
85-100 = validated_priority_A
70-84 = validated_priority_B
55-69 = validated_priority_C
below 55 = hold or reject
```

## Priority A requirements

A lead can only be Priority A if all are true:

```text
organization exists
not duplicate
clear ICP match
clear XR signal
clear operational pain likelihood
source URL is strong
business relevance is clear
contact research target personas are identifiable
```

Priority A does not mean send-ready.

Priority A means ready for contact research.

## Priority B requirements

A lead can be Priority B if:

```text
organization exists
ICP match is strong or moderate
XR signal exists
trigger or operational pain is plausible
some fields need enrichment
```

Priority B should usually go to contact research after Priority A.

## Priority C requirements

A lead can be Priority C if:

```text
organization is real
some fit exists
XR signal is weak or trigger is unclear
more research is needed before contact work
```

## Hold conditions

Hold leads when:

```text
source is promising but incomplete
XR signal exists but is stale
organization is outside likely geography but strategically relevant
buyer department is unclear
trigger needs confirmation
```

## Reject conditions

Reject leads when:

```text
duplicate
no XR signal
consumer-only VR/gaming
student-only project
source cannot be validated
stale with no current activity
no plausible operational need
clear compliance risk
```

## Human review requirements

Mark `human_review_required = true` if:

```text
healthcare or clinical context
student/minor context
uncertain jurisdiction
high-value but ambiguous fit
weak source but strong possible fit
outside United States or Canada
sensitive program area
```

Human review does not block validation.

It blocks outreach readiness.

## Field completeness report

Create:

```text
research/validation/003-field-completeness-report.md
```

Include:

```text
total raw rows
rows with organization domain
rows with source URL
rows with ICP cluster
rows with trigger signal
rows with technology signal
rows with likely buyer titles
rows with missing critical fields
recommended fixes
```

## Duplicate resolution log

Create:

```text
research/validation/003-duplicate-resolution-log.md
```

For every duplicate group, include:

```text
canonical_organization_name
canonical_domain
kept_lead_id
merged_or_rejected_lead_ids
reason kept
merged evidence
```

## Rejected lead file

Create:

```text
processed/validated/YYYY-MM-DD_reboot-imagine_rejected_org_leads.csv
```

Include:

```text
lead_id
organization_name
organization_domain
source_url
rejection_reason
rejection_notes
original_status
```

Do not silently discard rejected rows.

## Validation run summary

Create:

```text
research/validation/003-validation-run-summary.md
```

Include:

```text
date
input files reviewed
total raw leads
validated Priority A count
validated Priority B count
validated Priority C count
held count
rejected count
duplicate count
top ICP clusters
common rejection reasons
common missing fields
recommended next prompt
```

## Quality bar

A good validation run is:

```text
strict
source-backed
deduplicated
clear about uncertainty
honest about missing data
organized for the next contact-research step
```

A bad validation run is:

```text
overconfident
keeps noisy leads
guesses missing information
treats raw leads as send-ready
ignores compliance risk
drops rejected rows without logging
```

## Stop conditions

Stop and mark blocked if:

```text
raw lead files are missing
raw lead files are malformed
source URLs are mostly missing
more than 50 percent of leads have no visible XR signal
deduplication cannot be performed
validation criteria cannot be applied consistently
```

## Final response format

Return:

```text
1. Validation summary
2. Input files reviewed
3. Validated Priority A count
4. Validated Priority B count
5. Validated Priority C count
6. Held count
7. Rejected count
8. Duplicate count
9. Top rejection reasons
10. Files created
11. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
004-contact-research-and-email-validation.md
```

That next prompt should identify decision-maker contacts, validate emails, apply compliance checks, and prepare leads for human-reviewed outreach prioritization.
