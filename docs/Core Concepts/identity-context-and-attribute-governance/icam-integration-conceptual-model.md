---
title: ICAM Integration Conceptual Model
deprecated: false
hidden: false
metadata:
  robots: index
---
ICAM integrations provide identity context used in ABAC decisions.

## Conceptual Flow

1. Identity data is sourced from approved ICAM systems.
2. Attributes are mapped to policy-relevant fields.
3. Decisions evaluate request context against mapped attributes.
4. Outcomes are recorded for governance and review.

## Design Priorities

- Stable attribute definitions
- Clear mapping ownership
- Controlled change process for schema updates
- Fallback behavior for missing/invalid identity context

## Governance Tip

Document which policies depend on each critical ICAM attribute so impact can be assessed before changes.
