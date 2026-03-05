---
title: Connectors and Trust Boundaries
deprecated: false
hidden: false
metadata:
  robots: index
---
Connectors bring external identity and data context into Lattix decisions. Trust boundaries define how much confidence to place in that context.

## Why Trust Boundaries Matter

Every connector adds value and risk:

- Value: richer policy context and better decisions
- Risk: incorrect or stale inputs can create unsafe outcomes

## Connector Trust Model

- Define source ownership and accountability
- Validate minimum required data quality
- Monitor freshness and sync health
- Apply fallback/deny behavior for missing critical context

## Recommended Practices

- Classify connectors by criticality
- Require change review for critical connector settings
- Detect and alert on connector drift or sync failures
- Document which policies depend on which connector attributes

## Operational Principle

Treat connector state as part of your security posture. Policy quality cannot exceed identity/data input quality.
