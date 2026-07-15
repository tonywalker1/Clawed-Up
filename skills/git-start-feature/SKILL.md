---
name: git-start-feature
description: Create a feature branch from main with auto-generated or custom name
allowed-tools: Bash(git:*)
argument-hint: [branch-name]
---

## Context

- Current branch: !`git branch --show-current`
- Local changes: !`git status --short`

## Task

Create a new feature branch from an updated main branch.

**Argument:** $ARGUMENTS (optional branch name)
- If provided: use that exact name
- If omitted: ask the user what to name the branch

**Steps:**

1. If there are uncommitted changes, warn and stop (user should commit or stash first)
2. Fetch and update main: `git checkout main && git pull origin main`
3. Create and checkout the feature branch: `git checkout -b <branch-name>`
4. Confirm the new branch is active

**Examples:**
- `/git-start-feature add-user-auth` → creates branch `add-user-auth`
- `/git-start-feature` → prompts for branch name
