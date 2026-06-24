# Learning Workflow

Status: active

## Purpose

Use this workflow when a repo change teaches the agent system a new operating rule.

A learning change is not only a file edit.

It must also update the repo memory so future runs inherit the intent.

## Learning loop

1. Read `.agent/pointer.md`.
2. Read `.agent/workflow.md`.
3. Read `docs/REBOOT_OUTREACH_MEMORY.md`.
4. Identify the new rule being learned.
5. Update the files that enforce the rule.
6. Update `.agent/changelog.md` with the learning intent.
7. Update `.agent/output.md` with internal notes.
8. Update root `output.md` with the short status text.
9. Update the pointer if the next best task changes.
10. Run the closest validation.

## Attachment learning rule

When a run creates requested files that should be shared with the status message, list those paths in:

```text
.agent/attachments/requested-files.txt
```

The output workflow packages listed files into:

```text
requested-files.zip
```

That zip is sent with the short status text when a webhook secret is configured.

## Changelog rule

Every learning change must include:

- Date
- Intent
- Files changed
- Validation path
- Next use

## Current learned rule

Root `output.md` controls the short status text.

`.agent/attachments/requested-files.txt` controls which requested files are packaged into a zip.
