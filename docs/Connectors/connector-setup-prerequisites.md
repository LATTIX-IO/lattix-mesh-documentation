---
title: Connector Setup Prerequisites
deprecated: false
hidden: false
metadata:
  robots: index
---
Complete these prerequisites before enabling any connector in production.

## Ownership and Governance

- Assign a connector owner
- Assign security reviewer
- Define approval path for connector changes

## Technical Readiness

- Confirm access to required source systems
- Confirm required attributes/fields are available
- Define field mapping requirements for ABAC usage

## Security and Compliance Readiness

- Verify data classification and handling requirements
- Confirm least-privilege access for connector integration accounts
- Confirm redaction requirements for troubleshooting evidence

## Microsoft OneDrive and SharePoint Minimum Setup

- Use the shared Lattix Microsoft connector app model rather than creating ad hoc tenant-wide Graph apps per operator.
- Provision two multi-tenant confidential web apps:
  - discovery plane for scoped discovery
  - bootstrap plane for approved enterprise/bootstrap workflows
- Use the current policy-compliant display names `Lattix Graph Discovery Connector` and `Lattix Graph Bootstrap Connector`. The tenant currently blocks `Microsoft` in custom app display names.
- Register all approved callback URIs on both apps:
  - `https://app.lattix.io/api/connectors/onedrive/callback`
  - `https://app.lattix.io/api/connectors/sharepoint/callback`
  - `https://internal.lattix.io/api/connectors/onedrive/callback`
  - `https://internal.lattix.io/api/connectors/sharepoint/callback`
  - `https://acme.lattix.io/api/connectors/onedrive/callback`
  - `https://acme.lattix.io/api/connectors/sharepoint/callback`
- Persist the mesh-dashboard shared secret contract in Key Vault:
  - `conn-microsoft-discovery-client-id`
  - `conn-microsoft-discovery-client-secret`
  - `conn-microsoft-discovery-onedrive-redirect-uri`
  - `conn-microsoft-discovery-sharepoint-redirect-uri`
  - `conn-microsoft-bootstrap-client-id`
  - `conn-microsoft-bootstrap-client-secret`
  - `conn-microsoft-bootstrap-onedrive-redirect-uri`
  - `conn-microsoft-bootstrap-sharepoint-redirect-uri`
- Default the stored redirect URI secrets to the canonical public host `app.lattix.io` even though the app registrations also allow `internal` and tenant-host callback URIs. Mesh-dashboard shares the OAuth cookies across `*.lattix.io`, so the callback can safely complete on the canonical host.
- Discovery plane delegated Graph scopes:
  - `User.Read`
  - `offline_access`
  - `Sites.Selected`
  - `Files.SelectedOperations.Selected`
  - `Lists.SelectedOperations.Selected`
- Bootstrap plane delegated Graph scopes:
  - `User.Read`
  - `offline_access`
  - `Files.Read.All`
  - `Sites.Read.All`
- Operator approval model:
  - `scoped` is the default self-service path
  - `enterprise` requires a reviewed permission-change reference before the user can continue in the dashboard
  - `bootstrap` is reserved for internal/JIT workflows and should not be offered as self-service OAuth
- Grant home-tenant admin consent for the scopes required by the test tenant before running live smoke validation. External customer consent remains tenant-local and should be approved through that tenant's normal admin path.

## Microsoft Purview Minimum Setup

- Use a dedicated Entra app registration or service principal for client-credentials auth. Do not use personal user credentials for connector runtime access.
- Collect the minimum connector inputs: Purview account name, Entra tenant ID, client ID, and client secret or certificate.
- Request tokens for `https://purview.azure.net/.default`.
- For a read or import smoke, assign the service principal the minimum Purview read role on the target account or collection. Use a read-only assignment first and raise to a broader governance role only if later writeback flows need it.
- Optionally scope the connector to the root collection you want to validate first instead of the full account.
- Store client secrets in Key Vault and rotate them through the normal service-principal secret process.

## Operational Readiness

- Define health monitoring expectations
- Define sync-failure escalation path
- Define rollback strategy for misconfiguration

## Pre-Go-Live Checklist

- [ ] Owner and reviewers assigned
- [ ] Required fields mapped and validated
- [ ] Health checks visible
- [ ] Escalation runbook documented
- [ ] Test scenarios passed (allow/deny/missing data)
