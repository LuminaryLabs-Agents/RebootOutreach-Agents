# Prompt 007: Reboot Imagine Human Review and Send Readiness

## Title

```text
Reboot Imagine Human Review and Send Readiness
```

## Mission

Review the prioritized outreach queue and drafted email sequences for human approval, compliance readiness, suppression safety, sender readiness, and deliverability readiness.

This prompt is a pre-send gate.

Do not send emails.

Do not upload leads into a sequencer.

Do not schedule emails.

Do not mark any item as send-ready unless every required human, compliance, suppression, and sender-readiness gate is complete.

The goal is to produce a clear readiness decision for every queue item:

```text
approved_for_manual_send_prep
blocked_until_fixed
hold_for_more_review
do_not_contact
```

## Required previous prompts

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
.agents/prompts/002-precision-lead-search.md
.agents/prompts/003-lead-validation-gates.md
.agents/prompts/004-contact-research-and-email-validation.md
.agents/prompts/005-prioritized-outreach-queue.md
.agents/prompts/006-email-sequence-and-messaging-drafts.md
```

Also review latest files from:

```text
processed/outreach/
drafts/email-sequences/
research/outreach/
research/messaging/
processed/contacts/
```

Expected input files:

```text
processed/outreach/YYYY-MM-DD_reboot-imagine_prioritized_outreach_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_hold_queue.csv
processed/outreach/YYYY-MM-DD_reboot-imagine_suppression_review_queue.csv
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_segment_sequences.md
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_segment_sequences.json
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_subject-line-bank.md
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_personalization-token-map.md
research/messaging/006-copy-risk-review.md
research/messaging/006-human-approval-checklist.md
```

If the email sequence drafts do not exist, stop and recommend running:

```text
006-email-sequence-and-messaging-drafts.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

No outreach item should move toward sending unless all of these are true:

```text
the organization is validated
the contact is role-relevant
the email source is acceptable
business relevance is documented
suppression has been checked
the message copy has human approval
sender identity is confirmed
opt-out method is confirmed
postal address is confirmed
SPF, DKIM, and DMARC readiness are confirmed or flagged
daily send limits are defined
the item has no unresolved compliance risk
```

This prompt checks readiness.

It does not perform sending.

## Primary goal

Create a final review package that answers:

```text
Which contacts are approved for manual send preparation?
Which contacts are blocked?
Why are they blocked?
Which copy is approved?
Which copy needs revision?
Which compliance or deliverability items are missing?
Which suppression or do-not-contact conflicts exist?
What must be fixed before anything can be sent?
```

## Required output files

Create:

```text
processed/send-readiness/YYYY-MM-DD_reboot-imagine_send_readiness_queue.csv
processed/send-readiness/YYYY-MM-DD_reboot-imagine_send_readiness_queue.json
processed/send-readiness/YYYY-MM-DD_reboot-imagine_blocked_before_send.csv
processed/send-readiness/YYYY-MM-DD_reboot-imagine_do_not_contact.csv
research/send-readiness/007-send-readiness-summary.md
research/send-readiness/007-human-approval-log.md
research/send-readiness/007-sender-infrastructure-check.md
research/send-readiness/007-compliance-and-suppression-check.md
research/send-readiness/007-copy-approval-log.md
```

Use the current date in filenames.

## Required send-readiness fields

Every reviewed queue item must include:

```text
send_readiness_id
reviewed_at
queue_id
lead_id
contact_id
organization_name
organization_domain
contact_name
contact_title
email
email_validation_status
email_confidence_score
message_segment
message_angle
recommended_wave
subject_line_selected
sequence_version
human_review_status
human_reviewer_name
human_review_date
organization_fit_approved
contact_fit_approved
email_source_approved
business_relevance_approved
suppression_checked
suppression_result
compliance_review_status
copy_review_status
sender_identity_status
postal_address_status
unsubscribe_method_status
SPF_status
DKIM_status
DMARC_status
daily_send_limit_status
sequencer_or_manual_send_status
final_send_readiness_status
blocked_reason
required_fix
review_notes
```

## Final send-readiness statuses

Use these statuses:

```text
approved_for_manual_send_prep
hold_for_human_review
hold_for_copy_revision
hold_for_email_validation
hold_for_suppression_check
hold_for_compliance_review
hold_for_sender_setup
hold_for_deliverability_setup
do_not_contact
blocked_until_fixed
```

Important:

