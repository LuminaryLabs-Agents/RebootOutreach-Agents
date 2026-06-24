# Prompt 006: Reboot Imagine Email Sequence and Messaging Drafts

## Title

```text
Reboot Imagine Email Sequence and Messaging Drafts
```

## Mission

Draft segment-specific cold email sequences for Reboot Imagine using the prioritized outreach queue.

This prompt prepares copy for human review.

Do not send emails.

Do not upload emails into a sequencer.

Do not mark any sequence as approved.

Do not invent proof points, case studies, metrics, partnerships, or customer outcomes.

The goal is to create clear, low-pressure, compliant draft emails that match each contact's segment, role, trigger, and operational pain.

## Required previous prompts

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
.agents/prompts/002-precision-lead-search.md
.agents/prompts/003-lead-validation-gates.md
.agents/prompts/004-contact-research-and-email-validation.md
.agents/prompts/005-prioritized-outreach-queue.md
```

Also review latest outreach files from:

```text
processed/outreach/
research/outreach/
```

Expected input files:

```text
processed/outreach/YYYY-MM-DD_reboot-imagine_prioritized_outreach_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_hold_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_suppression_review_queue.csv
research/outreach/005-message-angle-map.md
research/outreach/005-human-review-checklist.md
research/outreach/005-outreach-queue-summary.md
```

If the prioritized outreach queue does not exist, stop and recommend running:

```text
005-prioritized-outreach-queue.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine's strongest cold-email narrative is operational, not conceptual.

Do not pitch generic XR innovation.

Lead with the operational gap:

```text
XR programs usually do not fail because of vision.
They fail because provisioning, support, repair, fleet operations, and scale are under-designed.
```

Primary message families:

```text
pilot-to-scale
downtime reduction
fleet provisioning
MDM and device management
simulation lab readiness
training rollout support
vendor support relief
white-label deployment support
repair, RMA, and lifecycle
```

## Primary goal

Create draft email sequences for each approved segment and message angle.

Each sequence should include:

```text
subject-line options
email 1
email 2
email 3
email 4 / close-the-loop
personalization tokens
CTA
proof point guidance
compliance footer placeholder
human review checklist
```

## Required output files

Create:

```text
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_segment_sequences.md
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_segment_sequences.json
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_subject-line-bank.md
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_personalization-token-map.md
research/messaging/006-messaging-run-summary.md
research/messaging/006-copy-risk-review.md
research/messaging/006-human-approval-checklist.md
```

Use the current date in filenames.

## Input queue rules

Only draft for contacts or segments that are in:

```text
queue_wave_1_ready_for_human_review
queue_wave_2_ready_for_human_review
```

Do not draft active send copy for:

```text
suppression_review
do_not_contact
hold_email_validation_needed
hold_compliance_review_needed
hold_suppression_process_missing
hold_weak_trigger
hold_low_role_fit
queue_wave_3_needs_more_personalization
```

For held leads, write notes only.

Do not create usable email copy for suppressed or do-not-contact records.

## Sequence cadence

Default sequence:

```text
Touch 1: Day 1
Touch 2: Day 4
Touch 3: Day 8
Touch 4: Day 12
```

Use this as copy context only.

Do not schedule messages.

Do not configure automation.

## Email style rules

Each email should be:

```text
plain text
short
specific
low-pressure
business-relevant
source-backed
non-deceptive
free of fake familiarity
free of exaggerated claims
easy to opt out of
```

Length targets:

```text
Email 1: 80 to 130 words
Email 2: 60 to 100 words
Email 3: 60 to 110 words
Email 4: 45 to 85 words
```

Avoid:

```text
hype
buzzword-heavy XR language
false urgency
fake compliments
unverified case-study claims
ROI numbers unless sourced
attachments
tracking-heavy language
aggressive meeting asks
```

## Required placeholders

Use placeholders, not guessed values.

Allowed placeholders:

