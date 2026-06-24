# Stage 003 Validation Run Summary

Date: 2026-06-24

## Input files reviewed

```text
intake/raw/2026-06-24_reboot-imagine_precision_org_leads_raw.csv
intake/raw/2026-06-24_reboot-imagine_precision_org_leads_raw.json
```

## Output files

```text
processed/validated/2026-06-24_reboot-imagine_validated_org_leads.csv
processed/validated/2026-06-24_reboot-imagine_validated_org_leads.json
processed/validated/2026-06-24_reboot-imagine_rejected_org_leads.csv
research/validation/003-field-completeness-report.md
research/validation/003-duplicate-resolution-log.md
```

## Counts

```text
total raw leads: 12
validated_priority_A: 2
validated_priority_B: 7
validated_priority_C: 2
hold_needs_more_research: 2
rejected: 0
duplicates: 0
```

## Top ICP clusters

```text
xr_software_vendor
medical_simulation
higher_education_xr
```

## Key risks

```text
partner-logo sources need deeper organization-specific verification
public-profile sources may be historical/stale
healthcare and education contexts require human review
no email validation is complete
suppression and sender readiness are not available
```

## Recommended next prompt

```text
004-contact-research-and-email-validation.md
```
