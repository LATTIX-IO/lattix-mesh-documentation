---
title: Deny by Default and Exception Design
deprecated: false
hidden: false
metadata:
  robots: index
---
High-trust systems begin with deny-by-default and add narrowly scoped exceptions.

## Why This Pattern Works

- Limits accidental overexposure
- Forces explicit reasoning for access
- Creates cleaner audit narratives

## Exception Design Rules

- Time-bound every exception
- Tie exception to a named business justification
- Require owner and review date
- Remove exception automatically when criteria expire

## Anti-Patterns

- Permanent emergency exceptions
- Exceptions that bypass all policy layers
- Exception logic copied across many policies without ownership
