---
description: 'Bexley rules for tests and test data'
applyTo: 'tests/**,test-data/**'
---
<!-- Generated from lbbexley-digital-standards 0.6.1 by scripts/sync-app.js. Don't edit here: change the standards repository and sync again. -->

# Tests and test data

- Fictional data only, in the safe formats from the data-protection skill (`test-data.md`).
- Accessibility tests must pass with zero axe violations of any impact. Never remove a target, skip a check or loosen a tag list to make a test pass: fix the page or screen.
- Saved sign-ins (`.auth/`) are secrets: never commit them.
- Every page, screen and agent topic people use has a test target or test question.
