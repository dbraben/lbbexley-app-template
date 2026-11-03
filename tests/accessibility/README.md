# Accessibility tests

`targets.json` lists every page and screen the accessibility tests open. Add each one in the same change that builds it: the `about` line in the file explains each field, and `examples` shows a Power Pages page, a canvas app screen and a model-driven form.

| Command | What it does |
|---|---|
| `npm run test:a11y` | Runs the tests: zero axe violations at WCAG 2.2 A and AA, and for Power Pages, reflow at 320 pixels and visible focus |
| `npm run test:a11y:login` | Signs in once with a test account and saves the session in `.auth/` for targets with `"auth": true`. The saved file is a secret and is never committed |
| `npm run test:a11y:install` | Installs the browser the tests use, once per machine |

The test code comes from the Bexley standards and lives in `.lbbexley/standards/tests/accessibility/`. Don't edit it here: `npm run standards:update -- <version>` replaces it with each release. To change how the tests work, propose it to the Digital Team (`/lbbexley:improve`).
