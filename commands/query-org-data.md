---
name: query-org-data
description: Run SOQL queries safely with clear limits and summarize records for debugging or analysis.
---

# Query Org Data

Use this command for data investigation without changing data.

## Inputs

- `targetOrg`: org alias or username.
- `soql`: query string.
- `resultFormat`: `table` (default), `json`, or `csv`.

## Execution

1. Validate query safety:
   - Ensure selected fields are needed.
   - Prefer explicit `LIMIT` for exploratory queries.
2. Execute query:
   - `sf data query --query "<soql>" --target-org <targetOrg> --result-format <resultFormat>`
3. For large result sets, propose filtering or pagination approach.

## Output

- Row count and key highlights.
- Any query anti-patterns detected (missing selectivity, missing limit in ad-hoc query).
- Follow-up query suggestions.
