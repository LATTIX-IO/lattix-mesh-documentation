---
title: 'Tenant Admin: Set Up Connectors'
deprecated: false
hidden: false
metadata:
  robots: index
---
Connectors provide identity/data context used in policy decisions. Configure them with explicit trust and ownership.

## Prerequisites

- Connector prerequisites completed (source access, approvers, owners)
- Security reviewer available for first activation
- Change window defined for production updates

## Steps

1. Select connector scope
- Enable only connectors required for current workflows.
- Avoid enabling optional sources until needed.

2. Configure connector settings
- Map required fields for intended policy use.
- Document owner and support contact for each connector.

3. Enable health monitoring
- Confirm status checks are visible.
- Define alert/escalation path for sync failures.

4. Validate data readiness
- Confirm key attributes required by ABAC are present and current.

## Validate

- Connector shows healthy sync state.
- Required attributes are available for test users/resources.
- Security reviewer can trace connector-dependent policy outcomes.

## Operational Notes

- Treat connector changes as security-impacting changes.
- Re-test policy outcomes after connector mapping updates.
