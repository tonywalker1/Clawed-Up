---
name: git-finish-feature
description: Commit remaining changes, push branch, and create a pull request
allowed-tools: Bash(git:*), Bash(gh:*)
---

## Context

- Current branch: !`git branch --show-current`
- Uncommitted changes: !`git status --short`
- Staged changes: !`git diff --cached --stat`
- Recent commits on this branch: !`git log --oneline -5`
- Commits ahead of main: !`git log --oneline main..HEAD 2>/dev/null || echo "N/A"`

## Task

Complete the current feature branch by committing any remaining changes, pushing, and creating a PR.

**Preconditions:**
- Must be on a feature branch (not main/master). If on main, inform user and stop.

**Steps:**

1. Stage relevant modified files (avoid unrelated changes or generated files)
2. Create a commit with:
   - Concise imperative subject line (under 72 chars)
   - Footer: `Co-Authored-By: Claude <noreply@anthropic.com>`
3. Push the branch: `git push -u origin <branch-name>`
4. Create PR using `gh pr create`:
   - Title: derive from branch name or commit subject
   - Body: summarize changes, include test plan section
   - Use HEREDOC for body formatting

**If no uncommitted changes:** Skip to push and PR creation.

**On errors:** Provide actionable guidance (e.g., merge conflicts, gh auth issues).
