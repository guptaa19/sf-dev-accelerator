---
name: metadata-lifecycle
description: Run complete metadata lifecycle workflows including retrieve, validate, deploy, and destructive change handling.
---

# Metadata Lifecycle

## Inputs

- `targetOrg`: alias/username.
- `operation`: `retrieve`, `validate`, `deploy`, `quick-deploy`, `destructive`.
- `manifestPath`: package xml path.
- `sourceDir`: optional source directory fallback.
- `testLevel`: `RunLocalTests`, `RunSpecifiedTests`, `NoTestRun`.
- `tests`: class names for specified tests.

## Execution patterns

- Retrieve:
  - `sf project retrieve start --manifest <manifestPath> --target-org <targetOrg>`
- Validate:
  - `sf project deploy validate --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`
- Deploy:
  - `sf project deploy start --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`
- Quick deploy:
  - `sf project deploy quick --job-id <validatedJobId> --target-org <targetOrg>`
- Destructive changes:
  - Require explicit confirmation.
  - Execute only with approved destructive manifest strategy.

## Output

- Deployment/retrieval IDs.
- Component success/failure summary.
- Failure diagnostics and retry plan.
