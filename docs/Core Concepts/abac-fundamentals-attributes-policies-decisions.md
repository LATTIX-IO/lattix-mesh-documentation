---
title: ABAC Fundamentals (Attributes, Policies, Decisions)
deprecated: false
hidden: false
metadata:
  robots: index
---
Attribute-Based Access Control (ABAC) makes access decisions using attributes about users, resources, actions, and context.

## ABAC Building Blocks

- **Subject attributes**: role, team, clearance, organization unit
- **Resource attributes**: classification, owner, data domain
- **Action attributes**: read, share, export, approve
- **Context attributes**: time, session state, request origin, risk indicators

## Policy Decision Basics

Most decisions should follow:

1. Deny by default
2. Evaluate allow rules with explicit conditions
3. Apply exception and override logic intentionally
4. Return decision with rationale/audit context

## ABAC Design Tips

- Keep policies small and composable
- Prefer explicit conditions over broad wildcards
- Separate business logic from emergency exceptions
- Version policy changes and test both allow and deny outcomes

## What Breaks ABAC Programs

- Poor attribute quality from upstream systems
- Policy sprawl without ownership
- Missing review cadence for stale rules
- No traceability between decision and policy version
