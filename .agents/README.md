# Reboot Outreach Agents

This folder stores repo-local agent operating context.

The goal is to make each future agent run self-directed, bounded, and easy to resume.

## Structure

```text
.agents/
  README.md
  prompts/
    001-research-goals.md
```

## Prompt rules

- Each prompt should be a bounded unit of work.
- Each prompt should state the goal, inputs, expected outputs, validation gates, and stop conditions.
- Prompts should prefer evidence, citations, and source URLs over assumptions.
- Prompts should never authorize sending outreach directly without validation and human approval.

## Current first prompt

```text
.agents/prompts/001-research-goals.md
```

This prompt defines the research goals for Reboot Imagine lead sourcing, validation, prioritization, and cold-email readiness.
