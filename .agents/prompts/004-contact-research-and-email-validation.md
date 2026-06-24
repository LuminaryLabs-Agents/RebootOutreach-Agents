# Prompt 004: Reboot Imagine Contact Research and Email Validation

## Title

```text
Reboot Imagine Contact Research and Email Validation
```

## Mission

Identify relevant decision-maker contacts for validated Reboot Imagine organization leads.

Validate contact fit, email confidence, business relevance, and compliance risk.

Do not send emails.

Do not create outreach campaigns.

Do not mark any lead as send-ready without human review.

Do not guess personal emails without validation.

Do not use private, purchased, leaked, or unauthorized data.

The goal is to turn validated organization leads into a contact-research file that can be reviewed, scored, and prioritized for outreach.

## Required previous prompts

Before running this prompt, review:

```text
.agents/prompts/000-research-goals.md
.agents/prompts/001-seed-information-collector.md
.agents/prompts/002-precision-lead-search.md
.agents/prompts/003-lead-validation-gates.md
```

Also review the latest validated organization files from:

```text
processed/validated/
```

Expected files:

```text
YYYY-MM-DD_reboot-imagine_validated_org_leads.csv
YYYY-MM-DD_reboot-imagine_validated_org_leads.json
YYYY-MM-DD_reboot-imagine_rejected_org_leads.csv
```

If validated organization files do not exist, stop and recommend running:

```text
003-lead-validation-gates.md
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Working thesis

Reboot Imagine should contact people who own XR deployment risk, headset operations, training operations, simulation programs, IT support, customer implementation, or vendor-side customer success.

Do not look for generic contacts first.

Do not default to info@ addresses unless no better business contact exists.

Prioritize contacts whose role connects directly to:

```text
XR deployment
VR headset fleet operations
simulation center operations
immersive learning programs
medical or clinical training
enterprise training
industrial training
IT operations
endpoint management
innovation programs
customer implementation
XR software vendor customer success
```

## Primary goal

For each validated Priority A and Priority B organization, identify the best 1 to 3 contacts for future human-reviewed outreach.

For complex enterprise, university, hospital, or vendor accounts, identify up to 5 contacts only when each contact has a clear role reason.

Do not over-collect.

Quality is more important than volume.

## Required output files

Create:

```text
processed/contacts/YYYY-MM-DD_reboot-imagine_contact_research.csv
processed/contacts/YYYY-MM-DD_reboot-imagine_contact_research.json
processed/contacts/YYYY-MM-DD_reboot-imagine_email_validation_queue.csv
processed/contacts/YYYY-MM-DD_reboot-imagine_rejected_contacts.csv
research/contact-research/004-contact-run-summary.md
research/contact-research/004-contact-source-log.md
research/contact-research/004-compliance-risk-log.md
```

Use the current date in filenames.

## Input lead priority order

Process leads in this order:

```text
validated_priority_A
validated_priority_B
validated_priority_C only if time remains or the organization is strategically important
```

Skip rejected organization leads.

Hold organization leads marked:

```text
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

unless the validation summary explicitly says manual review is needed.

## Contact persona priority

Prioritize contacts in this order.

### Education and university XR programs

```text
Director of Simulation
Simulation Center Director
Director of Immersive Learning
Director of Academic Technology
Director of Innovation
Director of Educational Technology
XR Lab Director
AV/IT Manager
Endpoint Manager
Dean or Associate Dean for Innovation
```

### Healthcare and medical simulation

```text
Director of Simulation
Clinical Simulation Director
Clinical Innovation Lead
Digital Health Program Manager
Director of Medical Education
Simulation Operations Manager
Biomedical IT Leader
IT Operations Manager
```

### Enterprise and industrial training

```text
Director of Learning and Development
Head of Training
Director of Operational Excellence
Safety Training Director
Workforce Development Director
Field Enablement Leader
IT Operations Manager
Endpoint Manager
```

### XR software vendors

```text
VP Customer Success
Head of Implementations
VP Product
Director of Customer Operations
Implementation Manager
Founder
CEO
COO
Partnerships Lead
```

### Location-based entertainment and activations

```text
Venue Operations Director
Technical Director
Experience Producer
General Manager
Owner
Support Operations Manager
```

## Contact role classification

Classify each contact as one of:

```text
economic_buyer
technical_buyer
program_champion
vendor_side_buyer
implementation_owner
support_owner
influencer
low_priority_contact
```