```text
{{first_name}}
{{organization_name}}
{{sender_name}}
{{sender_title}}
{{sender_company}}
{{sender_email}}
{{sender_phone_optional}}
{{organization_trigger}}
{{visible_XR_signal}}
{{message_angle}}
{{proof_point}}
{{resource_offer}}
{{unsubscribe_line}}
{{postal_address}}
```

Do not include unavailable personal details.

Do not invent a recipient's problem.

Phrase inferred pain carefully.

Example:

```text
If your team is scaling this beyond a pilot, the support model may become the bottleneck.
```

Avoid:

```text
I know your team is struggling with headset support.
```

## Compliance placeholders

Every email draft must include placeholders for:

```text
sender identity
organization identity
opt-out / unsubscribe language
postal address
```

Default footer placeholder:

```text
{{sender_name}}, {{sender_title}} at {{sender_company}}
{{postal_address}}
{{unsubscribe_line}}
```

Do not include final legal text unless the sender identity, address, and unsubscribe process are confirmed.

## Segment sequence requirements

Draft sequences for these segments when they exist in the queue:

```text
higher_education_xr
medical_simulation
healthcare_innovation
enterprise_training
industrial_training
xr_software_vendor
workforce_development
location_based_entertainment
enterprise_innovation_lab
```

For each segment, include:

```text
segment
target personas
primary pain
message angle
subject options
4-touch sequence
personalization tokens
proof-point guidance
CTA guidance
copy risks
human review notes
```

## CTA rules

Use low-pressure CTAs.

Allowed CTAs:

```text
Would it be useful if I sent over a short checklist?
Worth comparing notes?
Would a 5-point XR ops review be useful?
Is there someone else who owns XR support on your team?
Open to a quick note exchange?
Should I close this out for now?
```

Avoid:

```text
Book 30 minutes here
Can you meet tomorrow?
Are you the decision maker?
I guarantee we can reduce costs
```

## Proof-point rules

Use only proof points already verified in prior research.

Allowed proof directions:

```text
Meta for Work authorized reseller status
ArborXR / ManageXR ecosystem alignment
REK0 deployment story
XR-native MSP positioning
provisioning and RMA services
custom kitting and shipping
white-label vendor support
24/7 support tier where publicly supported
```

Do not write:

```text
we helped dozens of companies
we reduced downtime by X percent
we saved X hours
we are the leading provider
```

unless those exact claims are publicly verified.

## Message family: Higher education XR

Use when segment is:

```text
higher_education_xr
```

Primary pain:

```text
immersive learning pilots become hard to support once they move into classrooms, labs, courses, or multiple departments
```

Recommended angle:

```text
pilot_to_scale
simulation_lab_readiness
headset_support_burden
```

Preferred CTA:

```text
send_checklist
```

## Message family: Medical simulation

Use when segment is:

```text
medical_simulation
healthcare_innovation
```

Primary pain:

```text
clinical and simulation XR programs need reliable device readiness, support discipline, and operational control
```

Recommended angle:

```text
simulation_lab_readiness
compliance_and_operational_control
downtime_reduction
```

Preferred CTA:

```text
offer_sim_lab_readiness_review
```

Use extra caution.

Avoid implying knowledge of patient data, PHI, treatment workflows, or private clinical operations.

## Message family: Enterprise and industrial training

Use when segment is:

```text
enterprise_training
industrial_training
workforce_development
```

Primary pain:

```text
VR training programs become operationally fragile when devices, sites, repairs, updates, and local support are not standardized
```

Recommended angle:

```text
downtime_reduction
training_rollout_support
fleet_provisioning
```

Preferred CTA:

```text
offer_5_point_ops_review
```

## Message family: XR software vendors

Use when segment is:

```text
xr_software_vendor
```

Primary pain:

```text
software teams get pulled into customer deployment, headset setup, onboarding, and support issues that are not core product work
```

Recommended angle:

