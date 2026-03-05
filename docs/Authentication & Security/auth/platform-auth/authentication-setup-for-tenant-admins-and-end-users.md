---
title: Authentication Setup for Tenant Admins and End Users
deprecated: false
hidden: false
metadata:
  robots: index
---
This guide covers secure onboarding for user authentication in a SaaS tenant.

## Prerequisites

- Tenant workspace exists
- Tenant Admin assigned
- Identity/ICAM contacts confirmed

## Setup Workflow

1. Define role groups
- Tenant Admins
- Security Users
- Standard end users (Passport/Data Room as needed)

2. Configure authentication policy
- Enforce organization-approved sign-in requirements (including MFA where required)
- Restrict role assignment to authorized admins

3. Assign initial users
- Add minimum set of users for pilot
- Validate each user receives only required permissions

4. Validate end-to-end sign-in
- Confirm successful sign-in for each role type
- Confirm role-scoped access is enforced

## Post-Setup Checks

- Backup admin account is assigned
- No broad admin assignments remain
- Support contacts know escalation path for login/access issues

## Security Reminder

Never share credentials or session artifacts for troubleshooting. Use approved support channels and redacted evidence.
