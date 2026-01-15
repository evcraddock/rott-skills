---
name: tag-edit
description: Bulk tag operations on links. Use when user says "rename tag *", "merge tags", "bulk edit tags", or similar. (plugin:rott)
allowed-tools: rott
---

# Edit Tags

Performs bulk tag operations on links.

## Status

**Note**: The rott CLI does not currently have a direct bulk tag edit command. Tag operations must be done per-link using `rott link edit`.

## Workaround Examples

### Rename a tag across all links

**User**: "Rename tag 'programming' to 'dev'"

1. List links with the tag: `rott link list -t programming --json`
2. For each link, edit to update the tag
3. This requires editing each link individually with `rott link edit <id>`

### Add tag to multiple links

**User**: "Add tag 'archived' to these links"

1. For each link ID provided, edit the link to add the tag
2. Use `rott link edit <id>` for each link

## CLI Commands

```bash
# List links with a tag
rott link list -t <tag>

# Edit a link (to modify its tags)
rott link edit <ID>
```

## Notes

- Bulk tag operations require editing links individually
- Use `rott link list -t <tag> --json` to find all links with a tag
- Consider this a limitation to address in future rott CLI versions
