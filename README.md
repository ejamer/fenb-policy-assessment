# FENB Policy Assessment

Assessment and analysis of governance documentation for the Fédération d'escrime du Nouveau-Brunswick (FENB), organized as an Obsidian vault and published as a static site.

**Hosted site: https://ejamer.github.io/fenb-policy-assessment/fenb-governance/00---home/fenb-governance-hub**

## Overview

This project uses [Quartz v5](https://quartz.jzhao.xyz/) to publish an Obsidian vault containing structured analysis of FENB's policy framework — including policy inventory, gap analysis, cross-reference mapping, and recommended actions.

## Folder Structure

```
content/                        # Obsidian vault (symlinked from ~/Documents/Obsidian/FENB)
├── FENB Governance/
│   ├── 00 - Home/              # Entry point and navigation
│   ├── 01 - Foundation/        # Bylaws, Board Policy Manual, Strategic Plan
│   ├── 02 - Policies/          # Individual policy notes and index
│   ├── 03 - Analysis/          # Gap register, cross-reference map, recommendations
│   └── 04 - Forms and Templates/
└── source_files/
    ├── governance-pdfs/        # Source PDF documents
    └── policies/               # Bilingual policy source files (.en.md / .fr.md)

quartz/                         # Quartz framework (do not edit)
quartz.config.default.yaml      # Site configuration (title, baseUrl, plugins)
.github/workflows/deploy.yml    # GitHub Actions — builds and deploys on push to main
```

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
