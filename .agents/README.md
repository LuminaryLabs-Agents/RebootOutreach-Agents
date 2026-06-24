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
    002-precision-lead-search.md
    003-lead-validation-gates.md
    004-contact-research-and-email-validation.md
    005-prioritized-outreach-queue.md
    006-email-sequence-and-messaging-drafts.md
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
002-precision-lead-search.md = raw organization lead collection from seed files
003-lead-validation-gates.md = validate, deduplicate, score, and prepare organizations for contact research
004-contact-research-and-email-validation.md = find relevant contacts, validate email confidence, and flag compliance risk
005-prioritized-outreach-queue.md = rank human-review-ready contacts, assign review waves, and map message angles
006-email-sequence-and-messaging-drafts.md = draft segment-specific messages for human review only
```

## Intended next prompts

```text
007-human-review-and-send-readiness.md
008-results-feedback-and-learning-loop.md
```
