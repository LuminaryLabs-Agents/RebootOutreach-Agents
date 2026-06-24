# Prompt 001: Reboot Imagine Seed Information Collector

## Title

```text
Reboot Imagine Precision Search Seed Collector
```

## Mission

Gather the seed information needed to start a precise lead search for Reboot Imagine.

Do not gather full lead lists yet.

Do not enrich contacts yet.

Do not prepare outreach yet.

This prompt only creates the search foundation.

The goal is to identify the exact language, signals, source types, organization examples, exclusion rules, and search queries that future agents should use to collect high-fit leads.

## Context

Reboot Imagine is an XR managed service provider.

The likely strongest market is not generic XR curiosity.

The strongest market is organizations that already believe in XR but need help making XR operational at scale.

Key offer themes:

```text
XR procurement
XR provisioning
headset fleet setup
MDM enrollment
Meta for Work
ArborXR
ManageXR
device repair and RMA
remote support
white-label support for XR software vendors
pilot-to-scale support
XR downtime reduction
enterprise XR support
education XR support
medical XR support
industrial XR training support
```

## Research goal

Create a precision-search seed pack that future agents can use to find high-fit organizations and contacts.

The seed pack should answer:

```text
Who should we search for?
What language do they use publicly?
Where do they appear online?
What signals show they are ready now?
What terms should we include?
What terms should we exclude?
What examples should calibrate the search?
```

## Required output files

Create these files:

```text
research/seeds/001-search-seed-map.md
research/seeds/002-keyword-bank.md
research/seeds/003-source-map.md
research/seeds/004-example-targets.md
research/seeds/005-negative-filters.md
research/seeds/006-precision-search-queries.md
```

## Step 1: Confirm Reboot Imagine positioning

Review public sources for Reboot Imagine.

Start with:

```text
https://www.rebootimagine.com/
```

Capture:

```text
core offer
target sectors
named partners
named customers
service categories
proof points
geographic limits
compliance claims
language Reboot Imagine uses repeatedly
```

Do not over-infer.

Only include claims that can be tied to public evidence.

## Step 2: Build ICP seed clusters

Create seed clusters for the highest-fit lead categories.

Start with these clusters:

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

For each cluster, capture:

```text
why this cluster fits
likely pain
likely buyer titles
common public source types
keywords they use
trigger signals
disqualification signals
example organizations to calibrate search
```

## Step 3: Build buyer-title seed bank

Collect buyer-title patterns.

Prioritize titles with authority over XR programs, training operations, IT operations, innovation, simulation, or customer implementation.

Include title variants such as:

```text
Director of Simulation
Simulation Center Director
Director of Immersive Learning
Director of Academic Technology
Director of Innovation
Clinical Innovation Lead
Digital Health Program Manager
Director of Learning and Development
Head of Training
Director of Workforce Development
Director of Operational Excellence
IT Operations Manager
Endpoint Manager
AV/IT Manager
VP Customer Success
Head of Implementations
VP Product
Founder
CEO
```

For each title, mark:

```text
primary buyer
technical influencer
program champion
vendor-side buyer
low-priority contact
```

## Step 4: Build keyword bank

Create keyword groups.

### Core XR operations terms

```text
XR deployment
VR deployment
headset deployment
VR fleet
XR fleet
device provisioning
headset provisioning
MDM enrollment
XR support
VR support
immersive learning support
simulation lab support
Meta Quest deployment
Meta for Work
Meta Quest for Business
ArborXR
ManageXR
kiosk mode
device management
remote app deployment
headset repair
RMA
```

### Pain terms

```text
pilot to scale
scaling XR
VR downtime
headset downtime
device readiness
classroom headset issues
training fleet support
implementation burden
support tickets
firmware updates
Wi-Fi issues
casting issues
device setup
multi-site rollout
```

### Vertical terms

```text
immersive learning
medical simulation
clinical simulation
VR training
AR training
XR training
enterprise training
workforce training
safety training
technical training
simulation center
innovation lab
digital health
spatial computing
```

### Vendor-side terms

```text
XR software vendor
VR training platform
immersive training platform
simulation software
enterprise VR software
VR content provider
XR implementation partner
customer onboarding
white-label support
deployment partner
```

## Step 5: Build trigger-signal bank

Find signals that suggest urgency.

Prioritize triggers from the last 180 days.

Strong triggers:

```text
new immersive learning lab
new simulation center
new VR training program
new workforce training grant
new XR partnership
new Meta Quest deployment
new ArborXR or ManageXR mention
new innovation program
new digital health pilot
new safety training initiative
new enterprise training rollout
XR-related job posting
conference talk about immersive learning or XR training
grant award for simulation or training technology
public procurement for VR/AR/XR hardware
```

