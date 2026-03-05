---
title: Connector Setup Prerequisites
deprecated: false
hidden: false
metadata:
  robots: index
---
Complete these prerequisites before enabling any connector in production.

## Ownership and Governance

- Assign a connector owner
- Assign security reviewer
- Define approval path for connector changes

## Technical Readiness

- Confirm access to required source systems
- Confirm required attributes/fields are available
- Define field mapping requirements for ABAC usage

## Security and Compliance Readiness

- Verify data classification and handling requirements
- Confirm least-privilege access for connector integration accounts
- Confirm redaction requirements for troubleshooting evidence

## Operational Readiness

- Define health monitoring expectations
- Define sync-failure escalation path
- Define rollback strategy for misconfiguration

## Pre-Go-Live Checklist

- [ ] Owner and reviewers assigned
- [ ] Required fields mapped and validated
- [ ] Health checks visible
- [ ] Escalation runbook documented
- [ ] Test scenarios passed (allow/deny/missing data)
