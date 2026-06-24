# Prompt 005: Reboot Imagine Prioritized Outreach Queue

## Title

```text
Reboot Imagine Prioritized Outreach Queue
```

## Mission

Build a human-review-ready outreach queue from validated organizations and researched contacts.

This prompt ranks who should be contacted first, why they should be contacted, what message angle should be used, and what proof point should support the outreach.

Do not send emails.

Do not create live campaigns.

Do not upload leads into a sequencer.

Do not mark any contact as fully send-ready without human review.

The goal is to produce a clean, prioritized queue that a human can review before campaign drafting and sending.

## Required previous prompts

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
.agents/prompts/002-precision-lead-search.md
.agents/prompts/003-lead-validation-gates.md
.agents/prompts/004-contact-research-and-email-validation.md
```

Also review the latest files from:

```text
processed/validated/
processed/contacts/
research/contact-research/
```

Expected input files:

```text
processed/validated/YYYY-MM-DD_reboot-imagine_validated_org_leads.csv
processed/contacts/YYYY-MM-DD_reboot-imagine_contact_research.csv
processed/contacts/YYYY-MM-DD_reboot-imagine_email_validation_queue.csv
processed/contacts/YYYY-MM-DD_reboot-imagine_rejected_contacts.csv
research/contact-research/004-contact-run-summary.md
research/contact-research/004-compliance-risk-log.md
```

If validated contact files do not exist, stop and recommend running:

```text
004-contact-research-and-email-validation.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine should prioritize contacts where all of the following are true:

```text
organization has visible XR activity
organization likely has operational XR support pain
contact has role relevance
email confidence is acceptable
business relevance is clear
compliance risk is low or flagged for review
there is a specific reason to contact them now
```

The strongest message is not generic XR innovation.

The strongest message is:

```text
XR programs do not fail because of vision.
They fail because provisioning, support, repair, fleet operations, and scale are under-designed.
```

## Primary goal

Create a prioritized outreach queue that answers:

```text
Who should be contacted first?
Why are they high priority?
Which message angle fits them?
Which proof point should be used?
Which leads need human review before sending?
Which leads should be held, suppressed, or revalidated?
```

## Required output files

Create:

```text
processed/outreach/YYYY-MM-DD_reboot-imagine_prioritized_outreach_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_prioritized_outreach_queue.json
processed/outreach/YYYY-MM-DD_reboot-imagine_hold_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_suppression_review_queue.csv
research/outreach/005-outreach-queue-summary.md
research/outreach/005-prioritization-rationale.md
research/outreach/005-message-angle-map.md
research/outreach/005-human-review-checklist.md
```

Use the current date in filenames.

## Input contact priority order

Process contacts in this order:

```text
contact_priority_A
contact_priority_B
contact_priority_C only if organization priority is high or strategic
```

Do not process contacts with statuses such as:

```text
rejected_private_or_unauthorized_source
invalid_syntax
domain_mismatch
rejected_contact
suppression_conflict
unresolved_compliance_risk
```

Hold contacts with:

```text
valid_syntax_unverified
catch_all_risk
generic_org_inbox
validated_public_pattern_with_review
```

unless human review explicitly clears them.

## Required queue fields

Every outreach queue row must include:

```text
queue_id
created_at
lead_id
contact_id
organization_name
organization_domain
organization_url
ICP_cluster
organization_priority_band
contact_name
contact_title
contact_role_classification
contact_priority_band
email
email_validation_status
email_confidence_score
business_relevance_note
compliance_risk_status
suppression_check_status
human_review_required
human_review_status
trigger_signal
trigger_date
trigger_recency_bucket
visible_XR_signal
technology_signal
operational_pain_hypothesis
message_segment
message_angle
recommended_subject_direction
recommended_first_line_basis
recommended_proof_point
recommended_CTA
outreach_priority_score
outreach_priority_band
recommended_wave
recommended_next_action
do_not_send_reason
review_notes
```

## Outreach eligibility rules

A contact can enter the main outreach queue only if:

