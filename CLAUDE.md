# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault used as a knowledge base on **Test Time Training (TTT)**: papers, methods, results, and notes collected over time. It contains no code, so there is no build, lint, or test tooling. The work is writing and organizing Markdown notes.

The vault was just created. It holds only the default `Welcome.md` and an empty `Untitled.base`. There is no folder taxonomy, note template, or naming scheme yet. Before adding notes, look at what exists and follow any structure the user has since established. If you introduce a new convention (folders, frontmatter properties, a naming pattern), say so and then record it in this file.

## Vault setup

- The vault root is also the working directory, and it is not a git repository. The `obsidian-git` plugin is installed, so versioning is meant to go through Obsidian, not manual `git init`.
- Community plugins in use: `realclaudian` (Claudian, the Claude integration) and `obsidian-git`. Don't edit anything under `.obsidian/` or `.claudian/` unless asked. Those folders hold app and plugin state, and the plugin `main.js` files are bundled builds.
- `.base` files are Obsidian Bases (database-style views over note properties). If the user builds a base over papers or methods, the frontmatter property names that base filters on become a de facto schema. Check them before inventing new ones.

## Working conventions

- Link notes with Obsidian wikilinks (`[[Note Name]]`), not relative Markdown links. This lets the graph and backlinks work.
- Move or rename notes through the Obsidian CLI (`obsidian vault="TestTimeTraining" move path="..." to="..."`), never `mv`, so links are updated. Folder renames go through `app.fileManager.renameFile` via `obsidian eval`.
- When adding a paper or technique, cite the source (title, authors, year, arXiv or venue link) in the note. Don't fill in results, numbers, or claims from memory. Verify them against the paper, or mark them as unverified.
