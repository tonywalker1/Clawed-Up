---
name: verify-change
description: Verify infrastructure changes before making updates
allowed-tools: Read, Edit, Bash(*)
---

## Task

Verify infrastructure changes (networks, VMs, containers, storage, documentation) before updating.

## Procedure

### 1. Confirm Understanding

Ask clarifying questions if change impacts multiple systems, files, or docs.
Don't assume the statement is complete.

**Example**: "When you say you renamed the KVM bridge, is the Linux bridge still called `br7`, or did you rename that too?"

### 2. Ask for the "Why"

Understand if it's:
- **Current state**: "This is how it runs today"
- **Aspirational**: "This is what we're moving toward"
- **Clarification**: "I meant this, not what I said before"

### 3. Request Concrete Evidence

For infrastructure changes, ask for command output or config files:
- `nmcli device status` — network config
- `virsh list` — VM state
- `podman network ls` — container networks
- Actual config files from the system

Evidence grounds discussions in reality, not abstractions.

### 4. Update in Minimal Scope

Make the specific correction, then verify it doesn't require changes elsewhere before updating multiple locations.

## Principles

- Don't assume: distinguish current vs planned/aspirational
- Don't proceed silently: ask if unclear rather than interpret
- Verify with evidence: system output > descriptions
