---
name: audit-docs
description: Audit and align documentation with codebase
allowed-tools: Read, Edit, Write, Glob, Grep, Task
argument-hint: [paths...]
---

## Task

Examine the project (or specified paths) and all documentation to identify misalignments. Make direct edits to fix issues.

**Scope:** $ARGUMENTS (specific paths) or entire project if omitted.

## Procedure

### 1. Understand the Codebase

- Architecture and design patterns
- Key modules and their responsibilities
- Public APIs and exported interfaces
- Recent changes and conventions

### 2. Map Documentation

Identify and read all docs: README, CONTRIBUTING, design docs, API docs, guides, module-level comments.

### 3. Identify Misalignments

**Categories:**
- **Architectural**: Docs describe outdated architecture, or implementation patterns undocumented
- **API coverage**: Public APIs added but not documented, or docs reference removed APIs
- **Feature coverage**: Major features lack docs, or docs cover removed features
- **Terminology**: Inconsistent naming across docs or between docs and code
- **Tone/audience**: Inconsistent voice, or docs inaccessible to target audience

### 4. Make Edits

- Update docs to reflect current implementation
- Add missing content for major features/APIs
- Standardize terminology
- Remove obsolete content
- Balance accessibility: experts find info quickly, newcomers aren't overwhelmed

### 5. Report

Provide concise summary:
1. Major categories of misalignment found
2. Files and issues addressed
3. Changes made
4. Remaining concerns requiring user input
