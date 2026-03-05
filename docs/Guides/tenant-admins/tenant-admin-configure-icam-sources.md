---
title: 'Tenant Admin: Configure ICAM Sources'
deprecated: false
hidden: false
metadata:
  robots: index
---
ICAM sources supply identity context for ABAC decisions. Configure carefully to avoid unsafe policy outcomes.

## Prerequisites

- ICAM integration owner assigned
- Required attribute list defined
- Security review criteria agreed

## Steps

1. Define critical attributes
- Mark required identity attributes for access decisions.
- Identify optional attributes used for enrichment.

2. Configure attribute mappings
- Map ICAM fields to platform policy fields.
- Keep mapping names and semantics consistent.

3. Establish missing-data behavior
- For critical attributes, prefer deny or fallback workflow.
- Avoid silent allow on missing required identity context.

4. Test attribute-driven decisions
- Run allow and deny cases with representative users.
- Validate expected behavior when attributes are absent/stale.

## Validate

- Attribute mappings are complete and documented.
- Deny behavior works for missing critical attributes.
- Security reviewer confirms outcome consistency.

## Change Control

- Re-test all affected policy scenarios after mapping changes.
- Record mapping updates with owner and date.
