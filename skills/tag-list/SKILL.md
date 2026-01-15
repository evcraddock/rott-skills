---
name: tag-list
description: List all available tags with usage counts. Use when user says "list tags", "show tags", "what tags do I have", or similar. (plugin:rott)
allowed-tools: rott
---

# List Tags

Lists all tags using `rott tags`.

## Examples

### List all tags

**User**: "Show me all my tags"

Runs: `rott tags`

### JSON output

**User**: "List tags as JSON"

Runs: `rott tags --json`

## CLI Commands

```bash
# List all tags
rott tags

# JSON output
rott tags --json
```

## Notes

- Shows all tags with usage counts
- Use `--json` for structured output when parsing is needed
- Tags are derived from all links in the collection
