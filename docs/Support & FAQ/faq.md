---
title: FAQ
deprecated: false
hidden: false
metadata:
  robots: index
---
## General

### Do we need deep platform internals to use Lattix?
No. Most tenant operations are completed through role-based workflows documented in this site.

### Does Lattix provide public APIs/SDKs for MVP?
Current documentation is focused on SaaS user workflows. Public API/SDK guidance is not part of this MVP doc set.

## Access and Policies

### Why was an expected action denied?
Common causes include missing attributes, policy conditions not met, or connector sync issues.

### Why was an action unexpectedly allowed?
Review policy changes, exception rules, and attribute mappings. Escalate if high-risk exposure is suspected.

### How often should we review policies?
At minimum, maintain a regular review cadence (for example monthly), plus ad hoc review after high-impact incidents or changes.

## Connectors and ICAM

### What if a connector goes stale?
Follow the Connector Health/Troubleshooting guide and validate affected policy outcomes after recovery.

### Can we enable all connectors at once?
Not recommended. Start with minimum required connectors and expand as needed.

## Compliance and Audit

### Is using Lattix alone enough for compliance?
No. Compliance is shared responsibility. Tenant governance and evidence practices are still required.

### What evidence should we retain?
Policy change records, approval history, access decision outcomes, and remediation records for in-scope controls.
