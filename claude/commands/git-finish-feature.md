---
description: Use when a feature is complete and ready for review. Commits changes, pushes branch, creates PR.
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

You will help complete a feature branch and create a pull request.

**Steps:**

1. **Check current state:**
   - Verify you're on a feature branch (not main)
   - Check for uncommitted changes: `git status`

2. **Stage relevant files:**
   - Stage all modified files related to the feature using `git add`
   - Avoid staging unrelated changes or generated files

3. **Draft commit message and PR description:**
   - Create a concise commit message (imperative mood, under 72 characters for subject)
   - Review the changes with `git diff --staged` to inform your draft
   - Include co-author attribution in the commit footer: `Co-Authored-By: Claude <noreply@anthropic.com>`
   - Draft a PR description that summarizes the feature and includes a test plan
   - Present both drafts to the user for approval before proceeding

4. **Upon user approval:**
   - Commit the changes: `git commit -m "<message>"`
   - Push the branch: `git push -u origin <current-branch>`
   - Create the PR using `gh pr create` with the drafted description

5. **Handle edge cases:**
   - If there are no staged changes, inform the user
   - If merge conflicts occur during push, guide the user through resolution
   - If gh command fails, provide helpful error guidance

**Note:** User must handle PR review and merge on GitHub manually.
