---
name: git-add-workflow-guidance
description: Add git workflow best practices to CLAUDE.md. Use when setting up a project to use feature branch workflows.
argument-hint: [ --scope global|project ]
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

You will add git workflow guidance to the user's CLAUDE.md file.

**Arguments:**

- `$ARGUMENTS`: Optional `--scope global` or `--scope project`
  - `--scope global` (default): Add to `~/.claude/CLAUDE.md` (applies to all projects)
  - `--scope project`: Add to `.claude/CLAUDE.md` in current project

**Steps:**

1. **Determine target file:**
   - Parse `$ARGUMENTS` for `--scope` flag
   - If `--scope project`: Use `$CWD/.claude/CLAUDE.md`
   - If `--scope global` or no argument: Use `~/.claude/CLAUDE.md`

2. **Check if file exists:**
   - Read the target CLAUDE.md file
   - If file doesn't exist, create it with frontmatter and basic structure
   - Search for existing "Git Workflow" section

3. **Handle existing guidance:**
   - If "Git Workflow" section already exists:
     - Show the user the existing section
     - Ask if they want to:
       1. Keep existing (do nothing)
       2. Replace with standard guidance
       3. Append standard guidance
   - Wait for user choice

4. **Add or update the section:**
   - If no existing section or user chose to add, insert this section:

```markdown
## Git Workflow

When working on this project:

- **Starting work**: Before making changes, check current branch with `git branch --show-current`
  - If on main/master and working on a feature or non-trivial change, create a feature branch first using `/git-start-feature`
- **Incremental commits**: Use `/git-commit` for commits during development (handles staging, message drafting, co-author attribution)
- **Completing features**: Use `/git-finish-feature` to commit, push, and create a PR
- **After merge**: Use `/git-cleanup-branch` to clean up the local feature branch

**Note:** For projects that commit directly to main, `/git-commit` will offer the choice to proceed on main or create a feature branch.
```

5. **Confirm completion:**
   - Inform user which file was updated
   - Show the added section
   - Remind them this guidance will now be in context for all Claude Code sessions

**Example usages:**

- `/git-add-workflow-guidance` → adds to `~/.claude/CLAUDE.md` (global)
- `/git-add-workflow-guidance --scope project` → adds to current project's `.claude/CLAUDE.md`
