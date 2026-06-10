---
name: obsidian
description: Use the Obsidian CLI to interact with the active vault. Use when asked to search vault content, check vault health (orphans, dead ends, unresolved links), list or filter files by tag/folder, query or set frontmatter properties, inspect backlinks or outgoing links, list tasks, query Bases, or get vault statistics. Requires the Obsidian desktop app to be running.
user-invocable: true
---

# Obsidian CLI Skill

The `obsidian` CLI (at `~/.local/bin/obsidian`) lets you read and interact with the active vault without parsing raw Markdown. The Obsidian desktop app must be running for any CLI command to work.

Arguments passed: `$ARGUMENTS`

## Key syntax rules

- File targeting: `file=<name>` resolves like a wikilink (name only); `path=<path>` is exact from vault root
- Vault targeting: `vault=<name>` as the first argument (defaults to active vault)
- Quotes required for values with spaces: `name="My Note"`
- `\n` for newlines, `\t` for tabs in content values
- Output format: append `format=json|tsv|csv` to most list commands

## Common use cases

### Search vault content
```sh
obsidian search query="<text>"                    # full-text search
obsidian search:context query="<text>"            # search with surrounding line context
obsidian search query="<text>" path="FENB Governance/03 - Analysis"  # limit to folder
```

### Vault health
```sh
obsidian orphans          # files with no incoming links
obsidian deadends         # files with no outgoing links
obsidian unresolved       # broken [[wikilinks]]
obsidian orphans total    # just the count
```

### File and tag listing
```sh
obsidian files folder="FENB Governance/02 - Policies"
obsidian tags counts sort=count
obsidian tags file="Note Name"
obsidian backlinks file="Note Name" counts
obsidian links file="Note Name"
```

### Frontmatter / properties
```sh
obsidian properties file="Note Name"              # list all properties
obsidian property:read name=status file="Note Name"
obsidian property:set name=status value=active file="Note Name"
```

### Tasks
```sh
obsidian tasks todo                               # all incomplete tasks
obsidian tasks file="Note Name" verbose           # tasks in a specific note with line numbers
obsidian tasks done                               # completed tasks
```

### Bases (Obsidian database views)
```sh
obsidian bases                                    # list all base files
obsidian base:query file="BaseName" format=json   # query a base
obsidian base:views file="BaseName"               # list views in a base
```

### Vault stats
```sh
obsidian vault                                    # name, path, file/folder counts, size
obsidian files total
obsidian tags total
```

### Sync and history
```sh
obsidian sync:status
obsidian history file="Note Name"                 # list local recovery versions
obsidian diff file="Note Name"                    # compare local vs sync versions
```

## Steps

0. **Ensure Obsidian is running.** Run `obsidian version` first. If it fails with "unable to find Obsidian", launch it with `snap run obsidian "obsidian://open?vault=FENB" &>/dev/null &` and wait 3 seconds before proceeding.
1. Check `$ARGUMENTS` — if the user passed a specific sub-command or goal, execute it directly.
2. If this is an open-ended request (e.g. "check vault health"), run the relevant read-only commands and summarize findings.
3. For write operations (`property:set`, `append`, `create`, etc.), confirm with the user before executing unless the request is explicit.
4. Return output directly; don't re-read note files unless you need full content not available from CLI output.
