---
name: sync-status
description: Show sync state and connectivity. Use when user says "sync status", "am I synced", "check sync", "what's my sync status", or similar. (plugin:rott)
allowed-tools: rott
---

# Sync Status

Shows sync state using `rott status`.

## Examples

### Check sync status

**User**: "What's my sync status?"

Runs: `rott status`

### JSON output

**User**: "Show sync status as JSON"

Runs: `rott status --json`

## CLI Commands

```bash
# Show status
rott status

# JSON output
rott status --json
```

## Notes

- Shows root document ID and sync status
- Use `--json` for structured output when parsing is needed
- Indicates if local changes need syncing