Do not collect low-priority contacts unless no better contact exists.

## Required contact fields

Every contact row must include:

```text
contact_id
lead_id
organization_name
organization_domain
organization_url
organization_priority_band
ICP_cluster
contact_name
contact_title
contact_department
contact_role_classification
contact_seniority_level
contact_source_url
contact_source_type
contact_source_date
contact_current_association_status
role_relevance_reason
role_relevance_score
seniority_score
source_quality_score
email
email_source_url
email_source_type
email_validation_status
email_validation_method
email_domain_match_status
email_confidence_score
catch_all_or_role_account_flag
business_relevance_note
jurisdiction_or_region
compliance_risk_status
suppression_check_status
human_review_required
recommended_next_action
review_notes
```

## Optional contact fields

Include if available from public sources:

```text
LinkedIn_profile_url
speaker_profile_url
staff_directory_url
bio_url
press_release_url
conference_url
publications_url
generic_contact_page_url
assistant_or_admin_contact
role_start_date
```

Do not include personal social media unless directly professional and public.

Do not include private home addresses.

Do not include personal phone numbers.

## Public source rules

Use public sources only.

Preferred contact sources:

```text
official organization staff page
official leadership page
official simulation center page
official department page
official press release
official conference speaker page
official author bio
official partner page
official procurement contact page
LinkedIn public profile snippet
company about page
```

Lower-confidence sources:

```text
third-party directories
old conference pages
unverified scraped people databases
AI-generated pages
generic SEO lead lists
```

Reject or hold contacts when the only source is weak.

## Email collection rules

Emails may be included only if one of these is true:

```text
email is publicly listed on an official organization page
email is listed on a credible conference, speaker, or publication page
email is listed in a public procurement document
email is a role account intentionally used by the organization
email pattern is confirmed from multiple public organization sources and marked for human review
```

Do not include emails from:

```text
leaked databases
private datasets
personal social profiles
non-public sources
purchased lead lists
guess-only pattern generation
```

Do not treat a guessed email as validated.

## Email validation status values

Use:

```text
validated_public_source
validated_public_pattern_with_review
valid_syntax_unverified
role_account_public
generic_org_inbox
catch_all_risk
invalid_syntax
domain_mismatch
unverified_hold
rejected_private_or_unauthorized_source
```

## Email validation method values

Use:

```text
official_page_public_email
conference_or_bio_public_email
procurement_public_email
public_pattern_crosscheck
manual_review_needed
syntax_only
not_validated
```

## Contact scoring model

Score each contact from 0 to 100.

```text
role relevance: 35
seniority / authority: 20
organization priority inherited: 15
source quality: 10
email confidence: 10
business relevance / compliance safety: 10
```

Priority bands:

```text
85-100 = contact_priority_A
70-84 = contact_priority_B
55-69 = contact_priority_C
below 55 = hold_or_reject
```

## Role relevance scoring

High score:

```text
contact directly owns XR, simulation, training, IT operations, implementation, customer success, or support
```

Medium score:

```text
contact is adjacent to the program or department
```

Low score:

```text
contact is generic leadership with no clear link
contact is junior
contact is press-only
contact is unrelated to the operational pain
```

## Email confidence scoring

Score email confidence from 0 to 10.

```text
10 = public official page email
8 = credible public conference/bio/procurement email
6 = public organization pattern confirmed with review required
4 = syntax-valid but unverified
2 = generic inbox only
0 = invalid, domain mismatch, private source, or unverifiable
```

## Compliance gate

Every contact must pass a business-relevance check before being advanced.

Pass if:

```text
contact is in a professional role
organization is B2B, institutional, public-sector, education, healthcare, enterprise, or vendor-side
Reboot Imagine's offer is plausibly relevant
source is public
future message can clearly explain why the outreach is relevant
```

Hold or reject if:

```text
contact appears personal rather than professional
student/minor context is involved
healthcare context is sensitive and business relevance is unclear
jurisdiction risk is unresolved
email source is unauthorized
suppression status is unknown
```

## Suppression check

Check whether the repo has a suppression or do-not-contact file.

Possible locations:

```text
suppression/
compliance/suppression/
processed/suppression/
```

If no suppression file exists, create a note in:

```text
research/contact-research/004-compliance-risk-log.md
```

Do not mark leads as outreach-ready until a suppression process exists.

