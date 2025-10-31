<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

---
description: Integrate collaboration guidelines into CLAUDE.md
argument-hint: [--scope global|project]
---

You will help integrate the Clawed-Up collaboration guidelines into the user's Claude Code configuration.

**Arguments:**
- `$ARGUMENTS`: Optional `--scope global|project` flag
  - `--scope global` (default): Integrate into `~/.claude/CLAUDE.md` for use across all projects
  - `--scope project`: Integrate into `./.claude/CLAUDE.md` in the current project directory
  - If no scope specified, default to `global`

**Steps:**

1. Parse `$ARGUMENTS` to extract the scope (default to `global` if not provided)

2. Determine the target file:
   - If scope is `global`: target is `~/.claude/CLAUDE.md`
   - If scope is `project`: target is `./.claude/CLAUDE.md` in the current working directory

3. Check if the target CLAUDE.md file exists
   - If not, inform the user they need to create a basic CLAUDE.md first (provide a minimal example)
   - If it exists, proceed to step 4

4. Fetch the collaboration guidelines from:
   ```
   https://raw.githubusercontent.com/tonywalker1/Clawed-Up/main/claude/guidelines/collaboration.md
   ```

5. Check if collaboration guidelines already exist in the target file
    - Search for "Collaboration Guidelines" section
    - If found, ask the user: "Collaboration guidelines already exist. Update them (overwrite), skip, or view current
      version?"
    - If not found, proceed to step 6

6. Intelligently insert the guidelines into the target CLAUDE.md:
    - Insert after the "## Collaboration Guidelines" header if one exists (replace existing content)
    - Otherwise, insert after the first ## header (project overview section)
    - If no ## headers exist, append to the end with a new section

7. Format the integration:
    - Include a comment noting the source: `<!-- Source: Clawed-Up collaboration guidelines -->`
    - Preserve any existing custom content in the file

8. Confirm to the user:
    - Show what was added/updated
    - Specify whether this was integrated to global (~/.claude/CLAUDE.md) or project scope (./.claude/CLAUDE.md)
    - Explain the scope hierarchy: project-level CLAUDE.md overrides global settings
    - Provide the link to the source for reference

**Example usages:**
- `/integrate-collaboration-guidelines` → integrates into `~/.claude/CLAUDE.md` (default global scope)
- `/integrate-collaboration-guidelines --scope project` → integrates into `./.claude/CLAUDE.md` locally

**Expected Outcome:**
User's target CLAUDE.md file now includes the collaboration guidelines. If integrated globally, guidelines apply
to all projects unless overridden by project-specific CLAUDE.md files.
