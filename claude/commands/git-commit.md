---
name: git-commit
description: Use when making incremental commits during development. Stages changes, drafts commit message with co-author attribution, gets approval.
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

You will help create an incremental commit on the current branch.

**Steps:**

1. **Check current state:**
   - Get current branch name: `git branch --show-current`
   - If on `main` or `master`:
     - Inform the user that committing directly to main is generally discouraged
     - Offer two options:
       1. Create a feature branch first using `/git-start-feature` (recommended)
       2. Proceed with commit to main anyway
     - Wait for user to choose before proceeding
   - Check for uncommitted changes: `git status`

2. **Stage relevant files:**
   - Stage all modified files related to the current change using `git add`
   - Avoid staging unrelated changes or generated files

3. **Draft commit message:**
   - Review the changes with `git diff --staged` to inform your draft
   - Create a concise commit message in imperative mood
   - Subject line should be under 72 characters
   - Include co-author attribution in the commit footer: `Co-Authored-By: Claude <noreply@anthropic.com>`
   - Present the draft to the user for approval before proceeding

4. **Upon user approval:**
   - Commit the changes: `git commit -m "<message>"`

5. **Handle edge cases:**
   - If there are no staged changes, inform the user
   - If `git status` shows untracked files that should be staged, clarify with the user

**Note:** This command creates a local commit only. The branch will be pushed when using `/git-finish-feature`.
