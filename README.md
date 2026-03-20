# tether-dev-docs

Documentations and guides for developers

## Overview

This documentation is designed to help developers integrate with Tether's services, understand API endpoints, and implement Tether functionality in their applications.

## Table of Contents

- [Security Notice](#security-notice)
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Usage](#usage)

## Security Notice

1. To ensure the security and integrity of your projects, please note that official PearPass packages are distributed exclusively through our GitHub organization.
2. Any packages with similar names found on the npm registry or other third-party package managers are not affiliated with PearPass and should be strictly avoided. We recommend installing directly from this repository to ensure you are using the verified, open-source version.

## Installation

```bash
npm install git+https://github.com/tetherto/tether-dev-docs.git
```

## Dependencies

This package requires the following dependencies:
- Node.js v22.12.0 or later

## Usage

```js
import { eslintConfig } from '@tetherto/tether-dev-docs';

// Use the exported ESLint configuration
export default eslintConfig;
```

You can also extend the configuration in your own ESLint setup:

```js
import { eslintConfig } from '@tetherto/tether-dev-docs';

export default [
    ...eslintConfig,
    {
        // Your custom rules
    }
];
```

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](./LICENSE) file for details.