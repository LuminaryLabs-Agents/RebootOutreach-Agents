# Prompt 008: Reboot Imagine Results Feedback and Learning Loop

## Title

```text
Reboot Imagine Results Feedback and Learning Loop
```

## Mission

Analyze results from a human-approved Reboot Imagine outbound cycle and convert those results into improvements for the next research, sourcing, validation, prioritization, and messaging cycle.

This prompt is a learning loop.

Do not send emails.

Do not reply to contacts.

Do not upload leads into a sequencer.

Do not change live campaign settings.

Do not override suppression or do-not-contact rules.

The goal is to learn from real outcomes and update the next agent run with better sourcing, scoring, segmentation, message angles, and validation rules.

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
.agents/prompts/007-human-review-and-send-readiness.md
```

Also review latest available files from:

```text
processed/send-readiness/
processed/outreach/
drafts/email-sequences/
research/send-readiness/
research/messaging/
research/outreach/
```

Expected prior files:

```text
processed/send-readiness/YYYY-MM-DD_reboot-imagine_send_readiness_queue.csv
processed/send-readiness/YYYY-MM-DD_reboot-imagine_blocked_before_send.csv
processed/send-readiness/YYYY-MM-DD_reboot-imagine_do_not_contact.csv
research/send-readiness/007-send-readiness-summary.md
drafts/email-sequences/YYYY-MM-DD_reboot-imagine_segment_sequences.md
processed/outreach/YYYY-MM-DD_reboot-imagine_prioritized_outreach_queue.csv
```

## Required results input

This prompt requires a manually exported result file from a human-approved outbound process.

Expected locations:

```text
results/raw/
results/imports/
processed/results/
```

Expected result file examples:

```text
YYYY-MM-DD_reboot-imagine_outbound_results_raw.csv
YYYY-MM-DD_reboot-imagine_outbound_results_raw.json
YYYY-MM-DD_reboot-imagine_reply_export_raw.csv
YYYY-MM-DD_reboot-imagine_bounce_unsubscribe_export_raw.csv
```

If no results file exists, stop and create a missing-results note.

Do not infer results from memory.

Do not invent outcomes.

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine should improve outbound by learning which combinations of these variables produce qualified interest:

```text
ICP cluster
source type
trigger signal
buyer persona
message angle
proof point
CTA
subject direction
email validation status
segment
outreach wave
```

The learning goal is not higher volume.

The learning goal is better qualified replies, fewer bounces, fewer opt-outs, clearer segmentation, and better sales-accepted opportunities.

## Primary goal

Create a feedback package that answers:

```text
Which sources produced the best leads?
Which ICPs produced the best replies?
Which buyer personas responded?
Which message angles worked?
Which message angles failed?
Which triggers predicted positive replies?
Which contacts should be suppressed?
Which leads should be recycled or nurtured?
Which seed queries should be improved?
Which scoring rules should change?
Which prompt should run next?
```

## Required output files

Create:

```text
processed/results/YYYY-MM-DD_reboot-imagine_classified_results.csv
processed/results/YYYY-MM-DD_reboot-imagine_classified_results.json
processed/results/YYYY-MM-DD_reboot-imagine_suppression_updates.csv
processed/results/YYYY-MM-DD_reboot-imagine_nurture_or_recycle_queue.csv
research/results/008-results-summary.md
research/results/008-reply-classification-report.md
research/results/008-source-and-segment-performance.md
research/results/008-message-angle-performance.md
research/results/008-objection-and-risk-log.md
research/results/008-learning-recommendations.md
research/results/008-next-cycle-plan.md
```

Use the current date in filenames.

## Input result fields

Read whatever fields are available from the results export.

Expected useful fields:

```text
queue_id
send_readiness_id
lead_id
contact_id
organization_name
organization_domain
contact_name
contact_title
email
ICP_cluster
message_segment
message_angle
recommended_wave
subject_line_used
sequence_version
touch_number
sent_at
delivered_status
open_status
click_status
reply_status
reply_text
reply_date
bounce_status
bounce_type
unsubscribe_status
spam_complaint_status
meeting_booked_status
human_notes
```

If some fields are missing, do not guess.

Add missing-field notes to:

```text
research/results/008-results-summary.md
```

## New classified result fields

Add these fields to every result row:

```text
result_id
classified_at
delivery_classification
reply_classification
reply_sentiment
intent_level
sales_relevance
objection_category
risk_category
recommended_action
suppression_action
nurture_or_recycle_status
learning_notes
next_cycle_signal
```

## Delivery classification values

Use these values:

```text
delivered
soft_bounce
hard_bounce
blocked
not_sent
unknown_delivery
```

## Reply classification values

Use these values:

```text
positive_interest
meeting_request
referral_to_colleague
curious_but_early
timing_issue
not_a_fit
vendor_already_selected
handled_in_house
budget_objection
wrong_contact
unsubscribe_request
negative_reply
spam_complaint
out_of_office
auto_reply
no_reply
unknown_reply
```

## Reply sentiment values

Use:

```text
positive
neutral
negative
automated
unknown
```

## Intent level values

Use:

```text
high_intent
medium_intent
low_intent
no_intent
negative_intent
unknown
```

## Sales relevance values

Use:

```text
sales_accepted_candidate
nurture_candidate
recycle_later
disqualified
suppression_required
manual_review_required
```

## Recommended action values

Use:

```text
route_to_human_sales_review
create_referral_followup_task
add_to_nurture_queue
recycle_after_timing_window
suppress_contact
suppress_domain_or_org
fix_data_quality_issue
revise_message_angle
revise_source_query
hold_for_manual_review
no_action
```

Do not perform the action.

Only classify and recommend.

## Suppression rules

Create suppression updates for:

```text
hard bounce
unsubscribe request
do-not-contact request
spam complaint
explicit negative reply requesting no further contact
invalid email
domain-level do-not-contact signal
```

Write these to:

```text
processed/results/YYYY-MM-DD_reboot-imagine_suppression_updates.csv
```

Include:

```text
email
domain
organization_name
contact_name
suppression_reason
source_result_id
date_added
notes
```

Do not remove suppression entries.

Do not override suppression entries.

## Reply classification rules

### Positive interest

Classify as `positive_interest` if the reply shows:

```text
interest in learning more
request for details
request for resource
request for pricing
question about service fit
clear problem acknowledgement
```

Recommended action:

```text
route_to_human_sales_review
```

### Meeting request

Classify as `meeting_request` if the reply asks to meet or agrees to a call.

Recommended action:

```text
route_to_human_sales_review
```

Do not schedule the meeting from this prompt.

### Referral to colleague

Classify as `referral_to_colleague` if the reply names or suggests another owner.

Recommended action:

```text
create_referral_followup_task
```

Do not email the referred person from this prompt.

### Curious but early

Classify as `curious_but_early` if the reply is positive but not urgent.

Recommended action:

```text
add_to_nurture_queue
```

### Timing issue

Classify as `timing_issue` if the reply indicates a future date, quarter, semester, budget cycle, deployment window, or event.

Recommended action:

```text
recycle_after_timing_window
```

Capture the stated timing window if available.

### Wrong contact

Classify as `wrong_contact` if the person says they are not the right owner.

Recommended action:

```text
fix_data_quality_issue
```

If they provide a referral, also mark:

```text
create_referral_followup_task
```

### Not a fit

Classify as `not_a_fit` if the organization or contact clearly does not match Reboot Imagine's offer.

Recommended action:

```text
disqualified
```

### Unsubscribe / do not contact

Classify as `unsubscribe_request` or `negative_reply` if the person requests no further contact.

Recommended action:

```text
suppress_contact
```

## Bounce rules

Hard bounces:

```text
mark suppression_action = suppress_contact
mark recommended_action = suppress_contact
add to suppression updates
```

Soft bounces:

```text
mark recommended_action = hold_for_manual_review
do not suppress unless repeated or known invalid
```

Unknown bounce:

```text
mark recommended_action = hold_for_manual_review
```

## Spam complaint rules

If spam complaint exists:

```text
mark suppression_action = suppress_contact
mark recommended_action = suppress_contact
flag risk_category = spam_complaint
add to suppression updates
include in risk log
```

Also recommend reviewing:

```text
source quality
message angle
email source
business relevance note
sender infrastructure
send volume
segment targeting
```

## Nurture or recycle queue

Create:

```text
processed/results/YYYY-MM-DD_reboot-imagine_nurture_or_recycle_queue.csv
```

Include:

```text
result_id
lead_id
contact_id
organization_name
contact_name
reply_classification
recommended_recycle_date
recommended_nurture_angle
timing_note
next_action_owner
review_notes
```

Use recycle dates only when the reply states a time window.

Do not invent dates.

If timing is vague, use:

```text
manual_review_needed
```

## Source and segment performance

Create:

```text
research/results/008-source-and-segment-performance.md
```

Analyze:

```text
ICP clusters contacted
source types used
trigger types used
message segments used
reply rates by segment
positive replies by segment
negative replies by segment
bounces by source type
unsubscribe or complaint patterns
best source patterns
worst source patterns
```

If sample size is small, state that results are directional only.

Do not overfit from small samples.

## Message angle performance

Create:

```text
research/results/008-message-angle-performance.md
```

Analyze:

```text
message_angle
subject_line_used
CTA
proof_point
reply_classification
positive reply rate
negative reply rate
unsubscribe rate
bounce rate
notes
```

Identify:

```text
angles to keep
angles to revise
angles to stop
angles needing more data
```

## Objection and risk log

Create:

```text
research/results/008-objection-and-risk-log.md
```

Track objections such as:

```text
already handled internally
already have vendor
budget unavailable
not using XR
not scaling yet
wrong department
security or compliance concern
support not a priority
timing issue
irrelevant outreach
negative sentiment
```

For each objection, include:

```text
example paraphrase
segment
message angle
recommended learning
```

Do not quote private replies extensively.

Paraphrase unless exact short quote is necessary and permitted by available data rules.

## Learning recommendations

Create:

```text
research/results/008-learning-recommendations.md
```

Include recommended changes to:

```text
ICP definitions
seed keywords
source map
negative filters
raw lead scoring
validation scoring
contact persona targeting
email validation rules
outreach priority scoring
message angles
subject lines
CTAs
proof point usage
human review gates
sender-readiness gates
```

Each recommendation should be tied to evidence from the result file.

Do not make broad changes based on one weak signal.

## Next-cycle plan

Create:

```text
research/results/008-next-cycle-plan.md
```

The next-cycle plan should choose where to loop back.

Allowed loop-back recommendations:

```text
run 001-seed-information-collector.md again
run 002-precision-lead-search.md again with revised queries
run 003-lead-validation-gates.md again with revised scoring
run 004-contact-research-and-email-validation.md again for better personas
run 005-prioritized-outreach-queue.md again with revised waves
run 006-email-sequence-and-messaging-drafts.md again with revised copy
run 007-human-review-and-send-readiness.md again after fixes
pause outreach until compliance or sender issues are fixed
```

For each recommendation, include:

```text
reason
evidence
files to update
expected improvement
risk
```

## KPI summary

Track:

```text
total contacts reviewed
sent count if provided
delivered count
hard bounce count
soft bounce count
unsubscribe count
spam complaint count
reply count
positive reply count
meeting request count
referral count
curious but early count
timing issue count
negative reply count
sales accepted candidate count
```

Calculate rates only when denominators are available.

Use:

```text
unknown
```

when data is missing.

## Data quality review

Check whether outcome tracking was possible.

Flag missing fields such as:

```text
queue_id
lead_id
contact_id
message_angle
segment
subject line
delivery status
reply status
bounce status
unsubscribe status
```

If tracking IDs are missing, recommend fixing output files from earlier prompts.

## Quality bar

A good feedback run is:

```text
evidence-based
conservative
honest about sample size
clear about suppressions
useful for improving the next cycle
specific about what to change
strict about not sending or replying
```

A bad feedback run is:

```text
overfits from tiny samples
ignores negative signals
fails to update suppression
only celebrates opens
does not classify replies
changes every prompt without evidence
forgets compliance and deliverability lessons
```

## Stop conditions

Stop and mark blocked if:

```text
results export is missing
results export lacks contact or queue identifiers
suppression requests cannot be identified
reply text cannot be safely classified
delivery/bounce fields are missing and cannot be inferred
```

If results are missing, create:

```text
research/results/008-missing-results-note.md
```

Include:

```text
which files were expected
which files were missing
what export is needed
recommended source fields
```

## Final response format

Return:

```text
1. Results feedback summary
2. Input files reviewed
3. Total results classified
4. Positive replies
5. Meeting requests
6. Referrals
7. Unsubscribes
8. Bounces
9. Suppression updates created
10. Best-performing segments
11. Weakest-performing segments
12. Message angles to keep
13. Message angles to revise
14. Recommended loop-back prompt
15. Files created
```

## Loop closure

This is the final prompt in the first Reboot Outreach loop.

After this prompt, start the next cycle by following the recommendation in:

```text
research/results/008-next-cycle-plan.md
```

The default next cycle should begin at:

```text
001-seed-information-collector.md
```

if search language needs improvement.

The default next cycle should begin at:

```text
002-precision-lead-search.md
```

if the search language is good but more leads are needed.

The default next cycle should begin at:

```text
006-email-sequence-and-messaging-drafts.md
```

if lead quality is good but message performance is weak.
