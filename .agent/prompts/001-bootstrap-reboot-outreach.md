# Prompt 001: Bootstrap Reboot Outreach

## Title

Reboot Outreach Agent Repo Bootstrap

## Goal

Create the repo-local memory and workflow structure that future agents will use to implement Nexus Crawler and Reboot Outreach safely.

## Instructions

You are operating inside `LuminaryLabs-Agents/RebootOutreach-Agents`.

This repo is the agent control center for Reboot Outreach.

Create or verify the following files:

```text
README.md
.agent/pointer.md
.agent/workflow.md
.agent/output.md
.agent/prompts/001-bootstrap-reboot-outreach.md
.agent/prompts/002-nexus-crawler-mvp.md
.agent/prompts/003-medical-source-seed-list.md
.agent/workflows/implementation-loop.md
.agent/workflows/crawler-validation-loop.md
docs/REBOOT_OUTREACH_MEMORY.md
docs/NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md
docs/NEXUS_CRAWLER_ACCEPTANCE.md
docs/MEDICAL_CRAWL_SEED_URLS.md
.github/workflows/discord-summary.yml
```

## Required behavior

- Establish the repo as a memory-first agent operating layer.
- Make `docs/REBOOT_OUTREACH_MEMORY.md` the main source of truth.
- Make `.agent/pointer.md` indicate the next best prompt.
- Make `.agent/output.md` summarize the latest run.
- Add a Discord workflow that uses `DISCORD_WEBHOOK_URL` from GitHub secrets.

## Validation

Check that every expected file exists.

The repo is ready when a new agent can read `.agent/pointer.md` and know what to do next.

## Next prompt

After this bootstrap is complete, point to:

```text
.agent/prompts/002-nexus-crawler-mvp.md
```