Weak triggers:

```text
generic innovation language
old XR blog post
student project only
one-off demo
consumer VR event
inactive program page
```

## Step 6: Build public source map

List the best places to search for each cluster.

Include:

```text
organization websites
university simulation center pages
medical school simulation lab pages
hospital innovation pages
workforce board program pages
grant award announcements
press releases
conference speaker pages
LinkedIn company pages
job postings
public procurement portals
ArborXR ecosystem mentions
ManageXR ecosystem mentions
Meta for Work references
XR vendor partner pages
```

For each source type, record:

```text
what it can reveal
how reliable it is
what fields it can provide
what search terms work best there
risk of stale data
```

## Step 7: Build example target list

Collect a small calibration set.

Do not create a final lead list.

Create 5 to 10 example organizations per ICP cluster.

Each example should include:

```text
organization_name
organization_url
cluster
why it looks relevant
visible trigger or signal
source_url
confidence level
```

Use examples to calibrate search quality.

Do not include emails in this prompt.

## Step 8: Build negative filters

Create exclusion terms and disqualification rules.

Exclude or deprioritize:

```text
consumer VR gaming only
student-only projects
inactive XR pages
news older than 18 months with no recent activity
no clear organization buyer
no B2B or programmatic relevance
crypto/metaverse hype with no operational deployment
headset product reviews
game studios unless they sell B2B XR deployment software
generic AR filters or consumer apps
adult entertainment
military targeting unless explicitly approved
sensitive health outreach without clear business context
```

Create negative search terms such as:

```text
-gaming
-gameplay
-review
-Reddit
-Steam
-Oculus store
-Beat Saber
-metaverse token
-NFT
-consumer app
```

Only use negative terms when they improve precision.

Do not accidentally filter out valid enterprise XR sources.

## Step 9: Build precision search queries

Create ready-to-run search query templates.

Group them by ICP.

Each query should include:

```text
purpose
query
expected result type
what fields to capture
how to validate result
```

Example query formats:

```text
"immersive learning lab" "Meta Quest" "university"
"medical simulation center" "VR training" "Meta Quest"
"VR training" "ArborXR" "enterprise"
"XR deployment" "ManageXR" "training"
"simulation center" "virtual reality" "director"
"workforce training" "virtual reality" "grant"
"VR training platform" "customer success" "deployment"
"Meta Quest for Business" "training" "case study"
"XR software vendor" "white label support"
```

Also create LinkedIn-style search strings for manual use:

```text
site:linkedin.com/company "XR training" "enterprise"
site:linkedin.com/in "Director of Simulation" "virtual reality"
site:linkedin.com/in "immersive learning" "university"
site:linkedin.com/in "VP Customer Success" "VR training"
```

## Step 10: Define seed quality gates

Every seed item must pass these gates.

### Gate A: Public evidence

Pass if:

```text
source is public
source URL is captured
claim is visible from the source
```

Fail if:

```text
claim is guessed
source is private
source requires unauthorized access
```

### Gate B: ICP relevance

Pass if:

```text
seed clearly helps find one of the target ICPs
```

Fail if:

```text
seed is generic XR noise
seed is mostly consumer entertainment
seed does not connect to Reboot Imagine's operational offer
```

### Gate C: Search usefulness

Pass if:

```text
seed can improve search queries
seed can improve filtering
seed can improve scoring
seed can identify source channels
```

Fail if:

```text
seed is interesting but not useful for lead discovery
```

### Gate D: Recency

Pass if:

```text
source is current or still clearly relevant
```

Flag if:

```text
source is older than 18 months
```

Fail if:

```text
old source is the only evidence and no current activity exists
```

## Final response format

Return:

```text
1. Seed summary
2. Best ICP clusters for first search
3. Keyword bank summary
4. Trigger bank summary
5. Source map summary
6. Negative filters
7. Top 25 precision search queries
8. Example target calibration set
9. Files created
10. Recommended next prompt
```

## Stop conditions

Stop and mark blocked if:

```text
Reboot Imagine positioning cannot be verified
the source pool is too thin to build useful search seeds
queries are returning mostly consumer XR noise
the research starts collecting personal contact data before seed gates are complete
```

## Next recommended prompt

After this prompt is complete, the next prompt should be:

```text
002-precision-lead-search.md
```

That next prompt should use the seed files to gather raw organization leads into:

```text
intake/raw/
```
