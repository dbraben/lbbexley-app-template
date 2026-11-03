# Contributing

How changes to this service are made. The same steps apply whether you use Claude Code, GitHub Copilot or neither.

## 1. Start from the requirements and an issue

A new service, or a big change, starts with requirements: what the people who run and use it said, in a cleaned meeting transcript or a requirement prompt in `docs/discovery/`, turned into `docs/requirements.md` by the requirements skill and checked by the service owner. [docs/discovery/README.md](docs/discovery/README.md) says how.

Every change then starts as an issue: a feature (one user story, with its acceptance criteria), a bug, or an accessibility problem. Accessibility problems come first. Never put personal data in an issue.

## 2. Plan

Write a plan in `docs/plans/` before building, using the plan skill's template. In Claude Code, sessions start in plan mode on Opus; in Copilot, use the lbbexley-plan agent. The plan includes the real words users will read and acceptance criteria someone can check. Someone approves it before building starts.

## 3. Build

On a branch, in the dev environment, with fictional data only. Follow `AGENTS.md` and the Bexley skills. Add each new page or screen to `tests/accessibility/targets.json` and each agent topic to `tests/agent-test-set.md` as you build them.

## 4. Check

- The standards check runs after every save, and the end-of-run check (standards check plus a review on a smaller model) runs before the assistant can finish.
- Run `npm run verify`: the standards check on everything, and the accessibility tests.
- Run `/lbbexley:review` (Copilot: `/lbbexley-review`) and fix everything it lists.
- Test by hand: keyboard only, a screen reader, 400% zoom and a phone. Record it in `tests/accessibility-test-log.md`.

Zero findings of any severity is the definition of done.

## 5. Pull request

Use the pull request template. The Quality workflow must pass, and a colleague reviews the change. Update `docs/compliance/` in the same pull request if the service changed.

## Improving the harness

The end-of-run check logs ideas for improving the Bexley standards in `.lbbexley/improvements.md`. Work through them with `/lbbexley:improve`: ideas for this service are applied here, and ideas for the standards become proposals for the Digital Team. Don't edit the synced Bexley files by hand: update them with `npm run standards:update -- <version>`.
