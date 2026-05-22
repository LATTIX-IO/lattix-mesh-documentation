---
title: Supported Connectors (MVP)
deprecated: false
hidden: false
metadata:
  robots: index
---
Connectors bring approved identity and data context into Lattix policy workflows.

## How to Use This Page

Use this page as the local capability snapshot for the current connector catalog. Tenant-specific status in Mesh Dashboard remains the source of truth for saved bindings, secrets, and runtime readiness.

## Current Connector Families

### Full file-source connectors available now

These connectors currently support the most complete Lattix-managed file flow: source connection, source scoping, CID association, default policy binding, and downstream manifest, binding, and policy-review surfaces.

- Microsoft OneDrive
- Microsoft SharePoint
- Google Drive
- Box
- Dropbox

### Identity and ABAC connectors available now

These connectors sync users, groups, or roles into the tenant policy surface so ABAC subject references can use existing enterprise identity sources.

- Okta
- Microsoft Entra
- Google IdP
- Ping Identity
- Auth0

### Governance and intelligence connectors in preview

These connectors are exposed in the control plane today, but they should not be described as equivalent to the full file-source path above.

- Microsoft Purview
- Microsoft Fabric
- Varonis

Purview and Varonis are governance-workflow integrations. They are configured, status-projected, and fail closed through the control plane, but they are not generic shared-runtime file-ingest connectors.

Fabric is available as a preview registration and inventory surface. Treat it as preview until a tenant completes real upstream validation.

### Mission and operational platform connectors in preview

These connectors currently expose preview registration and scoping surfaces, not the same runtime depth as the full file-source connectors.

- Palantir Foundry
- Palantir Gotham
- Palantir AIP
- Palantir Apollo
- Palantir Maven Smart System
- Anduril Lattice

### Planned object storage connectors

- AWS S3
- Google Cloud Storage
- Azure Blob Storage

These remain planned. Do not describe them as generally available or as part of the current full TDF ABAC flow.

## Selection Guidance

Choose connectors based on:

- Required policy attributes and source systems
- Whether the use case is file ingest, identity sync, or preview governance workflow
- Operational ownership and support readiness
- Compliance and data handling requirements

## MVP Adoption Pattern

1. Start with minimum required connectors.
2. Validate policy behavior with those connectors.
3. Add preview connectors only when the workflow and validation path are explicit.
4. Expand only after tenant-specific runtime validation is complete.

## Operational Note

Each connector should have a named owner, a support contact, and a documented escalation path.

## Full TDF ABAC Flow Note

The current full Lattix-managed TDF ABAC flow is strongest when a file-source connector and an identity connector are used together:

1. The file-source connector discovers and scopes the upstream content.
2. Lattix associates the content with a CID and default policy context.
3. The identity connector provides subject context for policy evaluation.
4. Downstream manifest, binding, and policy-review surfaces operate on that protected content inside Lattix.

Preview governance and mission connectors should be treated as scoped pilot workflows until tenant-specific validation is complete.
