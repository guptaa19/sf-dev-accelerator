---
name: data-operations
description: Execute Salesforce data operations including query, import, export, and record updates with safety checks.
---

# Data Operations

## Inputs

- `targetOrg`: alias/username.
- `operation`: `query`, `import`, `export`, `upsert`, `delete`.
- `soql`: query for read operations.
- `filePath`: csv/json path for import/export operations.
- `sobject`: object API name for upsert/delete workflows.

## Execution patterns

- Query:
  - `sf data query --query "<soql>" --target-org <targetOrg> --result-format table`
- Import:
  - `sf data import tree --files <filePath> --target-org <targetOrg>`
- Export:
  - `sf data export tree --query "<soql>" --output-dir <filePath> --target-org <targetOrg>`
- Upsert/delete:
  - Use `sf data` commands based on object and input file.
  - Require confirmation for destructive or large-volume operations.

## Output

- Rows affected.
- Data quality warnings.
- Rollback/recovery recommendation for destructive operations.
