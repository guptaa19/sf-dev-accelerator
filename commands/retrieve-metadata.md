---
name: retrieve-metadata
description: Retrieve metadata from a target org for comparison, debugging, or source alignment.
---

# Retrieve Metadata

Use this command when local source and org state may be out of sync.

## Inputs

- `targetOrg`: org alias or username.
- `manifestPath`: package manifest path (recommended).
- `metadata`: metadata selector string when no manifest is provided.

## Execution

1. Validate target org:
   - `sf org display --target-org <targetOrg>`
2. Retrieve metadata:
   - Manifest flow:
     - `sf project retrieve start --manifest <manifestPath> --target-org <targetOrg>`
   - Metadata selector flow:
     - `sf project retrieve start --metadata <metadata> --target-org <targetOrg>`
3. Summarize changed local files and next validation/deploy steps.

## Output

- Retrieved metadata summary.
- Local file change summary.
- Suggested next action (diff review, test run, deploy validate).
