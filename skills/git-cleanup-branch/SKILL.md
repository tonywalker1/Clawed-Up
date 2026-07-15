---
name: git-cleanup-branch
description: Switch to main and delete the current feature branch after PR merge
allowed-tools: Bash(git:*)
---

## Context

- Current branch: !`git branch --show-current`
- Uncommitted changes: !`git status --short`

## Task

Clean up after a merged or abandoned feature branch.

**Preconditions:**
- Must be on a feature branch (not main/master). If on main, inform user there's nothing to clean up.

**Steps:**

1. Note the current branch name before switching
2. If there are uncommitted changes, warn user and offer options:
   - Stash changes and proceed
   - Abort cleanup
3. Switch to main and update: `git checkout main && git pull origin main`
4. Delete the feature branch: `git branch -d <branch-name>`
5. If deletion fails (unpushed commits), explain and offer:
   - Force delete with `git branch -D` (loses unpushed work)
   - Abort so user can push first
6. Confirm cleanup complete
