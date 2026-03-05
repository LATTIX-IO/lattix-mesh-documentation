---
title: Policy Testing Strategies for High-Risk Data
deprecated: false
hidden: false
metadata:
  robots: index
---
High-risk data requires stricter testing before policy promotion.

## Minimum Test Matrix

- Expected allow (normal case)
- Expected deny (least privilege case)
- Missing attribute case
- Stale attribute case
- Exception-path case

## Promotion Strategy

- Test in controlled pilot scope
- Compare outcomes against baseline expectations
- Require security sign-off for high-impact changes

## Signals to Watch

- Sudden drop in denies
- Unexpected allow spikes
- Increased manual override requests
