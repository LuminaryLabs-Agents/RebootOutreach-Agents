# Intake

This folder is for raw lead data before enrichment, validation, scoring, or outreach.

## Structure

```text
intake/
  README.md
  raw/
    .gitkeep
```

## Raw lead data rules

- Put unprocessed lead exports in `intake/raw/`.
- Do not edit raw source files in place.
- Keep one source/export per file.
- Prefer timestamped filenames.
- Include source notes when possible.
- Do not commit secrets, API keys, passwords, private credentials, or sensitive personal data.

## Suggested raw file naming

```text
YYYY-MM-DD_source_segment_raw.csv
YYYY-MM-DD_source_segment_raw.json
YYYY-MM-DD_source_segment_raw.xlsx
```

## Suggested minimum raw columns

```text
source
source_url
organization_name
organization_domain
contact_name
contact_title
contact_email
linkedin_url
city
state
country
notes
collected_at
```

## Next stage

Raw intake data should later move through enrichment, validation, scoring, and outreach-readiness gates before any email is sent.
