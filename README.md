# Arbeidstilsynet/action-pnpm-setup

Opinionated action for fully setting up dependencies for a pnpm-based project. Installs the chosen Node.js version and pnpm, optionally audits dependencies, and finally installs dependencies.

Configure `packageManager` in `package.json` to ensure the same version of PNPM is used in pipelines and locally. Use [Corepack](https://pnpm.io/installation#using-corepack) locally to always get the correct version of PNPM for your repo.

> [!NOTE]
> For repositories using pnpm 11 or newer, use [pnpm/setup](https://github.com/pnpm/setup) instead.

## Requirements

PNPM version must be specified in `packageManager` in your `package.json`.

## Inputs

| Name                | Description                                                  | Required | Default  |
|---------------------|--------------------------------------------------------------|----------|----------|
| `node-version`      | Node.js version to use                                       | No       | `26.x`   |
| `working-directory` | Working directory containing package.json and pnpm-lock.yaml | No       | `.`      |
| `skip-install`      | Skip pnpm install step                                       | No       | `false`  |
| `skip-audit`        | Skip pnpm audit step                                         | No       | `true`   |

Auditing is disabled by default. Set `skip-audit: false` to run `pnpm audit`.

## Outputs

None

## Usage

### Minimal

```yaml
on:
  pull_request:

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - uses: Arbeidstilsynet/action-pnpm-setup@v3
```

### With all optional inputs

```yaml
on:
  pull_request:

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - uses: Arbeidstilsynet/action-pnpm-setup@v3
        with:
          node-version: "26.x"
          working-directory: "some/path"
          skip-install: false
          skip-audit: false
```

## Versioning

This repository uses a simple versioning system based on the `VERSION` file.
When you update the `VERSION` file and push to `main`, a Git tag with that version is created or updated automatically by the workflow.
If you make breaking changes to the action, bump the version and update `CHANGELOG.md`.
