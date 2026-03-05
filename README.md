# Lattix Mesh Documentation

Public-facing documentation for the Lattix SaaS platform.

This repository contains customer documentation focused on:

- Tenant Admin workflows
- Security User workflows
- Passport and Data Room usage
- Core zero trust, data-centric security concepts
- Operational guidance for compliance, connectors, and troubleshooting

## Scope

This docs set is intentionally scoped to current SaaS MVP capabilities.

It does not include:

- Internal implementation secrets
- Proprietary architecture detail not required by customers
- Credentials, tokens, keys, or sensitive operational data

## Repository Structure

- `docs/`: Main documentation content and navigation order files
- `reference/`: Supplementary reference content (ReadMe config/help pages)

Category structure under `docs/`:

- `Getting Started`
- `Core Concepts`
- `Guides`
- `Authentication & Security`
- `Compliance`
- `Connectors`
- `Troubleshooting`
- `Release Notes`
- `Support & FAQ`

## Authoring Rules

When adding or editing content:

1. Keep it user-facing and action-oriented.
2. Prefer role-based guidance (Tenant Admin, Security User, Passport User, Data Room User).
3. Avoid exposing internal-sensitive implementation details.
4. Include checklists, validation steps, and common failure modes where useful.
5. Update `_order.yaml` files when adding new pages.

## Contribution Workflow

1. Create a branch from `main`.
2. Add/update docs pages in `docs/` or `reference/`.
3. Verify navigation order in `_order.yaml`.
4. Open a pull request with:
- Summary of changes
- Target audience impacted
- Any migration/deprecation notes (if applicable)

## Release Notes and Change Tracking

Use:

- `docs/Release Notes/release-notes.md` for user-facing release summaries
- `docs/Release Notes/changelog.md` for chronological change history
- `docs/Release Notes/deprecations.md` for planned removals and migration guidance

## Support

For support process details, see:

- `docs/Support & FAQ/contact-support.md`
- `docs/Support & FAQ/escalation-sla.md`

