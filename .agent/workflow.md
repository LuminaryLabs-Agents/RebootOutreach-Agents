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
- What files should be packaged for review

## Required run order

Every run must follow this sequence:

1. Read `.agent/pointer.md`.
2. Read the target prompt listed in the pointer.
3. Read the workflow file listed in the pointer.
4. Read `docs/REBOOT_OUTREACH_MEMORY.md`.
5. Read `docs/NEXUS_CRAWLER_IMPLEMENTATION_PLAN.md`.
6. Read root `output-rules.md`.
7. If learning a new rule, read `.agent/workflows/learning-workflow.md`.
8. Execute only one bounded batch.
9. Update root `output.md` with the short status text.
10. If review files should be packaged, update `.agent/attachments/requested-files.txt`.
11. Update `.agent/output.md` with internal run notes.
12. Update `.agent/changelog.md` when the change teaches a future-run rule.
13. Update `docs/REBOOT_OUTREACH_MEMORY.md`.
14. Update `.agent/pointer.md` only if the next task is clear.
15. Run validation.
16. Commit and push.

## Output rule

Root `output.md` is the short status source.

`.agent/output.md` is the internal run log.

`.agent/attachments/requested-files.txt` lists repo-relative files to package into `requested-files.zip`.

Do not use generated memory dumps as the status message.

## Bounded batch rule

Do not attempt to complete the full product in one run.

A valid batch should be one of:

- Documentation bootstrap
- Output workflow cleanup
- File package workflow
- Learning workflow update
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
- Requested review files are listed in `.agent/attachments/requested-files.txt` when needed
- Docs match implementation state
- Validation has run or a clear validation blocker is logged
- The next action is explicit
