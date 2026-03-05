---
title: Policy Evaluation Issues
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this guide when policy outcomes are inconsistent with expected intent.

## Common Symptoms

- Expected allow returns deny
- Expected deny returns allow
- Same scenario produces inconsistent outcomes

## Investigation Steps

1. Capture context
- User role/attributes, resource scope, action, timestamp.

2. Identify active policy version
- Confirm which rule set evaluated the request.

3. Validate decision path
- Determine which condition matched or failed.

4. Validate attribute quality
- Check missing, stale, or conflicting identity/context attributes.

5. Validate recent changes
- Review policy, connector, and role changes in the same time window.

## Root Cause Categories

- Policy logic issue
- Attribute/mapping issue
- Role assignment issue
- Connector synchronization issue

## Fix and Verify

1. Apply controlled remediation
2. Re-test allow/deny/exception scenarios
3. Document outcome and preventive action

## Escalate Immediately If

- High-risk data is being overexposed
- Multiple policy domains are impacted
- Root cause remains unknown after standard triage
