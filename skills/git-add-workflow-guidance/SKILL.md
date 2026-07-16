---
name: git-add-workflow-guidance
description: Add feature-branch workflow guidance to CLAUDE.md
allowed-tools: Read, Edit, Write
argument-hint: [--scope global|project]
---

## Task

Add git workflow guidance to a CLAUDE.md file.

**Parse arguments from:** $ARGUMENTS
- `--scope project`: target `.claude/CLAUDE.md` in current project
- `--scope global` or no argument: target `~/.claude/CLAUDE.md`

**Steps:**

1. Read the target CLAUDE.md file
2. Check if a "Git Workflow" section already exists
3. If exists: show user the existing section and ask whether to keep, replace, or append
4. Add or update with this content:

```markdown
## Git Workflow

This project uses a feature-branch workflow:

- **Start work**: `/clawed-up:git-start-feature <description>` creates a branch from updated main
- **Commit**: Use `/clawed-up:git-commit` for incremental commits
- **Finish**: `/clawed-up:git-finish-feature` commits remaining changes, pushes, and creates PR
- **Cleanup**: `/clawed-up:git-cleanup-branch` deletes local branch after PR merge

Direct commits to main are discouraged. Create a feature branch for any non-trivial change.
```

5. Confirm which file was updated
