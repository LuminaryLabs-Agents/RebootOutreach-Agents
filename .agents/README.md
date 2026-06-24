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
    007-human-review-and-send-readiness.md
    008-results-feedback-and-learning-loop.md
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
007-human-review-and-send-readiness.md = verify human approval, suppression, sender identity, compliance, and deliverability readiness
008-results-feedback-and-learning-loop.md = classify outcomes, update suppression/nurture queues, and choose the next loop-back prompt
```

## Loop closure

```text
008-results-feedback-and-learning-loop.md
```

closes the first Reboot Outreach loop by using real outcome data to recommend where the next cycle should restart.

Typical loop-back targets:

```text
001-seed-information-collector.md = improve search language
002-precision-lead-search.md = collect more leads using proven seeds
003-lead-validation-gates.md = adjust scoring and rejection rules
004-contact-research-and-email-validation.md = improve buyer/contact targeting
005-prioritized-outreach-queue.md = revise waves and prioritization
006-email-sequence-and-messaging-drafts.md = improve message copy
007-human-review-and-send-readiness.md = re-check blocked send-readiness items
```
