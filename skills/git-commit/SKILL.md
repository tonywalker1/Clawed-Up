---
name: git-commit
description: Stage changes and create an incremental commit with co-author attribution
allowed-tools: Bash(git:*)
---

## Context

- Current branch: !`git branch --show-current`
- Status: !`git status --short`
- Staged diff: !`git diff --cached --stat`
- Unstaged diff: !`git diff --stat`
- Recent commits: !`git log --oneline -5`

## Task

Create a commit for the current changes.

**If on main/master:** Warn that direct commits to main are discouraged, but proceed if user invoked this directly.

**Steps:**

1. Stage relevant modified files (avoid generated files, unrelated changes)
2. Review the diff to understand changes
3. Create commit with:
   - Concise imperative subject (under 72 chars)
   - Optional body if changes need explanation
   - Footer: `Co-Authored-By: Claude <noreply@anthropic.com>`

Use HEREDOC for multi-line commit messages.