```text
approved_for_manual_send_prep
```

does not mean the agent sent anything.

It only means the row passed the documented pre-send checks and may be handled by a human or approved outbound operator.

## Gate 1: Human review

Every row must have human approval before any send-readiness approval.

Pass if:

```text
human reviewer is named
review date is present
organization fit is approved
contact fit is approved
message angle is approved
copy version is approved
```

Fail if:

```text
human reviewer is missing
review date is missing
any key fit question is unresolved
review only says okay without checking gates
```

If this gate fails, set:

```text
hold_for_human_review
```

## Gate 2: Organization and contact approval

Pass if:

```text
organization is Priority A or Priority B
contact is Priority A or Priority B
contact role is relevant to XR operations, training, simulation, IT, implementation, or vendor support
business relevance is clear
```

Hold if:

```text
organization is Priority C
contact is only moderately relevant
business relevance is weak but possible
```

Fail if:

```text
organization was rejected
contact was rejected
role is unrelated
consumer-only or student-only context is present
```

## Gate 3: Email source approval

Pass if:

```text
email is publicly sourced from an official or credible public page
email domain matches organization
email syntax is valid
email source URL is preserved
```

Hold if:

```text
email is pattern-based
email is generic inbox only
email has catch-all risk
email has syntax-only validation
```

Fail if:

```text
email source is private, purchased, leaked, guessed-only, or unauthorized
email syntax is invalid
email domain mismatches the organization
email source cannot be reviewed
```

## Gate 4: Suppression and do-not-contact check

Check all available suppression files.

Possible locations:

```text
suppression/
compliance/suppression/
processed/suppression/
processed/send-readiness/
```

Pass if:

```text
email checked against suppression list
domain checked against suppression list
organization checked against suppression list
contact checked against suppression list when available
no conflict exists
```

Hold if:

```text
suppression file is missing
suppression process is unclear
suppression check was not logged
```

Fail if:

```text
email appears on suppression list
domain appears on suppression list
contact has opted out
organization has do-not-contact status
prior complaint or negative reply exists
```

If fail, write to:

```text
processed/send-readiness/YYYY-MM-DD_reboot-imagine_do_not_contact.csv
```

## Gate 5: Compliance review

Pass if:

```text
business relevance is documented
message is truthful and non-deceptive
subject line is non-deceptive
sender identity is clear
postal address is available
opt-out method is available
jurisdiction risk is checked
sensitive context is reviewed
```

Hold if:

```text
jurisdiction is unclear
healthcare or education context needs extra review
message could imply private knowledge
postal address is missing
opt-out path is missing
```

Fail if:

```text
message relies on sensitive personal data
message implies private knowledge that is not publicly sourced
sender identity is unclear
opt-out is unavailable
do-not-contact conflict exists
```

## Gate 6: Copy approval

Review every selected email sequence.

Pass if:

```text
copy is segment-specific
copy uses approved proof points only
copy uses approved personalization tokens only
copy includes compliance placeholders
copy has no unsupported claims
copy has no fake urgency
copy has no sensitive over-personalization
copy has human approval
```

Hold if:

```text
subject line needs revision
CTA is too aggressive
personalization token is missing
proof point is not mapped clearly
copy is too generic
```

Fail if:

```text
copy invents claims
copy uses unverified metrics
copy includes fake familiarity
copy omits opt-out placeholder
copy implies private/sensitive knowledge
```

## Gate 7: Sender identity readiness

Pass if all are known:

```text
sender_name
sender_title
sender_company
sender_email
sender_domain
reply-to inbox
postal_address
unsubscribe method
```

Hold if any are missing.

Do not approve any row until sender identity is complete.

## Gate 8: Deliverability readiness

Check and record:

```text
SPF
DKIM
DMARC
domain age or warmup status
reply inbox access
bounce handling
unsubscribe handling
daily send limit
mailbox provider rules
sequencer/tool if any
```

Pass if:

```text
SPF status is confirmed
DKIM status is confirmed
DMARC status is confirmed
unsubscribe method is confirmed
daily send limits are conservative
bounce handling is defined
```

Hold if:

```text
any authentication item is unknown
daily send limit is undefined
unsubscribe process is undefined
bounce handling is undefined
```

This gate does not configure sender infrastructure.

It only records whether infrastructure is ready.

## Gate 9: Selected subject-line approval

Subject line must be:

