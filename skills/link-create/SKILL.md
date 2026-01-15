---
name: link-create
description: Create new links with URL, tags, and optional notes. Use when user says "save this link", "add a link", "bookmark this", "create link for *", or similar. (plugin:rott)
allowed-tools: rott
---

# Create Link

Creates a new link using `rott link create`.

## Examples

### Basic link creation

**User**: "Save this link: https://example.com"

Runs: `rott link create "https://example.com"`

### Link with tags

**User**: "Add a link for https://docs.rust-lang.org with tags: rust, docs"

Runs: `rott link create "https://docs.rust-lang.org" -t rust -t docs`

### Multiple tags

**User**: "Bookmark https://github.com/project tagged with programming, reference, github"

Runs: `rott link create "https://github.com/project" -t programming -t reference -t github`

## CLI Commands

```bash
# Create a link
rott link create <URL>

# Create with tags
rott link create <URL> -t <tag1> -t <tag2>

# JSON output
rott link create <URL> --json
```

## Notes

- URL is required
- Tags are optional, use multiple `-t` flags for multiple tags
- Use `--json` for structured output when parsing is needed
- After creating, the link ID is returned
