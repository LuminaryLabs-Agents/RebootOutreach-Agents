# Reboot Outreach Agent Workflow

This file defines the default behavior for all agent runs in this repo.

## Operating model

Reboot Outreach uses repo-local memory.

The repo should remember:

- What the system is building
- What prompt should run next
- What workflow should guide execution
- What files changed
- What validations ran
- What remains blocked
- What the next agent should do

## Required run order

Every run must follow this sequence:

1. Read `.agent/pointer.md`.
2. Read the target prompt listed in the pointer.
3. Read the workflow file listed in the pointer.
4. Read `docs/REBOOT_OUTREACH_MEMORY.md`.
5. Read `docs/NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md`.
6. Execute only one bounded batch.
7. Update `.agent/output.md`.
8. Update `docs/REBOOT_OUTREACH_MEMORY.md`.
9. Update `.agent/pointer.md` only if the next task is clear.
10. Run validation.
11. Commit and push.

## Bounded batch rule

Do not attempt to complete the full product in one run.

A valid batch should be one of:

- Documentation bootstrap
- Crawler source registry
- Fetcher and parser
- Signal detector
- Dedupe and scoring
- Database schema
- API layer
- Admin review UI
- CSV export
- Webhook adapter
- Tests and validation cleanup

## Memory update rule

After each meaningful change, update the memory with:

- Date
- Goal
- Files changed
- Decisions made
- Validation commands run
- Result
- Known issues
- Next action

## Safety rule

For crawler work:

- Public pages only
- No login bypass
- No CAPTCHA bypass
- No paywall bypass
- No private data extraction
- Rate limits required
- Source enable/disable required
- Evidence snippets required for detected signals

## Completion rule

A batch is not complete until:

- Files are coherent
- Docs match implementation state
- Validation has run or a clear validation blocker is logged
- The next action is explicit
