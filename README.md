# Arbeidstilsynet/action-pnpm-setup

Opinionated action for fully setting up dependencies for a PNPM-based project. Installs chosen Node version, PNPM, audits dependencies and finally installs dependencies.

Configure `packageManager` in `package.json` to ensure the same version of PNPM is used in pipelines and locally. Use [Corepack](https://pnpm.io/installation#using-corepack) locally to always get the correct version of PNPM for your repo.

## Versioning

This repository uses a simple versioning system based on the `VERSION` file.
When you update the `VERSION` file and push to `main`, a Git tag with that version is created or updated automatically by the workflow.
If you have to make breaking changes to the action, bump the version.

## Requirements

PNPM version must be specified in `packageManager` in your `package.json`.

## Inputs

| Name           | Description            | Required | Default |
|----------------|------------------------|----------|---------|
| `node-version` | Node.js version to use | No       | 24.x    |

## Outputs

None

## Usage

```yaml
on:
  pull_request:

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v5

      - uses: Arbeidstilsynet/action-pnpm-setup@v1
        with:
          node-version: "24.x"
```
