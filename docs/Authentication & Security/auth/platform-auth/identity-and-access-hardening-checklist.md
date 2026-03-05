---
title: Identity and Access Hardening Checklist
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this checklist to harden identity and access controls after initial setup.

## Access Model

- [ ] Least-privilege roles are in place
- [ ] Admin role is limited to required personnel
- [ ] Backup admin exists and is tested
- [ ] Role elevation follows approval workflow

## Authentication Controls

- [ ] MFA requirements enforced per policy
- [ ] Strong sign-in controls enabled for privileged users
- [ ] Inactive users are regularly removed or disabled

## Governance Controls

- [ ] Quarterly role review cadence defined
- [ ] High-impact auth/config changes require approval
- [ ] Access exceptions are time-bound and reviewed

## Operational Controls

- [ ] Login/access incident escalation path documented
- [ ] Security review owners assigned
- [ ] Sensitive troubleshooting data is redacted in tickets

## Verification

- [ ] Sample user tests confirm expected role boundaries
- [ ] Unauthorized role actions are blocked as expected
