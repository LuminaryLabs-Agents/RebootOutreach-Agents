# Scoring Model

Date: 2026-06-24

## Organization scoring

```text
ICP fit: 30
visible XR signal: 20
trigger or deployment signal: 20
operational pain likelihood: 15
source quality: 10
geographic fit: 5
```

Priority bands:

```text
85-100 = validated_priority_A
70-84 = validated_priority_B
55-69 = validated_priority_C
below 55 = hold or reject
```

## Contact scoring

```text
role relevance: 35
seniority / authority: 20
organization priority inherited: 15
source quality: 10
email confidence: 10
business relevance / compliance safety: 10
```

Contact priority bands:

```text
85-100 = contact_priority_A
70-84 = contact_priority_B
55-69 = contact_priority_C
below 55 = hold_or_reject
```

## Email confidence scoring

```text
10 = official public email source
8 = credible conference/bio/procurement email
6 = public pattern confirmed and marked for review
4 = syntax-valid but unverified
2 = generic inbox only
0 = not collected, invalid, private source, or unverifiable
```

Current staged run result:

```text
email confidence for every contact = 0
reason = no official public email source collected
```

## Compliance readiness score

This staged run assigns no outreach-ready score because compliance infrastructure is incomplete.

Missing items:

```text
suppression file
sender identity
postal address
unsubscribe method
human approval log
SPF/DKIM/DMARC readiness record
```