```text
vendor_support_relief
white_label_deployment_support
fleet_provisioning
```

Preferred CTA:

```text
offer_vendor_support_outline
```

## Message family: Location-based entertainment

Use when segment is:

```text
location_based_entertainment
```

Primary pain:

```text
public-facing XR experiences need fast device readiness, replacement flow, repair support, and event/venue uptime
```

Recommended angle:

```text
downtime_reduction
repair_RMA_and_lifecycle
fleet_provisioning
```

Preferred CTA:

```text
ask_current_support_model
```

## Subject line rules

Create 5 to 10 subject options per segment.

Subject lines should be:

```text
plain
specific
non-hype
short
aligned with the message angle
```

Examples:

```text
Scaling XR without adding support overhead
Quick question on your headset rollout
Keeping headsets ready for class
Reducing downtime across your VR training fleet
Offloading XR deployment support
From XR pilot to reliable program
```

Avoid:

```text
URGENT
Guaranteed ROI
Revolutionize your XR
Disrupting immersive learning
```

## Personalization token map

Create:

```text
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_personalization-token-map.md
```

For each token, define:

```text
token
description
source field
fallback behavior
human review requirement
```

Required tokens:

```text
{{first_name}}
{{organization_name}}
{{organization_trigger}}
{{visible_XR_signal}}
{{message_angle}}
{{proof_point}}
{{resource_offer}}
```

Fallback rule:

```text
If a token cannot be sourced, remove the sentence instead of guessing.
```

## Copy risk review

Create:

```text
research/messaging/006-copy-risk-review.md
```

Check every sequence for:

```text
unsupported claims
over-personalization
sensitive healthcare implications
student/minor implications
fake urgency
unclear opt-out
missing sender identity
missing postal address placeholder
aggressive CTA
compliance ambiguity
```

## Human approval checklist

Create:

```text
research/messaging/006-human-approval-checklist.md
```

For every sequence, require:

```text
message segment reviewed
proof point verified
subject lines approved
CTA approved
compliance footer completed
unsubscribe language completed
sender identity confirmed
postal address confirmed
suppression process confirmed
human approver name/date
```

## Sequence output format

For each segment, write:

```text
## Segment: <segment_name>

### Target personas

### Message angle

### Subject line options

### Touch 1

### Touch 2

### Touch 3

### Touch 4 / close-the-loop

### Personalization tokens

### Proof-point guidance

### CTA guidance

### Risks and human review notes
```

## JSON output format

The JSON sequence file should be an array.

Each object should include:

```text
segment
target_personas
message_angle
subject_options
touches
personalization_tokens
proof_point_guidance
CTA_guidance
risk_notes
human_review_required
approved_for_sending
```

Set:

```text
approved_for_sending: false
```

for every sequence.

## Quality bar

A good messaging draft is:

```text
specific
operational
short
accurate
human-review-ready
compliance-aware
segment-matched
low-pressure
```

A bad messaging draft is:

```text
generic
hype-driven
long
unsupported
too aggressive
send-ready without review
missing opt-out placeholders
not tied to the outreach queue
```

## Stop conditions

Stop and mark blocked if:

```text
prioritized outreach queue is missing
message angles are missing
proof points are not verified
sender identity is unknown
unsubscribe process is unknown
postal address is unknown
suppression process is missing
```

Do not stop merely because sender infrastructure is incomplete.

Instead, draft copy and clearly mark:

```text
not approved for sending
human review required
sender/compliance setup incomplete
```

## Final response format

Return:

```text
1. Messaging draft summary
2. Input files reviewed
3. Segments drafted
4. Subject-line banks created
5. Personalization tokens created
6. Copy risks found
7. Human approval blockers
8. Files created
9. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
007-human-review-and-send-readiness.md
```

That prompt should check human approvals, sender infrastructure, suppression, compliance footer readiness, and whether any queue item can safely move toward a live sending system.
