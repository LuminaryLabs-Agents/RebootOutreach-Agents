# Raw Contact Search Summary

Date: 2026-06-24

## Output file

```text
intake/raw/2026-06-24_reboot-imagine_raw_contacts.csv
```

## Scope

This was a bounded first-pass raw contact collection for Reboot Imagine.

The output focuses on public professional contacts connected to high-fit Reboot Imagine ICP categories:

```text
XR software vendors
medical simulation organizations
higher education XR programs
enterprise innovation / XR labs
location-based entertainment / immersive companies
```

## Reboot Imagine fit basis

Reboot Imagine publicly positions around:

```text
XR procurement
XR provisioning
MDM setup
custom kitting
RMA and repair
fleet management
technical support
software vendor services
enterprise / industrial / medical / education adopters
```

Primary source:

```text
https://www.rebootimagine.com/
```

## Source policy

Only public professional sources were used.

No private databases were used.

No purchased data was used.

No guessed personal emails were included.

## Email policy

The raw CSV intentionally leaves `email` blank for every contact.

Reason:

```text
The available quick-pass sources identified names/titles and organization relevance, but did not provide public official email evidence strong enough for outreach readiness.
```

Future agents should run:

```text
004-contact-research-and-email-validation.md
```

before adding any email data.

## Contact source examples used

```text
https://www.axios.com/2022/03/24/osso-vr-nets-66m-series-c
https://www.axios.com/2021/09/29/virtual-reality-training-walmart-nfl
https://en.wikipedia.org/wiki/Derek_Belch
https://en.wikipedia.org/wiki/Virti
https://en.wikipedia.org/wiki/VirtaMed
https://en.wikipedia.org/wiki/Amitai_Ziv
https://en.wikipedia.org/wiki/Virtual_Reality_and_Education_Laboratory
https://en.wikipedia.org/wiki/J_Dakota_Powell
https://en.wikipedia.org/wiki/Guy_Primus
```

## Counts

```text
raw contacts collected: 12
personal emails collected: 0
generic emails collected: 0
contacts requiring human review: 12
```

## Known limitations

- Several source records are public profiles or news articles rather than official organization staff pages.
- Some records are useful as ICP calibration contacts but need current-role verification.
- Some records are outside the default United States / Canada scope and should be held unless international outreach is approved.
- The CSV is raw intake, not outreach-ready.

## Recommended next action

Run the contact validation stage:

```text
.agents/prompts/004-contact-research-and-email-validation.md
```

Then verify:

```text
current title
current organization association
official source URL
public email source, if any
suppression status
business relevance
human review status
```
