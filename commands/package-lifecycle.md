---
name: package-lifecycle
description: Manage second-generation package creation, versioning, installation, and promotion workflows.
---

# Package Lifecycle

## Inputs

- `targetOrg`: Dev Hub or install org alias.
- `operation`: `create-package`, `create-version`, `install`, `promote`, `list`.
- `packageName`: package identifier.
- `versionId`: package version id where required.
- `installationKey`: optional package install key.

## Execution patterns

- Create package:
  - `sf package create --name <packageName> --package-type Unlocked --target-dev-hub <targetOrg>`
- Create version:
  - `sf package version create --package <packageName> --target-dev-hub <targetOrg> --wait 30`
- Install:
  - `sf package install --package <versionId> --target-org <targetOrg> --wait 30`
- Promote:
  - `sf package version promote --package <versionId> --target-dev-hub <targetOrg> --no-prompt`
- List:
  - `sf package list --target-dev-hub <targetOrg>`
  - `sf package version list --target-dev-hub <targetOrg>`

## Output

- Package/package-version summary.
- Compatibility and dependency notes.
- Promotion/rollback guidance.
