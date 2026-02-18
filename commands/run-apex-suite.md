---
name: run-apex-suite
description: Execute Apex test suites or targeted classes, summarize failures, and suggest fixes.
---

# Run Apex Suite

Use this command to run tests before merge or deployment.

## Inputs

- `targetOrg`: org alias or username.
- `scope`: `all-local`, `suite`, or `classes`.
- `suiteName`: required when `scope=suite`.
- `classNames`: comma-separated classes when `scope=classes`.

## Execution

1. Verify org:
   - `sf org display --target-org <targetOrg>`
2. Run tests based on scope:
   - `all-local`:
     - `sf apex run test --target-org <targetOrg> --test-level RunLocalTests --result-format human --wait 30`
   - `suite`:
     - `sf apex run test --target-org <targetOrg> --suite-names <suiteName> --result-format human --wait 30`
   - `classes`:
     - `sf apex run test --target-org <targetOrg> --class-names <classNames> --result-format human --wait 30`
3. Summarize outcome:
   - Pass/fail counts.
   - Slowest tests.
   - Top assertion/exception failures.

## Output

- Execution summary table.
- Failing tests with probable root cause.
- Suggested remediation order.
