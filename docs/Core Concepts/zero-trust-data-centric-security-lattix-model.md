---
title: Zero Trust Data-Centric Security (Lattix Model)
deprecated: false
hidden: false
metadata:
  robots: index
---
Zero trust data-centric security assumes no request is trusted by default and that controls follow the data, not only the network perimeter.

## Why Data-Centric Matters

Traditional controls focus on location (network, app boundary). Data-centric controls focus on:

- Who is requesting access
- What data is being requested
- Why it is being requested
- Under what context and policy conditions

This model helps reduce over-permissioning and improves auditability.

## Core Principles in Lattix

- **Verify explicitly**: evaluate each access request against policy and context.
- **Least privilege**: grant the minimum access scope needed.
- **Assume breach**: design controls that limit blast radius when misuse occurs.
- **Continuous governance**: review policy outcomes and lineage signals continuously.

## Practical Outcome for Customer Teams

- More consistent access decisions
- Better traceability for security and compliance
- Faster incident investigation with policy and lineage context
- Safer collaboration for sensitive workflows

## Common Misconceptions

- Zero trust does not mean zero access.
- Data-centric control is not a one-time setup.
- ABAC is not only a policy syntax problem; identity and attribute quality are critical.
