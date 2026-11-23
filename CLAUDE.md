# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Obsidian vault used as a knowledge base on **Test Time Training (TTT)**: papers, methods, results, and notes collected over time. It contains no code, so there is no build, lint, or test tooling. The work is writing and organizing Markdown notes.

## Structure

- `Papers/`: one note per paper, named by short title (or the full title when there is no common short name). Frontmatter: `type: paper`, `title`, `authors`, `year`, `venue`, `url`, `status` (`to-read` → `reading` → `done`), `iteration`, `tags`. Body sections are TL;DR, Problem, Method, Results, Limitations, Open questions, Related.
- `Templates/Paper.md`: the blank version of that note. New paper notes should copy it, so the frontmatter keys stay the same.
- `Iteration 1 Reading List.md`: hub linking the first batch of papers. Each reading batch gets its own hub note and a matching `iteration` number.
- `Reading Order.md`: numbered checklist of the papers in the order the user wants to read them. The order is the user's and should not be rearranged.
- `Papers.base`: table view over `Papers/`, driven by the frontmatter properties above. Renaming a property means updating the base too.
- `Welcome.md` and `Untitled.base` are leftover defaults from vault creation.

Paper stubs are created with metadata only (from the publisher pages). The body sections are intentionally empty until the user reads each paper.

## Vault setup

- The vault root is also the working directory, and it is a git repo on `main` with remote `origin` = `https://github.com/Fabeye/TTT_KDB.git`. `.gitignore` excludes `.claudian/`, `.obsidian/plugins/`, and per-device Obsidian state. The `obsidian-git` plugin is also installed. Don't commit or push unless asked.
- Community plugins in use: `realclaudian` (Claudian, the Claude integration) and `obsidian-git`. Don't edit anything under `.obsidian/` or `.claudian/` unless asked. Those folders hold app and plugin state, and the plugin `main.js` files are bundled builds.
- `.base` files are Obsidian Bases (database-style views over note properties). If the user builds a base over papers or methods, the frontmatter property names that base filters on become a de facto schema. Check them before inventing new ones.

## Working conventions

- Link notes with Obsidian wikilinks (`[[Note Name]]`), not relative Markdown links. This lets the graph and backlinks work.
- Move or rename notes through the Obsidian CLI (`obsidian vault="TestTimeTraining" move path="..." to="..."`), never `mv`, so links are updated. Folder renames go through `app.fileManager.renameFile` via `obsidian eval`.
- When adding a paper or technique, cite the source (title, authors, year, arXiv or venue link) in the note. Don't fill in results, numbers, or claims from memory. Verify them against the paper, or mark them as unverified.
