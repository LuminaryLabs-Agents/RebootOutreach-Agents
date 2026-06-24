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
6. Read root `output-rules.md`.
7. Execute only one bounded batch.
8. Update root `output.md` with the short status text.
9. Update `.agent/output.md` with internal run notes.
10. Update `docs/REBOOT_OUTREACH_MEMORY.md`.
11. Update `.agent/pointer.md` only if the next task is clear.
12. Run validation.
13. Commit and push.

## Output rule

Root `output.md` is the short status source.

`.agent/output.md` is the internal run log.

Do not use generated memory dumps as the status message.

## Bounded batch rule

Do not attempt to complete the full product in one run.

A valid batch should be one of:

- Documentation bootstrap
- Output workflow cleanup
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
- Root `output.md` describes the latest change
- Docs match implementation state
- Validation has run or a clear validation blocker is logged
- The next action is explicit
