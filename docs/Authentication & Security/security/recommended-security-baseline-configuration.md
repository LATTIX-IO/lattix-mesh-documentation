---
title: Recommended Security Baseline Configuration
deprecated: false
hidden: false
metadata:
  robots: index
---
Apply this baseline before broad user rollout.

## Identity and Access Baseline

- Enforce SSO for all users
- Enable MFA per organizational policy
- Assign least-privilege roles by default
- Maintain at least one backup Tenant Admin

## Governance Baseline

- Require approval for high-impact policy changes
- Use change windows for production policy publishing
- Track policy owner, approver, and review cadence

## ABAC Baseline

- Deny by default
- Keep exception rules narrow and time-bound
- Require testing for expected allow and deny paths
- Re-test after ICAM/connector mapping changes

## Connector and ICAM Baseline

- Enable only required connectors
- Define owner and support contact for each integration
- Monitor sync health and attribute freshness
- Define fallback behavior for missing critical attributes

## Monitoring and Evidence Baseline

- Review high-risk decision outcomes regularly
- Capture policy change records and validation evidence
- Maintain review logs for security and compliance teams

## Sensitive Data Handling Baseline

- Do not include secrets in docs, tickets, or screenshots
- Minimize sharing of personal/sensitive data in support artifacts
- Restrict exports to approved workflows and roles
