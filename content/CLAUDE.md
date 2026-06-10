# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

This is an Obsidian personal knowledge management vault. It contains Markdown notes organized using Obsidian's linking and tagging conventions. There is no build system, test suite, or compilation step.

## Obsidian Conventions

- Internal links use `[[Note Title]]` syntax (wiki-links)
- Tags use `#tag` inline or `tags:` in YAML frontmatter
- Frontmatter is YAML fenced with `---` at the top of a file
- Canvas files (`.canvas`) are JSON and represent visual note boards
- The `.obsidian/` directory holds vault configuration — avoid editing it directly

## Enabled Core Plugins

Daily notes, templates, graph, backlinks, outgoing links, tag pane, properties, bookmarks, canvas, bases, outline, and Obsidian Sync are active. Slash commands and the Zettelkasten prefixer are disabled.

## Obsidian CLI

The `obsidian` CLI (`~/.local/bin/obsidian`, v1.12.7) is installed and available. Use the `/obsidian` skill to invoke it. The Obsidian desktop app must be running — if the CLI returns "unable to find Obsidian", start it first with `snap run obsidian "obsidian://open?vault=FENB" &>/dev/null &` and wait a few seconds before retrying.

Prefer the CLI over reading raw files for:

- **Vault-wide search** — `obsidian search query="..."` is faster and more accurate than grepping Markdown
- **Health checks** — `obsidian orphans`, `obsidian deadends`, `obsidian unresolved` to find structural issues
- **Frontmatter queries** — `obsidian property:read` / `obsidian property:set` to inspect or update metadata without touching file content
- **Link analysis** — `obsidian backlinks` / `obsidian links` to trace note relationships
- **Task lists** — `obsidian tasks todo` to surface incomplete tasks across the vault
- **Bases queries** — `obsidian base:query` to pull structured data from Obsidian Bases views

## Working With Notes

- Notes are plain `.md` files; create them anywhere in the vault
- When creating notes, use YAML frontmatter for structured metadata (dates, tags, aliases)
- Prefer `[[wiki-links]]` over `[Markdown links](path)` for internal navigation

## FENB Governance Vault — Conventions

This vault contains governance analysis for Fencing-Escrime NB (FENB). Source PDFs and markdown files live in the Hugo site repo and must not be edited. Notes here are working documents.

### Folder Structure

```
FENB Governance/
├── 00 - Home/          # Hub/MOC notes
├── 01 - Foundation/    # Bylaws, Board Policy Manual, Strategic Plan
├── 02 - Policies/      # One note per policy (numbered + protocols)
├── 03 - Analysis/      # Gap analysis, cross-reference maps, architecture notes
└── 04 - Forms and Templates/  # Extracted forms and templates
```

### Frontmatter Standards

**Policy notes:**
```yaml
---
type: policy
section: "2.X"
title: ""
approved: "Month YYYY"
review-cycle: "2 years"
next-review: "Month YYYY"
status: active | archived | referenced-but-absent
tags: [policy, <domain-tag>]
---
```

**Foundation document notes:**
```yaml
---
type: foundation  # bylaw | board-policy | strategic-plan
title: ""
version-date: "Month YYYY"
status: active
tags: [bylaw | board-policy | strategic-plan]
---
```

**Analysis notes:**
```yaml
---
type: analysis
title: ""
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [analysis]
---
```

### Tagging Taxonomy

`#policy` `#bylaw` `#board-policy` `#strategic-plan` `#analysis` `#gap` `#form` `#protocol`

Domain tags: `#safe-sport` `#financial` `#hr` `#risk` `#privacy` `#dei` `#language` `#governance`

### Vault Editing Rules

- **Policy notes** include the full policy text plus a frontmatter block and an `## Observations` section below the content. Do not paraphrase policy text — keep it exact so the note is authoritative.
- **Analysis notes** are interpretive — they draw on policy notes and foundation documents and should be updated as understanding evolves.
- **Foundation document notes** contain key provisions extracted and structured, not verbatim full-text (source PDFs are the authoritative versions).
- Always use `[[note title]]` wiki-links when referencing another note in the vault.
- The `## Observations` section in any note is the place for issues, gaps, inconsistencies, and questions — keep it separate from policy text.
- When adding an observation that references a specific cross-document inconsistency, tag it with `#gap` or `#inconsistency` inline.
- Update `[[FENB Governance Hub]]` when adding new notes.
