# Reboot Outreach Agents

This folder stores repo-local agent operating context.

The goal is to make each future agent run self-directed, bounded, and easy to resume.

## Structure

```text
.agents/
  README.md
  prompts/
    000-research-goals.md
    001-seed-information-collector.md
```

## Prompt rules

- Each prompt should be a bounded unit of work.
- Each prompt should state the goal, inputs, expected outputs, validation gates, and stop conditions.
- Prompts should prefer evidence, citations, and source URLs over assumptions.
- Prompts should never authorize sending outreach directly without validation and human approval.

## Current prompt sequence

```text
000-research-goals.md = mission charter and validation foundation
001-seed-information-collector.md = first operational prompt for precision-search seeds
```

## Intended next prompts

```text
002-precision-lead-search.md
003-lead-validation-gates.md
004-prioritized-outreach-queue.md
```
