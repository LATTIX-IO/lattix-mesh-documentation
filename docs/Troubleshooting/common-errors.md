---
title: Common Errors
deprecated: false
hidden: false
metadata:
  robots: index
---
This page lists common issues and how to resolve them quickly.

## Access Denied Unexpectedly

Possible causes:

- Missing required attributes
- Policy condition mismatch
- Role assignment not aligned with expected scope

Actions:

1. Confirm user role and intended action scope
2. Validate required attributes are present/current
3. Review recent policy changes

## Access Allowed Unexpectedly

Possible causes:

- Overly broad policy condition
- Unexpired exception rule
- Incorrect attribute mapping

Actions:

1. Identify policy rule responsible for allow
2. Validate exception state and expiration
3. Escalate to security/admin if high-risk

## User Cannot Sign In

Possible causes:

- Identity provider mismatch
- User not assigned to required role/group
- Session/auth policy mismatch

Actions:

1. Confirm account assignment and role mapping
2. Re-attempt with known-good user context
3. Open support request with redacted details if unresolved

## Best Practice

Always capture expected vs actual behavior and a time window before escalation.
