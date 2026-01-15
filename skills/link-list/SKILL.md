---
name: link-list
description: List and filter links by tag. Use when user says "list links", "show my links", "links with tag *", "list bookmarks", or similar. (plugin:rott)
allowed-tools: rott
---

# List Links

Lists links using `rott link list` with optional filtering.

## Output Format

After fetching links, present them using AskUserQuestion. The options themselves should contain the link titles - do NOT print a separate numbered list.

Example AskUserQuestion options:
- Option 1 label: "Two AI researchers funded by Solana (ghuntley.com)"
- Option 2 label: "How to Debug Your Life (joanwestenberg.com)"
- Option 3 label: "Crypto scammers... (example.com)"
- Option 4 label: "None - just browsing"

Do NOT output a numbered list separately. The AskUserQuestion IS the list.

If there are more than 3 links, use "Show more..." as option 4 instead of "None".

## After Selection

When the user selects a link, present a second AskUserQuestion:

- Option 1 label: "Open in browser"
- Option 2 label: "View details"

If user selects "Open in browser", open the URL in the default browser.

If user selects "View details", run `rott link show <id> --json` and display:
- Title
- URL
- Tags
- Notes (if any)
- Created/updated dates

## Examples

### List all links

**User**: "Show me my links"

1. Runs: `rott link list --json`
2. Present links as AskUserQuestion options
3. User selects a link
4. Present "Open in browser" / "View details" options
5. Execute chosen action

### Filter by tag

**User**: "List links tagged with rust"

1. Runs: `rott link list -t rust --json`
2. Present links as AskUserQuestion options
3. User selects a link
4. Present action options

## CLI Commands

```bash
# List all links (use JSON for parsing)
rott link list --json

# Filter by tag
rott link list -t <tag> --json

# View link details
rott link show <id> --json
```

## Notes

- Use `--json` to parse link data
- Put link titles IN the AskUserQuestion options, not as separate output
- Include domain in parentheses for context
- Two-step flow: select link, then choose action
