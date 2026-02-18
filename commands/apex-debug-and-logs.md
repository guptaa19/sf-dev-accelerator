---
name: apex-debug-and-logs
description: Run anonymous Apex, capture logs, and diagnose Apex runtime failures quickly.
---

# Apex Debug and Logs

## Inputs

- `targetOrg`: alias/username.
- `operation`: `run-anon`, `set-trace`, `get-logs`, `analyze-failure`.
- `apexFile`: path for anonymous Apex script.
- `userName`: user for trace flag settings.

## Execution patterns

- Run anonymous Apex:
  - `sf apex run --file <apexFile> --target-org <targetOrg>`
- Set trace flags:
  - Use debug tooling flow for target user and duration.
- Get logs:
  - `sf apex log list --target-org <targetOrg>`
  - `sf apex log get --log-id <logId> --target-org <targetOrg>`
- Analyze failure:
  - Parse exception type, line numbers, governor-limit context, and call sequence.

## Output

- Runtime result and log references.
- Root-cause hypothesis.
- Recommended fixes and verification steps.