```text
short
truthful
non-deceptive
not clickbait
not fake-forwarded
not fake-replied
not urgent unless urgency is real
aligned with the email body
```

Reject subject lines containing:

```text
URGENT
Re:
Fwd:
Guaranteed ROI
Final notice
You are losing money
```

unless there is a documented and truthful reason.

## Gate 10: Personalization token approval

Every personalization token must be source-backed.

Pass if:

```text
token value comes from approved source fields
source URL is preserved
token does not imply private knowledge
fallback exists if token is missing
```

Hold if:

```text
token value is missing
token source is unclear
fallback sentence needs removal
```

Fail if:

```text
token is guessed
token is sensitive
token implies private operational pain
```

## Blocked-before-send file

Create:

```text
processed/send-readiness/YYYY-MM-DD_reboot-imagine_blocked_before_send.csv
```

Include:

```text
send_readiness_id
queue_id
lead_id
contact_id
organization_name
contact_name
email
blocked_reason
required_fix
gate_failed
review_notes
```

Do not silently drop blocked records.

## Do-not-contact file

Create:

```text
processed/send-readiness/YYYY-MM-DD_reboot-imagine_do_not_contact.csv
```

Include:

```text
send_readiness_id
queue_id
lead_id
contact_id
organization_name
contact_name
email
do_not_contact_reason
source_or_evidence
date_added
review_notes
```

## Sender infrastructure check

Create:

```text
research/send-readiness/007-sender-infrastructure-check.md
```

Include:

```text
sender domain
SPF status
DKIM status
DMARC status
reply inbox status
unsubscribe method
postal address
daily send limits
sequencer/tool status
bounce handling
complaint handling
missing items
recommended fixes
```

## Compliance and suppression check

Create:

```text
research/send-readiness/007-compliance-and-suppression-check.md
```

Include:

```text
suppression files checked
number of records checked
suppression conflicts
jurisdiction risks
healthcare/education sensitive-context flags
opt-out readiness
postal address readiness
sender identity readiness
blocked items
recommended fixes
```

## Copy approval log

Create:

```text
research/send-readiness/007-copy-approval-log.md
```

Include:

```text
sequence version
segment
subject line selected
copy status
proof point status
CTA status
personalization token status
human reviewer
approval date
required edits
```

## Human approval log

Create:

```text
research/send-readiness/007-human-approval-log.md
```

Include:

```text
reviewer_name
review_date
items_reviewed
items_approved_for_manual_send_prep
items_blocked
items_marked_do_not_contact
notes
```

## Send-readiness summary

Create:

```text
research/send-readiness/007-send-readiness-summary.md
```

Include:

```text
date
input files reviewed
total queue items reviewed
approved_for_manual_send_prep count
hold_for_human_review count
hold_for_copy_revision count
hold_for_email_validation count
hold_for_suppression_check count
hold_for_compliance_review count
hold_for_sender_setup count
hold_for_deliverability_setup count
do_not_contact count
blocked_until_fixed count
top blockers
sender infrastructure status
compliance status
recommended next prompt
```

## Quality bar

A good send-readiness review is:

```text
strict
gate-based
conservative
source-backed
human-review-centered
suppression-aware
deliverability-aware
clear about blockers
does not send anything
```

A bad send-readiness review is:

```text
approves rows without human review
ignores suppression
ignores sender setup
ignores unsubscribe requirements
treats draft copy as approved
moves weak contacts forward
assumes compliance is complete
sends or schedules emails
```

## Stop conditions

Stop and mark blocked if:

```text
prioritized outreach queue is missing
email sequence drafts are missing
human approval records are missing
suppression process is missing and cannot be checked
sender identity is missing
unsubscribe method is missing
postal address is missing
SPF, DKIM, or DMARC status is unknown
copy approval cannot be verified
```

Do not send.

Do not schedule.

Do not upload to a sending tool.

If infrastructure is incomplete, produce the blocked files and required-fix report.

## Final response format

Return:

```text
1. Send-readiness summary
2. Input files reviewed
3. Approved-for-manual-send-prep count
4. Hold counts by reason
5. Do-not-contact count
6. Blocked count
7. Sender infrastructure status
8. Compliance and suppression status
9. Copy approval status
10. Files created
11. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
008-results-feedback-and-learning-loop.md
```

That prompt should only be used after a human-approved outbound process has produced results.

It should analyze replies, bounces, unsubscribes, objections, positive responses, and conversion quality so future lead sourcing and messaging can improve.
