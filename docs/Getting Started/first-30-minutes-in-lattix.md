---
title: First 30 Minutes in Lattix
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this runbook to complete a safe initial setup session.

## 0-10 Minutes: Access and Workspace Validation

1. Sign in and confirm you are in the correct tenant workspace.
2. Verify your role and permissions match your expected responsibilities.
3. Review workspace metadata and ownership contacts.

## 10-20 Minutes: Identity and Role Baseline

1. Confirm user role assignments for Tenant Admin and Security User.
2. Validate identity attribute availability needed for ABAC.
3. Confirm baseline authentication controls are enabled per policy.

## 20-30 Minutes: First Governed Workflow

1. Review existing ABAC policy sets (or create your initial baseline policy draft).
2. Test a simple expected-allow and expected-deny access scenario.
3. Open lineage/security views and verify the test actions are traceable.

## Success Criteria

At the end of this session, you should have:

- Confirmed secure access to the correct workspace
- Verified role assignments and attribute availability
- Completed one policy validation cycle
- Confirmed auditability for at least one test flow

## Common First-Session Mistakes

- Testing with production users before pilot validation
- Creating broad allow rules before role/attribute verification
- Skipping denial-case testing

## Next Step

Continue with your role-specific quick overview and then move into **Guides**.
