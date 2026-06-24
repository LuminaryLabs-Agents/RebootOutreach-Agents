# Crawler Validation Loop

Use this workflow when validating Nexus Crawler behavior.

## Validation goals

A crawler batch is valid when it proves:

- The source registry can store approved URLs.
- The crawler only fetches public pages.
- The parser extracts usable content.
- The signal detector creates structured events.
- Duplicates are avoided.
- Scoring is deterministic enough to review.
- Output can be inspected through an API, dashboard, CSV, or log.

## Required checks

Run available project commands, such as:

```bash
npm test
npm run lint
npm run typecheck
npm run build
pytest
python -m pytest
```

Only run commands that exist in the target project.

## Manual validation checklist

- Add at least one FDA URL.
- Add at least one ACGME URL.
- Add at least one NIH grants URL.
- Add at least one hospital jobs URL.
- Run crawl against the seed batch.
- Confirm crawl logs exist.
- Confirm detected signals include source URL and evidence snippet.
- Confirm duplicate pages do not create duplicate signal events.
- Confirm bad URLs fail safely.
- Confirm CSV export works.

## Signal quality check

Each detected signal must have:

- Source URL
- Organization or source name
- Signal type
- Signal summary
- Evidence snippet
- Matched keywords or detector reason
- Confidence score
- Relevance score
- Detected timestamp
- Status

## Safety check

Reject implementation if it:

- Bypasses login
- Bypasses CAPTCHA
- Bypasses paywalls
- Extracts private personal data
- Runs without rate limits
- Cannot disable a source domain
- Stores raw pages without purpose or retention plan
