---
name: deploy-validate
description: Validate Salesforce metadata deployment with local tests before production deployment.
---

# Deploy Validate

Use this command when a change should be verified safely before a real deployment.

## Inputs

- `targetOrg`: org alias or username.
- `manifestPath`: package manifest path (optional if deploying by source dir).
- `testLevel`: `RunLocalTests` (default), `RunSpecifiedTests`, or `NoTestRun` (non-prod only).
- `tests`: comma-separated test class names when `RunSpecifiedTests` is selected.

## Execution

1. Confirm target org:
   - `sf org display --target-org <targetOrg>`
2. Validate deployment (check-only):
   - Manifest flow:
     - `sf project deploy validate --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`
   - Source-dir flow:
     - `sf project deploy validate --source-dir force-app --target-org <targetOrg> --test-level <testLevel>`
3. If validation succeeds and user approves, run real deployment:
   - `sf project deploy start --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`

## Output

- Deployment ID.
- Validation status and failing components/tests (if any).
- Next action recommendation (fix and retry, or proceed to deploy).
