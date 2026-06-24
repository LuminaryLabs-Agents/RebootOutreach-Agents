# Reboot Outreach Agents

Reboot Outreach Agents is the repo-local agent control center for the Reboot Outreach system.

It stores memory, plans, prompts, validation rules, crawl seed lists, and GitHub Actions for AI-assisted implementation work.

## Primary mission

Build and maintain the agent operating layer for Nexus Crawler and Reboot Outreach.

## Current product focus

The first product focus is Nexus Crawler.

Nexus Crawler is a public-web trigger detection engine. It crawls approved public sources, detects structured business signals, stores evidence, dedupes repeated findings, scores relevance, and exposes the resulting signal events through a reviewable workflow.

## Repo structure

```text
output.md
output-rules.md

.agent/
  pointer.md
  workflow.md
  output.md
  prompts/
    001-bootstrap-reboot-outreach.md
    002-nexus-crawler-mvp.md
    003-medical-source-seed-list.md
  workflows/
    implementation-loop.md
    crawler-validation-loop.md

docs/
  REBOOT_OUTREACH_MEMORY.md
  NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md
  NEXUS_CRAWLER_ACCEPTANCE.md
  MEDICAL_CRAWL_SEED_URLS.md

.github/workflows/
  reboot-outreach-output.yml
```

## Agent rule

Every agent run should:

1. Read `.agent/pointer.md`.
2. Read `.agent/workflow.md`.
3. Read the selected prompt.
4. Execute one bounded batch.
5. Update root `output.md` with the short status text.
6. Update `.agent/output.md` with internal run notes.
7. Update `docs/REBOOT_OUTREACH_MEMORY.md`.
8. Update `.agent/pointer.md` to the next best task.
9. Run validation.
10. Commit and push only after the repo state is coherent.

## Output workflow

The workflow at `.github/workflows/reboot-outreach-output.yml` follows the Lost Pages pattern adapted for this docs/agent repo:

```text
validate -> prepare-summary -> notify
```

Root `output.md` controls the short status text.

`output-rules.md` controls the style.

`.agent/output.md` is for longer internal notes.

Required GitHub secret:

```text
DISCORD_WEBHOOK_URL
```

Run options:

- Automatically on push to `main`
- Manually through `workflow_dispatch`
