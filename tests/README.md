# Tests

Record what was tested, how, when and by whom, so the accessibility statement and reviews are based on evidence.

- `accessibility/targets.json`: every page and screen the accessibility tests open (`npm run test:a11y`). The tests fail on any WCAG 2.2 A or AA violation, sideways scrolling at 320 pixels, or a tab stop without visible focus. The test code itself comes from the Bexley standards, in `.lbbexley/standards/tests/accessibility/`, and updates with each release.
- `accessibility-test-log.md`: keyboard, screen reader, zoom and user testing for each release
- `agent-test-set.md`: questions an agent must handle well, run after every change to the agent (only for services with a Copilot Studio agent)

Automated tests find many problems, but not all. They don't replace testing by people, including people who use assistive technology.
