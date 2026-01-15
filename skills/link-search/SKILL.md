---
name: link-search
description: Search links by keyword across titles, descriptions, and notes. Use when user says "search links", "find links about *", "search for *", or similar. (plugin:rott)
allowed-tools: rott
---

# Search Links

Searches links using `rott link search`.

## Output Format

After fetching results, present them using AskUserQuestion. The options themselves should contain the link titles - do NOT print a separate numbered list.

Example AskUserQuestion options:
- Option 1 label: "Rust Programming Guide (rust-lang.org)"
- Option 2 label: "Learn Rust in 30 Minutes (blog.example.com)"
- Option 3 label: "Rust vs Go Comparison (medium.com)"
- Option 4 label: "None - just browsing"

Do NOT output a numbered list separately. The AskUserQuestion IS the list.

If there are more than 3 results, use "Show more..." as option 4 instead of "None".

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

### Search by keyword

**User**: "Find links about rust"

1. Runs: `rott link search "rust" --json`
2. Present results as AskUserQuestion options
3. User selects a link
4. Present "Open in browser" / "View details" options
5. Execute chosen action

### Multi-word search

**User**: "Search for machine learning tutorials"

1. Runs: `rott link search "machine learning tutorials" --json`
2. Present results as AskUserQuestion options
3. User selects a link
4. Present action options

## CLI Commands

```bash
# Search links (use JSON for parsing)
rott link search "<query>" --json

# View link details
rott link show <id> --json
```

## Notes

- Search query is required
- Searches across titles, descriptions, and notes
- Use `--json` to parse link data
- Put link titles IN the AskUserQuestion options, not as separate output
- Include domain in parentheses for context
- Two-step flow: select link, then choose action
