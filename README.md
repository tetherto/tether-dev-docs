# tether-dev-docs

Shared development configuration for the Tether/PearPass ecosystem.

## Overview

This package exports a shared ESLint configuration used across all PearPass and Tether repositories to enforce consistent code style. It bundles opinionated defaults for JavaScript, JSX, and TypeScript projects.

## Table of Contents

- [Security Notice](#security-notice)
- [Installation](#installation)
- [What's Included](#whats-included)
- [Usage](#usage)
- [Dependencies](#dependencies)

## Security Notice

1. To ensure the security and integrity of your projects, please note that official PearPass packages are distributed exclusively through our GitHub organization.
2. Any packages with similar names found on the npm registry or other third-party package managers are not affiliated with PearPass and should be strictly avoided. We recommend installing directly from this repository to ensure you are using the verified, open-source version.

## Installation

```bash
npm install git+https://github.com/tetherto/tether-dev-docs.git
```

## What's Included

### ESLint configuration (`eslintConfig`)

A flat ESLint config array covering:

- **Prettier integration** — enforces formatting via `eslint-plugin-prettier` with the project's standard Prettier options (no semicolons, single quotes, 2-space indent, trailing commas off).
- **Import ordering** — `eslint-plugin-import` with groups: `builtin → external → internal → parent/sibling/index → object → type`, alphabetically sorted, blank lines between groups, `react` pinned before other externals.
- **React** — `eslint-plugin-react` with `jsx-uses-vars` to prevent false "unused variable" errors on JSX identifiers.
- **Arrow functions** — enforces concise bodies (`arrow-body-style: as-needed`).
- **TypeScript** (optional) — if `@typescript-eslint/parser` and `@typescript-eslint/eslint-plugin` are installed in the consuming project, the config automatically adds a `*.{ts,tsx}` override that disables `no-undef`/`no-unused-vars` in favour of their typed equivalents.
- **Globals** — `browser`, `node`, and `jest` globals pre-configured, plus `Pear` as a read-only global for Pear runtime projects.

## Usage

### Use as the sole ESLint config

```js
// eslint.config.js
import { eslintConfig } from '@tetherto/tether-dev-docs';

export default eslintConfig;
```

### Extend with custom rules

```js
// eslint.config.js
import { eslintConfig } from '@tetherto/tether-dev-docs';

export default [
  ...eslintConfig,
  {
    rules: {
      // project-specific overrides
    }
  }
];
```

### TypeScript support

Install the TypeScript ESLint packages in your project and the config will pick them up automatically:

```bash
npm install --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

## Dependencies

- Node.js v22.12.0 or later
- `eslint-config-prettier`
- `eslint-plugin-eslint-plugin`
- `eslint-plugin-import`
- `eslint-plugin-prettier`
- `eslint-plugin-react`
- `globals`

TypeScript support (`@typescript-eslint/parser`, `@typescript-eslint/eslint-plugin`) is optional — loaded from the consumer's `node_modules` at runtime.

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](./LICENSE) file for details.