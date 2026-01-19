---
description: Use after a PR is merged or branch is abandoned. Switches to main, deletes local feature branch.
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

You will help clean up a feature branch after it has been merged or abandoned.

**Steps:**

1. **Check current state:**
   - Verify you're on a feature branch (not main)
   - If on main, inform the user there's nothing to clean up
   - If on main, suggest using `/git-start-feature` to start a new feature

2. **Update main branch:**
   - Run `git pull origin main` to ensure main is up to date

3. **Switch to main:**
   - Run `git checkout main`

4. **Delete the feature branch:**
   - Get the current branch name before checking out
   - Run `git branch -d <branch-name>` to delete the local branch
   - If the deletion fails (e.g., due to unpushed changes), offer the user two options:
     - Force delete with `git branch -D <branch-name>` (loses unpushed changes)
     - Cancel cleanup and push the branch first
   - Ask which option they prefer before proceeding with force delete

5. **Confirm completion:**
   - Confirm that the feature branch has been deleted and you're now on main
   - Optionally suggest the next step (e.g., start another feature or pull latest changes)

**Example usage:**
- `/git-cleanup-branch` → deletes current feature branch and checks out main
