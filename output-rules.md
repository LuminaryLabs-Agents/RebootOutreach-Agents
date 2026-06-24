# Output Rules

Status: active

Root `output.md` is the short status text for the latest Reboot Outreach change.

## Message rules

- Use a clear headline.
- Include a short list of changes when useful.
- Describe only the latest change.
- Keep old history out.
- Keep long notes in `.agent/output.md`.

## File package rule

When requested review files should be included, list one repo-relative path per line in:

```text
.agent/attachments/requested-files.txt
```

The output workflow packages those files into:

```text
requested-files.zip
```
