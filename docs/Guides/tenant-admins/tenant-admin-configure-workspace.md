---
title: 'Tenant Admin: Configure Workspace'
deprecated: false
hidden: false
metadata:
  robots: index
---
This guide helps you complete a secure baseline tenant setup.

## Prerequisites

- Tenant Admin role assigned
- Initial user list and role plan approved
- Security reviewer identified

## Steps

1. Confirm workspace context
- Verify you are in the correct tenant/workspace.
- Check owner contacts and tenant metadata.

2. Configure role baseline
- Assign primary and backup Tenant Admins.
- Assign Security Users for review and investigation.
- Assign pilot Passport/Data Room users.

3. Apply least-privilege defaults
- Remove unnecessary broad access.
- Keep high-impact actions limited to admin roles.

4. Define governance owners
- Name owners for policy changes, connector changes, and exception approvals.

## Validate

- Expected users can sign in and see only expected scopes.
- Security reviewers can access required review views.
- No generic broad role remains in production user assignments.

## Common Mistakes

- Assigning admin role to all early users
- Skipping backup admin assignment
- No documented owner for approval workflows