Suppression fields to check when available:

```text
email
domain
organization_name
contact_name
reason
date_added
```

## Human review requirements

Set `human_review_required = true` if:

```text
healthcare or clinical context
education context involving students
role relevance is ambiguous
email pattern is inferred rather than publicly listed
generic inbox is the only email
jurisdiction is outside United States or Canada
organization is high value but contact source is weak
compliance risk is unclear
suppression file is missing
```

Human review must happen before any outreach sequence.

## Contact validation gates

### Gate 1: Organization eligibility

Pass if:

```text
organization is validated Priority A or Priority B
organization has not been rejected
organization has enough context for contact research
```

Fail if:

```text
organization was rejected
organization is duplicate
organization lacks source support
```

### Gate 2: Contact association

Pass if:

```text
contact is publicly associated with the organization
contact title or page indicates current or recent relevance
source URL supports association
```

Fail if:

```text
contact is no longer associated
association is unclear
source is stale and unsupported
```

### Gate 3: Role fit

Pass if:

```text
contact role maps to a buyer, champion, support owner, implementation owner, or influencer
```

Fail if:

```text
contact is unrelated
contact is too junior
contact is press-only or support-only with no buyer relevance
```

### Gate 4: Email source

Pass if:

```text
email is public, credible, syntax-valid, and domain-aligned
```

Hold if:

```text
email is pattern-based and needs manual review
email is generic inbox only
email is syntax-valid but unverified
```

Fail if:

```text
email is private-source only
email is invalid
email domain mismatches the organization
email source cannot be reviewed
```

### Gate 5: Compliance readiness

Pass if:

```text
business relevance is clear
suppression status is checked or flagged
human review status is set
future message can include clear opt-out
```

Fail if:

```text
business relevance is unclear
suppression conflict exists
source is unauthorized
sensitive context is unresolved
```

## Rejected contacts file

Create:

```text
processed/contacts/YYYY-MM-DD_reboot-imagine_rejected_contacts.csv
```

Include:

```text
contact_id
lead_id
organization_name
contact_name
contact_title
source_url
rejection_reason
rejection_notes
```

Do not silently discard rejected contacts.

## Email validation queue

Create:

```text
processed/contacts/YYYY-MM-DD_reboot-imagine_email_validation_queue.csv
```

Include contacts that need manual validation before outreach:

```text
contact_id
lead_id
organization_name
contact_name
contact_title
email
email_validation_status
email_validation_method
reason_manual_review_needed
source_url
review_notes
```

## Contact source log

Create:

```text
research/contact-research/004-contact-source-log.md
```

Include:

```text
source_url
organization_name
contact_name
source_type
what_was_found
confidence
notes
```

## Compliance risk log

Create:

```text
research/contact-research/004-compliance-risk-log.md
```

Include:

```text
organization_name
contact_name
risk_type
risk_reason
recommended_action
human_review_required
```

## Contact run summary

Create:

```text
research/contact-research/004-contact-run-summary.md
```

Include:

```text
date
input files reviewed
total organizations reviewed
Priority A organizations processed
Priority B organizations processed
contacts found
contacts rejected
contacts needing manual email validation
contacts with public validated emails
contacts requiring human review
missing suppression process note
recommended next prompt
```

## Quality bar

A good contact-research run is:

```text
role-relevant
source-backed
email-conservative
compliance-aware
deduplicated
clear about uncertainty
ready for human review
```

A bad contact-research run is:

```text
full of generic contacts
uses guessed emails as if validated
pulls from private or purchased sources
ignores suppression
targets junior or irrelevant people
marks contacts as send-ready too early
```

## Stop conditions

Stop and mark blocked if:

```text
validated organization files are missing
most organizations lack enough context for contact research
contact sources are mostly weak or private
emails cannot be source-verified
suppression process is missing and cannot be flagged
compliance risk cannot be evaluated
```

## Final response format

Return:

```text
1. Contact research summary
2. Input files reviewed
3. Organizations processed
4. Contacts found
5. Contacts rejected
6. Contacts needing manual validation
7. Contacts with public validated emails
8. Contacts requiring human review
9. Compliance risks
10. Files created
11. Recommended next prompt
```

## Next recommended prompt

After this prompt, run:

```text
005-prioritized-outreach-queue.md
```

That prompt should build the human-reviewed outreach queue, assign priority order, map message angles, and prepare—but not send—the first email sequence.
