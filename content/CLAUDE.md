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

The `obsidian` CLI (`~/.local/bin/obsidian`, v1.12.7) is installed and available. Use the `/obsidian-cli` skill to invoke it. The Obsidian desktop app must be running — if the CLI returns "unable to find Obsidian", start it first with `snap run obsidian "obsidian://open?vault=FENB" &>/dev/null &` and wait a few seconds before retrying.

Related skills: `/obsidian-markdown` for Obsidian-flavored Markdown syntax, `/obsidian-bases` for `.base` files, `/json-canvas` for `.canvas` files.

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
├── 01 - Analysis/      # Gap analysis, cross-reference maps, architecture notes
├── 02 - Foundation/    # Bylaws, Board Policy Manual, Strategic Plan
├── 03 - Policies/      # One note per policy (numbered + protocols)
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
related-policies: ["2.X", "2.Y"]
source-file:
  - "[[slug.en]]"
  - "[[slug.fr]]"
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
source-file:
  - "[[slug-en]]"
  - "[[slug-fr]]"
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

### Note Structure

Policy, foundation, form, and protocol notes all follow this section order to foreground assessment over summary:

```
frontmatter
# Title
(callout / approval date if applicable)

## Related Policies
(wiki-links to directly related notes)

## Observations
(gaps, inconsistencies, questions — tagged with #gap or #inconsistency inline)

## Summary
(structured summary of the source document's content)
```

The `source-file` frontmatter field links to the source `.en`/`.fr` wiki-link slugs. The source files are authoritative; the vault note is an assessed summary, not a verbatim copy.

### Vault Editing Rules

- **Policy and foundation notes** contain a structured summary of the source document under `## Summary`. Do not attempt to reproduce verbatim text — the source files are authoritative. Headings within `## Summary` are H3 (or H4 for nested subsections).
- **Analysis notes** are interpretive — they draw on policy notes and foundation documents and should be updated as understanding evolves. They do not have a `## Summary` section; content flows directly.
- Always use `[[note title]]` wiki-links when referencing another note in the vault.
- The `## Observations` section is the place for issues, gaps, inconsistencies, and questions. Keep it above `## Summary` so assessment is encountered before content.
- When adding an observation that references a specific cross-document inconsistency, tag it with `#gap` or `#inconsistency` inline.
- Update `[[FENB Governance Hub]]` when adding new notes.
- For CLI write operations (`property:set`, `append`, `create`), confirm with the user before executing unless the request is explicit.
