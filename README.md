# ddev-playwright

[![tests](https://github.com/codingsasi/ddev-playwright/actions/workflows/tests.yml/badge.svg)](https://github.com/codingsasi/ddev-playwright/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2025.svg)

This is a DDEV addon that provides a Playwright testing environment for your DDEV projects.

## Installation

```bash
ddev add-on get codingsasi/ddev-playwright
ddev restart
```

## Configuration

After installation, you'll need to set up Playwright in your project if you haven't already:

```bash
# Install Playwright dependencies and browsers in your project.
ddev playwright install-deps
ddev playwright install

```

## Usage

You can run Playwright commands directly using the `ddev playwright` command:

```bash
# Run Playwright tests
ddev playwright test

# Show Playwright help
ddev playwright --help
```

## Accessing the Web Application from Tests

Your tests can access the web application using the hostname `web` or the DDEV_PRIMARY_URL environment variable:

```javascript
// Example test
import { test, expect } from '@playwright/test';

test('basic test', async ({ page }) => {
  // Using the DDEV_PRIMARY_URL environment variable
  await page.goto(process.env.DDEV_PRIMARY_URL || 'http://web');

  // Rest of your test...
});
```

## Customizing

You can customize the Playwright configuration by editing the `playwright.config.ts` or `playwright.config.js` file in your project.

## Contributing

Feel free to submit issues or pull requests with improvements.

**Contributed and maintained by [Abhai Sasidharan/codingsasi]**
