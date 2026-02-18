---
name: source-tracking
description: Handle source tracking workflows for scratch org development and conflict resolution.
---

# Source Tracking

## Inputs

- `targetOrg`: scratch org alias.
- `operation`: `status`, `push`, `pull`, `reset`, `conflicts`.

## Execution patterns

- Status:
  - `sf project deploy preview --target-org <targetOrg>`
  - `sf project retrieve preview --target-org <targetOrg>`
- Push:
  - `sf project deploy start --source-dir force-app --target-org <targetOrg>`
- Pull:
  - `sf project retrieve start --source-dir force-app --target-org <targetOrg>`
- Conflict review:
  - Run deploy/retrieve preview and summarize changed artifacts.
- Tracking reset (when needed):
  - `sf project reset tracking --target-org <targetOrg> --no-prompt`

## Output

- Local-vs-org delta summary.
- Conflicts and recommended conflict-resolution order.
