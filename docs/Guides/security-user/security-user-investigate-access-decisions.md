---
title: 'Security User: Investigate Access Decisions'
deprecated: false
hidden: false
metadata:
  robots: index
---
Use this runbook when access outcomes appear incorrect or risky.

## Investigation Workflow

1. Define the question
- Was this decision expected based on current policy and context?

2. Collect decision context
- User role/attributes, resource scope, action type, decision time, and policy version.

3. Validate policy path
- Identify which rule set allowed/denied the action.
- Check for exception or override involvement.

4. Check upstream context quality
- Validate required attributes were present and current.
- Check for connector/ICAM sync issues.

5. Determine outcome
- Expected behavior
- Policy defect
- Data quality defect
- Operational misconfiguration

## Response Guidance

- For policy defects: route to Tenant Admin for controlled change.
- For data quality defects: escalate to ICAM/connector owners.
- For active high-risk exposure: trigger incident process per your security policy.

## Documentation Standards

- Record facts, not assumptions
- Include timestamps and policy version context
- Exclude secrets and unnecessary personal data
