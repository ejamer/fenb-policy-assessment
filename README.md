# FENB Policy Assessment

Assessment and analysis of governance documentation for the Fédération d'escrime du Nouveau-Brunswick (FENB), organized as an Obsidian vault and published as a static site.

**Hosted site: https://ejamer.github.io/fenb-policy-assessment/**

## Overview

This project uses [Quartz v5](https://quartz.jzhao.xyz/) to publish an Obsidian vault containing structured analysis of FENB's policy framework — including policy inventory, gap analysis, cross-reference mapping, and recommended actions.

## Folder Structure

```
content/                        # Obsidian vault (symlinked from ~/Documents/Obsidian/FENB)
├── FENB Governance/
│   ├── 00 - Home/                # Entry point and navigation
│   ├── 01 - Analysis/            # Gap register, cross-reference map, recommendations
│   ├── 02 - Foundation/          # Bylaws, Board Policy Manual, Strategic Plan
│   ├── 03 - Policies/            # Individual policy, protocol, and annex notes
│   └── 04 - Forms and Templates/
├── ob-templates/                 # Obsidian templates for new notes (see Note Templates below)
└── source_files/
    ├── governance-pdfs/        # Source PDF documents
    └── policies/               # Bilingual policy source files (.en.md / .fr.md)

quartz/                         # Quartz framework (do not edit)
quartz.config.default.yaml      # Site configuration (title, baseUrl, plugins)
.github/workflows/deploy.yml    # GitHub Actions — builds and deploys on push to main
```

## Note Templates

Templates for new governance notes live in `content/ob-templates/` and are configured as the vault's template folder (Settings → Templates → Template folder location: `ob-templates`).

To use one: place your cursor where the new content should go, open the command palette (Ctrl/Cmd+P), run **Insert template**, and pick one of:

| Template | Use for | Target folder |
|---|---|---|
| **Foundation Document** | Bylaws, Board Policy Manual, Strategic Plan, and other foundational governance documents | `02 - Foundation/` |
| **Policy Note** | Individual numbered policies (e.g. `2.6 Financial Management`) | `03 - Policies/` |
| **Protocol Note** | Operational protocols without a formal policy number (e.g. Concussion Protocol); pre-flags a missing approval date with a `#gap` tag | `03 - Policies/` |
| **Annex Note** | Schedules/annexes to a policy that the Board can amend without a full policy review | `03 - Policies/` |
| **Form Note** | Intake or administrative forms referenced by a policy | `04 - Forms and Templates/` |
| **Analysis Note** | New entries for the gap register, cross-reference map, or other analysis documents | `01 - Analysis/` |

Each template pre-fills frontmatter (`type`, `status`, `tags`, `source-file`, etc.) and a standard section skeleton (Related Policies, Observations, Source Summary, Summary). After inserting, fill in the title, dates, and any bracketed placeholders, and link the bilingual source files under `source-file`.

## Build & Deploy

The site builds and deploys automatically via GitHub Actions on every push to `main`.

To preview locally:

```bash
# Requires Node 22+
export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh"
npx quartz build --serve
# Site available at http://localhost:8080
```

To publish changes after editing in Obsidian:

```bash
git add content/
git commit -m "your message"
git push
```
