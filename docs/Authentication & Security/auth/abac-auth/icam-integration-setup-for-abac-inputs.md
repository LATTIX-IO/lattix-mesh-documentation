---
title: ICAM Integration Setup for ABAC Inputs
deprecated: false
hidden: false
metadata:
  robots: index
---
This guide helps you configure ICAM identity context for reliable ABAC decisions.

## Prerequisites

- ICAM source owner assigned
- Required policy attributes defined
- Tenant Admin and Security User available for validation

## Setup Workflow

1. Define required attributes
- Identify critical attributes required for allow/deny decisions.
- Mark optional attributes for enrichment only.

2. Configure mappings
- Map ICAM identity fields to ABAC policy fields.
- Keep naming and semantics consistent across teams.

3. Define missing-attribute behavior
- For critical attributes, prefer deny or controlled fallback path.
- Avoid implicit allow on incomplete identity context.

4. Validate with test scenarios
- Expected allow
- Expected deny
- Missing attribute
- Stale attribute

## Operational Controls

- Re-test policy behavior after mapping changes
- Review attribute quality and freshness on a set cadence
- Track which policies depend on each critical attribute

## Common Failure Modes

- Over-reliance on optional attributes
- Inconsistent mappings across environments/teams
- No owner assigned for attribute lifecycle
