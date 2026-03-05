---
title: Data Room Concepts and Collaboration Boundaries
deprecated: false
hidden: false
metadata:
  robots: index
---
Data rooms enable collaboration in a controlled environment where access, sharing, and actions are bounded by policy.

## Data Room Core Concepts

- **Bounded collaboration**: actions are limited to approved participants and scope
- **Policy-governed sharing**: access conditions apply to room activity
- **Operational transparency**: actions can be reviewed and audited

## Boundary Types

- Participant boundary: who can join or act
- Data boundary: what can be viewed, shared, or exported
- Action boundary: what operations are permitted
- Time boundary: when access begins/ends

## Practical Design Guidance

- Start narrow for participant scope
- Separate read vs share vs export permissions
- Use short-lived access windows for sensitive activity
- Review membership and permissions on a defined cadence

## Common Failure Mode

Teams create data rooms with broad standing permissions and no periodic review. Treat data rooms as governed workflows, not static shared folders.
