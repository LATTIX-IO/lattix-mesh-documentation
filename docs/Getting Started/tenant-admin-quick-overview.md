---
title: Tenant Admin Quick Overview
deprecated: false
hidden: false
metadata:
  robots: index
---
Tenant Admins are responsible for secure, reliable tenant operation in Lattix.

## What You Own

- Workspace setup and governance
- Role assignment and least-privilege posture
- Connector and ICAM integration readiness
- ABAC policy lifecycle (draft, test, approve, publish)

## What Good Looks Like

- Access model is clearly documented and reviewed
- Policy changes follow a repeatable approval flow
- Connector health and policy outcomes are monitored
- Security and compliance reviewers can trace decisions

## Day-1 Priorities

1. Validate workspace and user roles
2. Confirm identity attributes required for ABAC
3. Stand up initial baseline policies
4. Test expected-allow and expected-deny paths
5. Confirm lineage/decision traceability

## Ongoing Responsibilities

- Review and update policies as business needs change
- Coordinate with Security Users on investigations
- Maintain connector and ICAM configuration hygiene
- Support audit and compliance evidence requests

## Avoid These Risks

- Broad allow policies without attribute checks
- Unreviewed role escalation
- Skipping denial-path testing
- Sharing sensitive credentials in docs or tickets
