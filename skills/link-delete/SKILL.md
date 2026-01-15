---
name: link-delete
description: Remove links with confirmation handling. Use when user says "delete link *", "remove link *", "trash link *", or similar. (plugin:rott)
allowed-tools: rott
---

# Delete Link

Deletes a link using `rott link delete`.

## Examples

### Delete by ID

**User**: "Delete link abc123"

1. Confirm with user: "Are you sure you want to delete link abc123?"
2. If confirmed: `rott link delete abc123`

### Search then delete

**User**: "Remove the old tutorial link"

1. Runs: `rott link search "old tutorial"`
2. If single match: confirm and `rott link delete <id>`
3. If multiple matches: ask user to select

## CLI Commands

```bash
# Delete link by ID (full UUID or prefix)
rott link delete <ID>
```

## Notes

- **Always confirm before deleting**
- Link ID can be full UUID or a unique prefix
- Deletion is permanent
- If no ID provided, search by keywords first
- Multiple matches require user selection
