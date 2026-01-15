---
name: note-update
description: Modify existing notes on links. Use when user says "update note on *", "edit note on *", "change note on *", or similar. (plugin:rott)
allowed-tools: rott
---

# Update Note

Modifies an existing note on a link.

## Status

**Note**: The rott CLI does not currently have a direct note update command. To update a note:

1. Delete the existing note
2. Create a new note with the updated content

## Workaround Examples

### Update note on link

**User**: "Update the note on link abc123"

1. List notes: `rott link note list abc123`
2. Show user the notes and ask which to update
3. Get the note content user wants
4. Delete old note: `rott link note delete abc123 <note_id>`
5. Create new note: `rott link note create abc123 -b "<new content>"`

## CLI Commands

```bash
# List notes on a link
rott link note list <LINK_ID>

# Delete a note
rott link note delete <LINK_ID> <NOTE_ID>

# Create a new note
rott link note create <LINK_ID> -b "<body>"
```

## Notes

- This is a workaround until native note update is implemented
- Always confirm before deleting the old note
- Preserve any content the user wants to keep
