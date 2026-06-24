# Reboot Outreach Agent Changelog

## 2026-06-24

Intent:

Future runs should record review file paths in `.agent/attachments/requested-files.txt`.

The output workflow makes a zip from those paths.

Files:

- `.agent/workflows/learning-workflow.md`
- `.agent/attachments/requested-files.txt`
- `data/test-output/xr-companies.csv`
- `.github/workflows/reboot-outreach-output.yml`
- `.agent/workflow.md`
- `.agent/output.md`
- `docs/REBOOT_OUTREACH_MEMORY.md`
- `output.md`

Validation:

- Required files are checked.
- Root `output.md` is prepared.
- Listed files are zipped when present.

Next:

Add review file paths to `.agent/attachments/requested-files.txt` before pushing.
