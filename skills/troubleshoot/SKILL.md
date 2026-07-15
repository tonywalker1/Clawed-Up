---
name: troubleshoot
description: Evidence-based troubleshooting with pivot recognition
allowed-tools: Read, Bash(*), Grep, Glob
---

## Task

Debug persistent issues using evidence-based approach. Recognize when to pivot.

## Pivot Signals

Change approach when:
- Same error across multiple "should work" configurations → problem is fundamental
- 3-4+ hours on single error with no progress → likely upstream bug or incompatibility
- Multiple reinstalls/reconfigurations fail identically → configuration isn't the issue

## Pivot Procedure

1. **Document**: Capture what was tried and what failed
2. **Propose alternative**: Present fundamentally different solution
3. **Explain trade-offs**: Why alternative addresses root cause
4. **Get approval**: Architecture changes require user decision

## Key Insight

When the same error persists across multiple "correct" configurations, the problem is usually:
- Upstream bug
- Version incompatibility
- Environmental assumption that doesn't hold

Stop debugging configuration and consider architectural alternatives.

## Example

Graylog 6.0.x RPM had persistent Guice errors across OpenSearch 2.11, 2.14, 2.15.
After 4+ hours, pivoted to containerized Graylog 5.2.0 which worked immediately.
