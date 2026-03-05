---
title: Connector Security Considerations
deprecated: false
hidden: false
metadata:
  robots: index
---
Connectors are part of your security boundary. Treat connector configuration as a high-impact security control.

## Security Principles

- Least privilege for connector identities
- Explicit trust boundaries for upstream data
- Deny-safe behavior for missing critical inputs
- Continuous monitoring for connector drift

## Key Risks

- Over-permissioned connector accounts
- Stale or incorrect attributes driving decisions
- Undocumented mapping changes
- Delayed detection of sync failures

## Mitigation Practices

- Restrict connector permissions to minimum required scope
- Track mapping changes with owner and approval
- Re-test policy behavior after connector updates
- Alert on stale or failed synchronization

## Governance Controls

- Review connector access quarterly (or per internal policy)
- Record which policies depend on each critical connector attribute
- Require security review for high-risk connector changes

## Data Handling Guidance

- Minimize collection to policy-relevant fields
- Avoid exporting raw connector payloads unless required
- Redact sensitive fields in operational artifacts
