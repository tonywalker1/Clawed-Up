---
name: guidelines-collaboration
description: Integrate collaboration guidelines into CLAUDE.md
allowed-tools: Read, Edit, Write, WebFetch
argument-hint: [--scope global|project]
---

## Task

Integrate collaboration guidelines into a CLAUDE.md file.

**Argument:** $ARGUMENTS
- `--scope global` (default): target `~/.claude/CLAUDE.md`
- `--scope project`: target `./.claude/CLAUDE.md`

## Procedure

1. Determine target file based on scope
2. Verify target exists (if not, provide minimal CLAUDE.md example)
3. Fetch guidelines from:
   `https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/guidelines/collaboration.md`
4. Check if "Collaboration Guidelines" section already exists
   - If yes: ask user to update (overwrite), skip, or view current
5. Insert guidelines:
   - Replace existing section if present
   - Otherwise insert after first ## header
   - Include source comment: `<!-- Source: Clawed-Up collaboration guidelines -->`
6. Confirm what was added and where
   - Note: project-level CLAUDE.md overrides global settings