```text
organization is validated Priority A or Priority B
contact is Priority A or Priority B
email is publicly validated or manually reviewable
business relevance is documented
suppression status is checked or explicitly flagged
human review status is set
there is a clear message angle
there is a clear reason for outreach now
```

A contact must go to the hold queue if:

```text
email is syntax-only or unverified
email source needs manual review
suppression file is missing
compliance risk needs review
message angle is unclear
trigger is weak or stale
contact role is only moderately relevant
```

A contact must go to the suppression review queue if:

```text
suppression conflict exists
opt-out or do-not-contact signal exists
email source appears unauthorized
business relevance is unclear
jurisdiction risk is unresolved
```

## Prioritization scoring model

Score each contact from 0 to 100.

```text
organization ICP fit: 20
organization trigger strength: 15
operational pain likelihood: 15
contact role relevance: 20
email confidence: 10
message specificity: 10
compliance safety: 5
source quality: 5
```

Priority bands:

```text
85-100 = outreach_priority_A
70-84 = outreach_priority_B
55-69 = outreach_priority_C
below 55 = hold
```

## Recommended waves

Assign each approved queue item to one wave.

```text
Wave 1 = highest-confidence, strongest trigger, best role fit
Wave 2 = strong fit, weaker trigger or minor validation issue
Wave 3 = good fit, needs more personalization or review
Hold = not ready for outreach
Suppression Review = do not contact until resolved
```

Wave 1 requirements:

```text
outreach_priority_A
validated email or reviewed public pattern
clear trigger
clear operational pain hypothesis
role-relevant contact
low compliance risk
human review completed or explicitly required before send
```

Wave 2 requirements:

```text
outreach_priority_A or outreach_priority_B
good fit
some personalization available
minor missing field or weaker trigger
```

Wave 3 requirements:

```text
outreach_priority_B or outreach_priority_C
plausible fit
needs more evidence or better personalization before sending
```

## Message segments

Assign exactly one primary segment.

