---
title: User Roles in Lattix
deprecated: false
hidden: false
metadata:
  robots: index
---
Lattix roles define what each person can do in the platform.

## Tenant Admin

Primary owner for tenant configuration and policy governance.

Typical responsibilities:

- Workspace administration
- Role assignment and access governance
- Connector and ICAM configuration oversight
- ABAC policy lifecycle ownership

## Security User

Focused on monitoring, verification, and investigations.

Typical responsibilities:

- Review lineage and policy enforcement outcomes
- Investigate access decisions and anomalies
- Support security reviews and incident response workflows
- Partner with Tenant Admin on policy improvements

## Passport User

Consumes approved Passport-based access workflows.

Typical responsibilities:

- Request access through supported Passport flows
- Use granted access according to policy and purpose
- Maintain compliant usage and renewal behavior

## Data Room User

Collaborates in controlled data room contexts.

Typical responsibilities:

- Participate in approved data room activities
- Share and consume data within policy boundaries
- Follow retention and usage rules

## Role Design Best Practices

- Keep role assignment minimal and intentional
- Separate admin and day-to-day user duties
- Require review for role elevation
- Audit role assignments on a regular cadence
