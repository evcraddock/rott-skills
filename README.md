# Rott Skills

AI agent skills for managing links and notes using the [rott CLI](https://github.com/evcraddock/rott).

## Overview

This repository contains skill definitions that enable AI agents to interact
with the rott CLI for personal link management. Each skill is a markdown file
describing how to handle user requests and which CLI commands to run.

## Prerequisites

- [rott CLI](https://github.com/evcraddock/rott) installed and configured

## Available Skills

### Link Management

- **link-create**: Create new links with URL, tags, and optional notes
- **link-list**: List and filter links by tag (includes view details)
- **link-search**: Search links by keyword (includes view details)
- **link-update**: Edit link metadata, tags, or content
- **link-delete**: Remove links with confirmation handling

### Note Management

- **note-add**: Attach notes to existing links
- **note-update**: Modify existing notes on links

### Tag Operations

- **tag-list**: List all available tags with usage counts
- **tag-edit**: Bulk tag operations on links

### Sync

- **sync-status**: Show sync state and connectivity

## Installation

### Claude Code

```bash
/plugin marketplace add evcraddock/rott-skills
/plugin install rott@rott-skills
```

### Other Agents

Copy the `skills/` directory or individual `SKILL.md` files into your agent's
skill/prompt directory. Each skill is self-contained with examples and CLI
command references.

## Skill Format

Each skill is a directory containing a `SKILL.md` file:

```yaml
---
name: skill-name
description: When to use this skill
allowed-tools: rott
---

# Skill Title

Description and examples of user prompts with corresponding CLI commands.
```

## License

MIT License - see [LICENSE](./LICENSE) for details
