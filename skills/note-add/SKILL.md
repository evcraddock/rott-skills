---
name: note-add
description: Attach notes to existing links. Use when user says "add note to link *", "note on link *", "attach note to *", or similar. (plugin:rott)
allowed-tools: rott
---

# Add Note

Adds a note to a link using `rott link note create`.

## Examples

### Add note with body

**User**: "Add a note to link abc123: This is a great resource"

Runs: `rott link note create abc123 -b "This is a great resource"`

### Add note with title and body

**User**: "Add a note titled 'Summary' to link abc123 with body: Key concepts explained"

Runs: `rott link note create abc123 -T "Summary" -b "Key concepts explained"`

### Search then add note

**User**: "Add a note to the rust docs link"

1. Runs: `rott link search "rust docs"`
2. If single match: ask for note content, then `rott link note create <id> -b "<content>"`
3. If multiple matches: ask user to select

## CLI Commands

```bash
# Add note with body
rott link note create <LINK_ID> -b "<body>"

# Add note with title and body
rott link note create <LINK_ID> -T "<title>" -b "<body>"

# JSON output
rott link note create <LINK_ID> -b "<body>" --json
```

## Notes

- Link ID is required (full UUID or prefix)
- Body is required (use `-b` flag)
- Title is optional (use `-T` flag)
- If body is not provided via flag, an editor opens
- If no link ID provided, search by keywords first
