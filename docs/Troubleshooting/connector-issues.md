---
title: Connector Issues
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this runbook for connector health and sync problems.

## Symptoms

- Connector shows stale or failed sync
- Attributes expected by policy are missing
- Sudden change in decision outcomes tied to connector data

## Triage Steps

1. Confirm scope
- Single connector or multiple connectors affected?

2. Check connector status and recency
- Identify first observed failure window.

3. Validate mapping and required fields
- Confirm no recent mapping drift for critical fields.

4. Validate policy impact
- Re-run expected allow/deny scenarios.

5. Escalate
- Notify connector owner and security reviewer with findings.

## Resolution Validation

- Connector returns to healthy state
- Critical attributes repopulate
- Policy outcomes return to expected behavior

## Preventive Actions

- Define connector owner and backup
- Review mapping changes in change control
- Monitor freshness and failure trends
