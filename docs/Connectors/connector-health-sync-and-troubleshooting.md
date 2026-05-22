---
title: Connector Health, Sync, and Troubleshooting
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this guide to monitor connector health and respond to sync issues.

## Health Signals to Watch

- Connector availability status
- Sync recency/freshness indicators
- Field mapping validation errors
- Decision anomalies tied to connector-dependent attributes

## Routine Health Review

1. Check connector status on a regular cadence
2. Review stale or failed sync indicators
3. Verify critical attributes remain populated
4. Confirm no unexpected policy behavior shift

## Troubleshooting Workflow

1. Identify scope

- Single user/resource impact or broad impact?

1. Validate source availability

- Confirm upstream source system is reachable and healthy.

1. Validate mapping integrity

- Confirm critical fields are still mapped correctly.

1. Validate policy impact

- Re-test expected allow/deny scenarios using affected attributes.

1. Escalate

- Route to connector owner and security reviewer with timestamped findings.

## Recovery Validation

- Sync status returns to healthy
- Critical attributes repopulate as expected
- Affected policy outcomes match expected behavior

## Identity Connector GA Checks

Use these checks for Okta, Google IdP, and Auth0 when validating the shared identity runtime path.

1. Confirm runtime health

- `conn-identity /health` should return `status=healthy`.
- `conn-identity /ready` should return `ready=true` and list the configured provider set. For Google IdP, the runtime provider name is `google_workspace`.

1. Confirm workload identity wiring

- The `lattix-conn-identity` pod template should carry `azure.workload.identity/use=true`.
- The `lattix-conn-identity` service account should carry the expected `azure.workload.identity/client-id` annotation.
- Startup and readiness probes should target `/ready`, not `/health`, so missing provider resolution fails closed during rollout.

1. Confirm dashboard control-plane state

- `GET /api/settings/connectors` should show `connectorNamespace=identity` for `okta`, `google_idp`, and `auth0`.
- Connector status should show secrets present when tenant Key Vault refs were stored successfully.

1. Confirm manual sync behavior

- `POST /api/settings/connectors/sync` should return `ok=true`.
- `provider_auth_required` means the connector binding exists but required tenant Key Vault secrets are missing or unreadable.
- `connector_runtime_sync_failed` means the runtime request reached `conn-identity` but the provider binding could not be resolved or executed.

1. Run the smoke harness when available

- `prop-system-tests/tests/test_conn_identity_flow.py` validates runtime health/readiness, dashboard connector visibility, and manual sync behavior for `okta`, `google_idp`, and `auth0`.
- Required env vars: `LATTIX_CONN_IDENTITY_URL`, `MESH_DASHBOARD_URL`, `MESH_DASHBOARD_HOST`, and either `MESH_DASHBOARD_COOKIE` or `MESH_DASHBOARD_INTERNAL_TOKEN`.

## Storage Connector Checks

Use these checks for OneDrive, SharePoint, Google Drive, Box, and Dropbox when validating the current full file-source path.

1. Confirm dashboard control-plane state

- `GET /api/settings/connectors` should show `connectorNamespace=storage` for the configured file-source connector.
- Saved storage connectors should surface the connector-specific status summary and, when runtime is ready, a non-empty `statuses[*].runtime.capabilities` list.

1. Confirm auth and source scope

- OneDrive and SharePoint should retain the expected tenant-scoped OAuth binding plus any site, drive, or folder scoping.
- `GET /api/settings/connectors` should surface first-class Microsoft control-plane fields for saved bindings and jobs: discovery mode, OAuth plane, and optional permission-change reference.
- Scoped Microsoft flows should resolve to the discovery plane; enterprise/bootstrap flows should resolve to the bootstrap plane.
- `enterprise` discovery should fail closed without a permission-change reference.
- Google Drive, Box, and Dropbox should retain the expected access-token or refresh-token references in tenant Key Vault.
- A saved binding without usable upstream credentials should be treated as configured but not ready.

1. Confirm manual sync behavior

- `POST /api/settings/connectors/sync` should return `ok=true` when the sync request is recorded.
- `provider_auth_required` means the binding exists but the upstream credential material is missing or unreadable.
- `connector_runtime_sync_failed` means the request reached the control plane but shared-runtime execution was not queued or resolved cleanly.
- `platform_oauth_not_configured` means the shared Microsoft discovery/bootstrap app secrets are missing from platform Key Vault.
- `redirect_uri_unavailable` means neither the platform secret contract nor the request-origin fallback could resolve a callback URI.
- `bootstrap_discovery_requires_internal_approval` means a self-service caller attempted the internal-only bootstrap mode.

1. Confirm runtime capability shape

- Full file-source providers should advertise the storage capabilities needed for inventory, metadata, health checks, and CID-linked workflows.
- An explicit empty capability list means runtime not ready, not fully loaded.

## Governance and Mission Preview Checks

Use these checks for Purview, Fabric, Varonis, Palantir, and Anduril preview connectors.

1. Confirm preview posture

- Treat these connectors as preview registrations or workflow surfaces unless a tenant has completed real upstream validation.
- Do not describe them as equivalent to the OneDrive, SharePoint, Google Drive, Box, or Dropbox path.

1. Confirm workflow family

- Purview and Varonis are governance-workflow connectors. They can be configured and status-projected even when the shared storage runtime does not advertise generic file capabilities.
- Fabric and the mission-platform connectors should be treated as preview registrations until a tenant validates a real runtime workflow.

1. Confirm operator expectations

- Empty or missing generic runtime capabilities on a preview connector is a signal to use the preview or governance workflow, not to force a storage-style retry loop.

## Common Failure Patterns

- `/health` is healthy but `/ready` is missing expected providers: workload identity or provider bootstrap wiring is incomplete.
- `google_idp` appears broken while `google_workspace` appears healthy: treat this as an alias-normalization regression and verify dashboard, orchestrator, and runtime canonicalization together.
- Manual sync returns `provider_auth_required`: check tenant Key Vault secret names and connector binding metadata before retrying.
- Manual sync returns `connector_runtime_sync_failed`: inspect `conn-identity` logs for binding resolution failures, missing secrets, or provider-specific config validation errors.
- Microsoft connect start returns `platform_oauth_not_configured`: verify the eight shared Key Vault secret names under the `conn-microsoft-{discovery,bootstrap}-*` contract.
- Microsoft connect start returns `permission_change_reference_required`: the tenant selected enterprise discovery without the reviewed CAB/change-reference field.
- Microsoft callback fails with `invalid_state` after starting on `internal` and returning to `app`: verify the ingress host still sits under `*.lattix.io` so the shared OAuth cookies remain valid across subdomains.
- Connector status shows an explicit empty runtime capability list: treat this as runtime not ready, or as a preview connector that does not implement the full storage path yet.
- A preview connector is retried through a generic storage-style sync path: verify the connector family first, then use the governance or preview workflow instead of a file-ingest retry loop.

## What Not to Include in Tickets

- Secrets, tokens, private keys
- Unnecessary sensitive data payloads