Allowed values:

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
other_manual_review
```

## Message angles

Assign one primary message angle.

Allowed values:

```text
pilot_to_scale
downtime_reduction
fleet_provisioning
headset_support_burden
MDM_and_device_management
simulation_lab_readiness
training_rollout_support
vendor_support_relief
white_label_deployment_support
repair_RMA_and_lifecycle
compliance_and_operational_control
```

## Message angle rules

Use `pilot_to_scale` when:

```text
lead has a pilot, lab, grant, new program, or expansion signal
```

Use `downtime_reduction` when:

```text
lead appears to operate training, classroom, simulation, event, or multi-site headset usage
```

Use `fleet_provisioning` when:

```text
lead shows device rollout, Meta Quest, headset fleet, procurement, or onboarding signal
```

Use `MDM_and_device_management` when:

```text
lead mentions ArborXR, ManageXR, Meta for Work, kiosk mode, remote deployment, app management, or endpoint control
```

Use `vendor_support_relief` when:

```text
lead is an XR software vendor, training platform, or immersive software provider
```

Use `white_label_deployment_support` when:

```text
vendor-side lead likely wants to preserve customer relationship while outsourcing deployment or support
```

Use `simulation_lab_readiness` when:

```text
lead is a medical school, academic simulation center, hospital sim center, or training lab
```

## Recommended CTA types

Assign one CTA type.

Allowed values:

```text
send_checklist
offer_5_point_ops_review
ask_current_support_model
ask_if_scaling_beyond_pilot
ask_who_owns_xr_support
offer_vendor_support_outline
offer_sim_lab_readiness_review
soft_permission_to_send_resource
```

Default CTA:

```text
soft_permission_to_send_resource
```

Avoid aggressive meeting asks unless the lead is Wave 1 and has a strong trigger.

## Proof point mapping

Choose one proof direction for each row.

Allowed values:

```text
Meta_for_Work_reseller_status
ArborXR_or_ManageXR_alignment
REK0_deployment_story
XR_native_MSP_positioning
24_7_support_tier
provisioning_and_RMA_services
white_label_vendor_support
custom_kitting_and_shipping
```

Do not invent unverified proof.

Use proof only if it maps to the lead's segment and message angle.

## Human review checklist

Create:

```text
research/outreach/005-human-review-checklist.md
```

For each Wave 1 and Wave 2 item, require review of:

```text
organization fit
contact role fit
email source
suppression status
business relevance
jurisdiction risk
personalization note
message angle
proof point
CTA
do-not-contact conflicts
```

No contact may be moved into a live send system until human review is marked complete.

## Deliverability guardrails

Do not send emails from this prompt.

Still classify deliverability readiness.

Check whether the repo or notes define:

```text
sender domain
SPF
DKIM
DMARC
unsubscribe process
physical mailing address
sender identity
suppression list
daily mailbox limits
sequencer/tool
```

If missing, flag in the queue summary.

Recommended conservative default if no sender infrastructure exists:

```text
do not send
build queue only
complete sender authentication and suppression process first
```

## Queue status values

Use these statuses:

```text
queue_wave_1_ready_for_human_review
queue_wave_2_ready_for_human_review
queue_wave_3_needs_more_personalization
hold_email_validation_needed
hold_compliance_review_needed
hold_suppression_process_missing
hold_weak_trigger
hold_low_role_fit
suppression_review
do_not_contact
```

## Hold queue rules

Write held contacts to:

```text
processed/outreach/YYYY-MM-DD_reboot-imagine_hold_queue.csv
```

Include:

```text
queue_id
lead_id
contact_id
organization_name
contact_name
contact_title
hold_reason
required_fix
review_notes
```

## Suppression review queue rules

Write suppression-risk contacts to:

```text
processed/outreach/YYYY-MM-DD_reboot-imagine_suppression_review_queue.csv
```

Include:

```text
queue_id
lead_id
contact_id
organization_name
contact_name
email
risk_reason
recommended_action
review_notes
```

## Message angle map

Create:

```text
research/outreach/005-message-angle-map.md
```

Group by segment.

For each segment, include:

```text
segment
primary pain
best message angle
recommended proof point
recommended CTA
example first-line basis
what to avoid
```

Do not write full email copy in this prompt.

That belongs in:

```text
006-email-sequence-and-messaging-drafts.md
```

## Prioritization rationale

Create:

```text
research/outreach/005-prioritization-rationale.md
```

Include:

```text
why Wave 1 leads were selected
why Wave 2 leads were selected
why leads were held
top triggers found
top message angles
major risks
manual review requirements
```

## Outreach queue summary

Create:

```text
research/outreach/005-outreach-queue-summary.md
```

Include:

```text
date
input files reviewed
total contacts reviewed
Wave 1 count
Wave 2 count
Wave 3 count
hold count
suppression review count
top ICP clusters
top message angles
missing deliverability infrastructure
human review blockers
recommended next prompt
```

## Quality bar

A good queue is:

```text
small enough for human review
highly relevant
source-backed
role-specific
trigger-aware
message-angle-ready
compliance-aware
not send-authorized
```

A bad queue is:

```text
too large
generic
full of weak contacts
missing source URLs
missing suppression status
message angles are vague
assumes sending is allowed
```

## Stop conditions

Stop and mark blocked if:

```text
contact research file is missing
email validation fields are missing
suppression process is missing and cannot be flagged
most contacts lack role relevance
most contacts lack public-source support
deliverability infrastructure is unknown and queue cannot be safely classified
```

Do not stop merely because sender infrastructure is missing.

Instead, build the queue and mark all entries as requiring sender-readiness review.

## Final response format

Return:

```text
1. Outreach queue summary
2. Input files reviewed
3. Wave 1 count
4. Wave 2 count
5. Wave 3 count
6. Hold count
7. Suppression review count
8. Top message angles
9. Missing sender or compliance infrastructure
10. Files created
11. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
006-email-sequence-and-messaging-drafts.md
```

That prompt should draft segment-specific email sequences for human review, using the prioritized outreach queue, but still must not send emails.
