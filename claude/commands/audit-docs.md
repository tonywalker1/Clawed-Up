---
description: Audit and align documentation with codebase
argument-hint: [paths...]
---

<!--
Source: Clawed-Up (https://github.com/tonywalker1/Clawed-Up)
License: MIT - See LICENSE file or https://opensource.org/licenses/MIT
Copyright (c) 2025 Tony Walker
Contributions welcome: https://github.com/tonywalker1/Clawed-Up/blob/main/CONTRIBUTING.md
-->

# Audit Documentation for Alignment

Examine the entire project (or specified code paths) and all documentation to identify architectural, implementation,
and content misalignments. Make direct edits to documentation to fix identified issues. Focus on big-picture concerns:
architecture/implementation sync, API/function coverage, and terminology consistency across docs.

## Usage

```bash
/audit-docs                          # Examine entire project
/audit-docs src/ lib/                # Examine specific paths only
```

## What This Command Does

1. **Analyzes the codebase** to understand architecture, design patterns, and implementation details
2. **Reads all documentation** (README, guides, API docs, design docs, contributing guidelines, etc.)
3. **Identifies misalignments** at the architectural and content level:
    - Architecture/design documented but implementation diverged
    - Implementation changes not reflected in documentation
    - API additions/removals not documented or vice versa
    - Terminology inconsistencies across documents
    - Missing coverage of major features, modules, or capabilities
4. **Makes documentation edits** to align with code as identified
5. **Balances accessibility**: ensures experts find what they need quickly, newcomers find docs inviting and useful

## Instructions for Claude Code

You are conducting a comprehensive documentation audit. Follow these steps:

### Step 1: Understand the Codebase

Search and examine the codebase to understand:

- **Architecture & design patterns**: How is the system structured? What are the main components and their
  relationships?
- **Key modules/files**: What does each major component do?
- **Public APIs or exported interfaces**: For libraries, what functions/types/classes are exposed?
- **Recent changes**: Has the architecture or implementation evolved? Are there major patterns or conventions?

**Scope**: If paths are specified, examine those. Otherwise, examine the entire codebase. Focus on understanding the
*intent* and *structure*, not line-by-line code.

### Step 2: Map Existing Documentation

Identify and read all documentation files:

- Top-level docs (README, CONTRIBUTING, etc.)
- Architecture or design documents
- API/SDK documentation
- Usage guides or tutorials
- Inline documentation (docstrings, comments at the module level)
- Any other docs you find

**For each doc**: Note what it claims to cover and what audience it targets.

### Step 3: Identify Misalignments

Compare code understanding to documentation. Flag these categories:

**A. Architectural/Design Misalignment**

- Documentation describes architecture that no longer matches implementation
- Implementation patterns exist but aren't documented
- Design decisions or constraints mentioned in code but not explained in docs

**B. API/Function/Type Coverage**

- Public APIs, functions, or types added but not documented
- Documentation references removed or renamed APIs
- Exported interfaces are incomplete or inaccurate

**C. Feature or Module Coverage**

- Major features or modules exist but lack documentation
- Documentation covers features that no longer exist or are deprecated

**D. Terminology Inconsistency**

- Same concept called different names across documents
- Terminology in docs doesn't match terminology in code

**E. Audience & Tone Consistency**

- Documentation has inconsistent voice/formality across files
- Some docs are too dense for newcomers; others are unnecessarily verbose for experts

**For each issue**: Note which documents are affected and what the gap is.

### Step 4: Make Editorial Changes

For each identified misalignment:

- **Update existing docs** to reflect current architecture and implementation
- **Add missing content** where major features or APIs lack documentation
- **Standardize terminology** across docs to match code and be consistent project-wide
- **Improve clarity** where docs are confusing or inaccessible
- **Remove obsolete content** that references outdated architecture or removed features

**Guidelines for edits**:

- Use clear, pragmatic language
- For experts: Get to the point quickly; assume domain knowledge
- For newcomers: Be welcoming and provide context without overwhelming
- Keep examples concrete and relevant
- Maintain existing style/structure unless it's the problem

### Step 5: Report Findings

Provide a concise summary of:

1. **Major categories of misalignment** found (if any)
2. **Specific files and issues** addressed
3. **Changes made** (user will see in git; link to affected docs)
4. **Remaining concerns** (if any issues require user input or decision)

Keep the report brief and actionable. If no significant misalignments found, report that.

---

**Remember**: You are an editor reviewing a full draft. Make direct changes. The user will review files in git and may
follow up with additional requests.
