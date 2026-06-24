# Prompt 001: Reboot Imagine Research Goals

## Title

```text
Reboot Imagine Outreach Research Goals
```

## Target organization

```text
Reboot Imagine
https://www.rebootimagine.com/
```

## Mission

Research Reboot Imagine deeply enough to build a validated, prioritized, cold-email-ready lead pipeline.

The output should help future agents identify which organizations and contacts are worth collecting, validating, scoring, and preparing for outreach.

Do not send emails from this prompt.

Do not generate final outreach lists without validation gates.

Do not treat raw scraped data as outreach-ready.

## Primary research goals

1. Understand Reboot Imagine's offer, positioning, services, audience, language, and proof points.

2. Identify the most likely buyer personas and decision makers.

3. Define ideal customer profiles based on fit, need, urgency, budget, and relevance.

4. Build heuristic rules for finding high-fit leads.

5. Define source channels for collecting raw lead data.

6. Define validation gates from raw lead discovery through outreach readiness.

7. Define lead scoring and prioritization rules.

8. Define segmentation rules for email messaging.

9. Define trigger signals that make a lead timely.

10. Define deliverability, compliance, and human-review safeguards.

## Research inputs

Use these inputs first:

```text
Website: https://www.rebootimagine.com/
Repo intake folder: intake/raw/
```

Then use public-source research only.

Recommended source types:

```text
organization website
LinkedIn company pages
public staff pages
public event pages
school or nonprofit directories
grant announcements
news articles
podcasts/interviews
conference speaker pages
public IRS/nonprofit records where relevant
public procurement pages where relevant
```

Avoid private, guessed, purchased, or non-consensual data sources.

## Output files future agents should create later

```text
research/reboot-imagine-profile.md
research/icp-and-personas.md
research/lead-source-map.md
research/validation-gates.md
research/scoring-model.md
research/outreach-prioritization.md
research/email-segments.md
research/kpi-feedback-loop.md
```

## Lead discovery heuristics

Look for organizations that show one or more of these signals:

```text
mission-aligned education, youth, workforce, community, reentry, creative technology, digital inclusion, innovation, entrepreneurship, or social-impact work
recent program launch
recent grant or funding award
recent hiring for program, partnerships, community, education, innovation, or development roles
active workshops, cohorts, events, or public programming
visible need for storytelling, outreach, digital transformation, AI enablement, training, or strategic program support
small-to-mid organization with enough public activity to indicate budget or urgency
clear named decision makers
clear contact path
```

Reject or deprioritize organizations that show these signals:

```text
no public activity in the last 18 months
no clear fit with Reboot Imagine's mission or offer
no identifiable decision maker
only generic contact form and no staff context
highly regulated outreach risk without clear opt-in or business relevance
competitor or vendor mismatch
student-only or consumer-only audience when B2B/program partnership is required
```

## Contact persona targets

Prioritize contacts with program, partnership, innovation, education, workforce, or executive authority.

High-priority titles may include:

```text
Executive Director
Founder
CEO
COO
Chief Program Officer
Director of Programs
Director of Partnerships
Director of Innovation
Director of Education
Director of Workforce Development
Community Engagement Director
Development Director
Grant Program Manager
School District Administrator
Career and Technical Education Director
```

Lower priority unless context is strong:

```text
generic info inbox
junior staff without budget or program authority
press-only contacts
support-only contacts
student ambassadors
```

## Validation gates

Every lead should pass through these gates before outreach.

### Gate 1: Source capture

Required:

```text
organization_name
organization_domain
source_url
source_type
collected_at
collector_notes
```

Pass criteria:

```text
source is public
organization exists
source URL resolves
lead is not duplicated
```

### Gate 2: Organization fit

Required:

```text
mission fit
program fit
geographic fit if relevant
likely need
likely budget or partnership capacity
recent activity signal
```

Pass criteria:

```text
clear reason Reboot Imagine could help
at least one visible need or timing trigger
no obvious exclusion factor
```

### Gate 3: Contact fit

Required:

```text
contact_name
contact_title
contact_source_url
role_relevance
seniority_level
```

Pass criteria:

```text
person is currently associated with the organization
role is relevant to program, partnership, innovation, education, funding, or executive decisions
contact is not a protected/private individual outside business context
```

### Gate 4: Email validation

Required:

```text
email
email_source
email_validation_status
email_validation_method
```

Pass criteria:

```text
email is found from a public or consented source, or follows a verified organization pattern with manual review
email syntax is valid
email domain matches organization or accepted parent domain
email is not a known role-only inbox unless intentionally segmented
email is not invalid, disposable, or high-risk catch-all without review
```

### Gate 5: Compliance review

Required:

```text
country_or_region
legal_basis_or_business_relevance
unsubscribe_plan
sender_identity
suppression_list_checked
```

Pass criteria:

```text
business relevance is documented
message will include truthful identity
message will include opt-out path
suppression list checked
no sensitive targeting language
```

### Gate 6: Outreach readiness

Required:

```text
segment
priority_score
personalization_note
recommended_angle
proof_point_to_use
first_email_status
human_review_status
```

Pass criteria:

```text
lead has a clear segment
lead has a clear reason for outreach now
lead has a short, specific personalization note
lead has passed human review before sending
```

## Scoring model

Score each organization from 0 to 100.

Recommended weights:

```text
mission fit: 20
program need: 20
timing trigger: 15
contact authority: 15
budget or partnership capacity: 10
public proof available: 10
email confidence: 5
low compliance risk: 5
```

Priority bands:

```text
80-100: Priority A, send first after human approval
65-79: Priority B, enrich and queue after A leads
50-64: Priority C, nurture or research more
0-49: Hold or reject
```

## Outreach prioritization rules

Send first to leads with:

```text
Priority A score
recent trigger within 90 days
clear decision maker
validated email
strong personalization note
clear alignment to Reboot Imagine offer
low compliance and deliverability risk
```

Hold leads with:

```text
unclear decision maker
weak personalization
unverified email
no timing trigger
low mission fit
possible compliance concern
```

## Recommended segments

Use segments to keep messaging specific.

Suggested starting segments:

```text
education and school programs
workforce development organizations
nonprofits and community organizations
innovation and entrepreneurship programs
funders and grantmaking organizations
municipal or public-sector innovation teams
creative technology or digital inclusion programs
```

## Messaging-angle research goals

For each segment, identify:

```text
pain point
likely goal
proof point needed
best first sentence
relevant Reboot Imagine offer
low-pressure call to action
```

Avoid generic claims.

Avoid pretending to know private problems.

Prefer observable public facts.

## KPI goals

Track:

```text
raw leads collected
leads rejected by gate
leads enriched
validated emails
Priority A leads
send-ready leads
open rate
reply rate
positive reply rate
meeting-booked rate
bounce rate
unsubscribe rate
spam complaint rate
segment performance
source performance
```

## Stop conditions

Stop and mark blocked if:

```text
Reboot Imagine positioning cannot be confirmed from public sources
lead source requires paid/private/unauthorized access
email cannot be validated
compliance risk is unclear
sender identity or unsubscribe method is not ready
human review has not happened
```

## Expected final answer from an agent running this prompt

Return:

```text
1. Research summary
2. ICP and persona map
3. Lead source map
4. Validation gate checklist
5. Scoring model
6. Prioritized lead collection plan
7. Risks and blocked items
8. Files changed
9. Next recommended prompt
```
