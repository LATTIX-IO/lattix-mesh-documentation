---
title: Connector Health, Sync, and Troubleshooting
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this guide to monitor connector health and respond to sync issues.

## Health Signals to Watch

- Connector availability status
- Sync recency/freshness indicators
- Field mapping validation errors
- Decision anomalies tied to connector-dependent attributes

## Routine Health Review

1. Check connector status on a regular cadence
2. Review stale or failed sync indicators
3. Verify critical attributes remain populated
4. Confirm no unexpected policy behavior shift

## Troubleshooting Workflow

1. Identify scope
- Single user/resource impact or broad impact?

2. Validate source availability
- Confirm upstream source system is reachable and healthy.

3. Validate mapping integrity
- Confirm critical fields are still mapped correctly.

4. Validate policy impact
- Re-test expected allow/deny scenarios using affected attributes.

5. Escalate
- Route to connector owner and security reviewer with timestamped findings.

## Recovery Validation

- Sync status returns to healthy
- Critical attributes repopulate as expected
- Affected policy outcomes match expected behavior

## What Not to Include in Tickets

- Secrets, tokens, private keys
- Unnecessary sensitive data payloads
