# Implementation Loop

Use this workflow for bounded implementation work.

## Loop

```text
read pointer
read selected prompt
read memory
inspect target files
choose one bounded milestone
implement milestone
run validation
update memory
update output
update pointer if needed
commit and push
```

## Rules

- Do not expand scope mid-run.
- Do not turn crawler work into outbound automation unless adapter stubs are explicitly requested.
- Prefer small, reviewable diffs.
- Keep product rules in memory updated.
- Log every validation command.
- If validation fails, fix it or record the blocker.

## Required memory update format

```md
## YYYY-MM-DD - Short batch title

Goal:

Files changed:

Decisions made:

Validation:

Result:

Known issues:

Next action:
```

## Good milestone examples

- Add crawler source registry schema
- Add public page fetcher
- Add parser and page text extraction
- Add signal detector
- Add dedupe hash
- Add signal scoring
- Add CSV export
- Add dashboard signal review page
- Add webhook adapter stub
- Add tests

## Bad milestone examples

- Build the entire company
- Build crawler, CRM, email, enrichment, and sales dashboards at once
- Scrape private systems
- Skip tests
- Ignore memory updates
