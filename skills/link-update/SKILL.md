---
name: link-update
description: Edit link metadata, tags, or content. Use when user says "edit link *", "update link *", "change link *", "modify link *", or similar. (plugin:rott)
allowed-tools: rott
---

# Update Link

Edits a link using `rott link edit`.

## Examples

### Edit by ID

**User**: "Edit link abc123"

Runs: `rott link edit abc123`

Note: This opens an interactive editor for the link.

### Search then edit

**User**: "Update the rust docs link"

1. Runs: `rott link search "rust docs"`
2. If single match: `rott link edit <id>`
3. If multiple matches: ask user to select

## CLI Commands

```bash
# Edit link by ID (full UUID or prefix)
rott link edit <ID>
```

## Notes

- Link ID can be full UUID or a unique prefix
- Opens an interactive editor to modify the link
- If no ID provided, search by keywords first
- Changes are saved when the editor is closed
