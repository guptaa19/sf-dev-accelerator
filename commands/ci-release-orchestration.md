---
name: ci-release-orchestration
description: Compose Salesforce CI/CD release flows including validate, test, deploy, and post-release verification steps.
---

# CI Release Orchestration

## Inputs

- `targetOrg`: alias/username.
- `releaseMode`: `validate-only`, `full-release`, `hotfix`.
- `manifestPath`: package xml path.
- `testLevel`: deployment test level.
- `tests`: optional specified test classes.

## Standard sequence

1. Pre-flight:
   - Confirm org and auth status.
   - Confirm metadata scope and risk.
2. Validate:
   - `sf project deploy validate --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`
3. Test:
   - Run focused or local Apex suites.
4. Deploy:
   - `sf project deploy start --manifest <manifestPath> --target-org <targetOrg> --test-level <testLevel>`
5. Post-release:
   - Smoke checks.
   - Log and user-impact review.

## Output

- Release readiness status.
- Gate pass/fail summary.
- Deployment evidence and next actions.
