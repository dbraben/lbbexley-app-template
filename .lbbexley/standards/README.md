# Bexley standards scripts

<!-- Generated from lbbexley-digital-standards 0.6.0 by scripts/sync-app.js. Don't edit here: change the standards repository and sync again. -->

Version 0.6.0. Copied here so `npm run check`, the accessibility tests, the Copilot hooks and the pull request check all use the same release of the Bexley standards as the Claude Code plugin:

- `scripts/` and `config/`: the standards check and the hook scripts
- `tests/accessibility/`: the accessibility test runner (Playwright and axe). The pages and screens it tests are in `tests/accessibility/targets.json` at the root of this repository, which is yours to edit.

Update them with `npm run standards:update -- <version>`, never by hand.
