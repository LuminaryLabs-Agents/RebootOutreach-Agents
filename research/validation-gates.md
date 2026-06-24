# Validation Gates

Date: 2026-06-24

## Gate 1: Public source validity

Pass if:

```text
source is public
source URL resolves
source can be reviewed later
organization exists
source connects to XR, VR, AR, simulation, training, provisioning, support, or immersive deployment
```

Fail if:

```text
source is private
source requires unauthorized access
source is guessed
source is consumer-only noise
source cannot be reviewed later
```

## Gate 2: Organization fit

Pass if:

```text
organization maps to a target ICP
there is an XR / VR / AR / simulation / training / vendor-services signal
Reboot Imagine's provisioning, fleet management, support, or vendor-service offer is plausibly relevant
```

Hold if:

```text
source is stale
geography is outside default US/Canada scope
operational pain is plausible but not visible
```

Fail if:

```text
no XR signal
student-only project
consumer-only gaming context
no business or institutional buyer
```

## Gate 3: Contact fit

Pass if:

```text
contact is professionally associated with organization
role is executive, program, training, simulation, IT, implementation, customer success, or support relevant
source URL supports the role or association
```

Hold if:

```text
role appears historical
source is not official
current association needs verification
```

Fail if:

```text
contact is too junior
press-only contact
personal context only
association cannot be verified
```

## Gate 4: Email confidence

Pass only if:

```text
email is public and source-backed
email syntax is valid
email domain aligns with organization
source URL is preserved
```

Hold if:

```text
email is not collected
email is pattern-based
email is generic inbox only
email source is not official
```

Fail if:

```text
email is guessed
email comes from private/purchased/leaked source
email domain mismatches organization
email is invalid
```

## Gate 5: Compliance and suppression

Pass only if:

```text
business relevance documented
suppression checked
sender identity available
postal address available
opt-out path available
jurisdiction reviewed
human review completed
```

In this staged run, this gate is not complete because:

```text
no suppression file found
no sender identity record found
no postal address record found
no human approval record found
```

## Gate 6: Outreach readiness

No contact in this run is outreach-ready.

Reason:

```text
emails are not source-validated
suppression is not checked
human review is incomplete
sender readiness is unknown
```
