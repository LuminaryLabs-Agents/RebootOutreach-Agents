# Reboot Outreach Agents

Reboot Outreach Agents is the repo-local agent control center for the Reboot Outreach system.

It stores the memory, plans, prompts, validation rules, crawl seed lists, and GitHub Actions needed to coordinate AI-assisted implementation work.

## Primary mission

Build and maintain the agent operating layer for Nexus Crawler and Reboot Outreach.

The repo is intended to answer these questions for future Codex or ChatGPT runs:

- What is the product goal?
- What should the next agent run do?
- What files define the current memory?
- What crawl sources are approved for testing?
- What counts as a usable implementation?
- What validations must pass before work is considered complete?
- How should progress be summarized to Discord?

## Current product focus

The first product focus is Nexus Crawler.

Nexus Crawler is a public-web trigger detection engine. It crawls approved public sources, detects structured business signals, stores evidence, dedupes repeated findings, scores relevance, and exposes the resulting signal events through a reviewable workflow.

It is not a generic scraper.

It is not a cold-email sender.

It is not a full CRM automation stack yet.

It is the ingestion and signal-detection layer for Reboot Outreach.

## Repo structure

```text
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
  discord-summary.yml
```

## Agent rule

Every agent run should:

1. Read `.agent/pointer.md`.
2. Read `.agent/workflow.md`.
3. Read the selected prompt.
4. Execute one bounded batch.
5. Update `.agent/output.md`.
6. Update `docs/REBOOT_OUTREACH_MEMORY.md`.
7. Update `.agent/pointer.md` to the next best task.
8. Run validation.
9. Commit and push only after the repo state is coherent.

## Discord summary workflow

The workflow at `.github/workflows/discord-summary.yml` posts a compact project summary to Discord.

Required GitHub secret:

```text
DISCORD_WEBHOOK_URL
```

Run options:

- Automatically on push to `main`
- Manually through `workflow_dispatch`

## Safety posture

Crawler-related work must follow these rules:

- Crawl public pages only.
- Do not bypass login, paywalls, CAPTCHAs, or private systems.
- Use rate limits.
- Respect robots.txt where applicable.
- Store only necessary business signal data.
- Keep crawl logs.
- Allow source domains to be disabled.
