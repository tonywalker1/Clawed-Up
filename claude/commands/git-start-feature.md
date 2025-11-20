---
description: Start a new feature branch with optional custom branch name
argument-hint: [ description ] [ --branch-name custom-branch-name ]
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

You will help start a new feature branch. Parse the arguments to extract the feature description and optional branch
name.

**Arguments:**

- `$ARGUMENTS`: The feature description (required), optionally followed by `--branch-name <custom-name>`
- If `--branch-name` is provided, use that exact name for the branch
- If only description is provided, auto-generate branch name in kebab-case from the description

**Steps:**

1. Parse `$ARGUMENTS` to separate description from optional `--branch-name` argument
2. Update the local main branch: `git pull origin main`
3. Generate branch name:
    - If `--branch-name` provided: use that name directly
    - Otherwise: convert description to kebab-case (lowercase, hyphens instead of spaces)
4. Create and checkout the new feature branch: `git checkout -b <branch-name>`
5. Confirm to the user that the feature branch has been created

**Example usages:**

- `/git-start-feature add user authentication` → creates branch `add-user-authentication`
- `/git-start-feature implement payment system --branch-name payment-v2` → creates branch `payment-v2`
