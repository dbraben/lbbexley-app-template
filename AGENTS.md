# {{SERVICE_NAME}}

Instructions for AI coding assistants working in this repository. Claude Code reads this file through `CLAUDE.md`; GitHub Copilot reads it directly.

This is a London Borough of Bexley service built on the Power Platform. The council's digital standards apply to everything here. In Claude Code they come from the lbbexley plugin; in Copilot from `.github/skills/lbbexley-*`, `.github/agents/lbbexley-*` and `.github/instructions/lbbexley-*`. Path rules in `.claude/rules/` and `.github/instructions/` load automatically for the files they cover.

## The service

| | |
|---|---|
| Service | {{SERVICE_NAME}} |
| What it does | {{SERVICE_SUMMARY}} |
| Users | {{AUDIENCE}} |
| Built with | {{BUILD_TYPES}} |
| Owner | {{SERVICE_OWNER}} |
| Solution | {{SOLUTION_NAME}} (publisher prefix `lbbexley`) |
| Dev environment | {{DEV_ENVIRONMENT_URL}} |
| Personal data | {{PERSONAL_DATA}} |
| AI features | {{AI_FEATURES}} |

## How work runs: plan, build, check

1. **Plan** on the strongest model. Claude Code starts in plan mode with `opusplan` (Opus plans, Sonnet builds); Copilot uses the lbbexley-plan agent. For a new service or a big change, use the requirements skill (a conversation in the chat, plus any cleaned material in `docs/discovery/`), then the architect skill. Use the plan skill for every feature, starting from its user story in `docs/requirements.md`. Plans go in `docs/plans/`.
2. **Build** on the everyday model, once the person approves the plan.
3. **Check** on a smaller model. Before you finish, the end-of-run check runs the standards check on everything you changed and asks the end-of-run reviewer (Haiku in Claude Code; lbbexley-check in Copilot) to look at the changes. Fix everything it finds. Its ideas for improving the harness go to `.lbbexley/improvements.md`.
4. **Save** the work once the check is clean, so the person never has to: commit what changed on the current branch, with a short message saying what changed, and tell them it's committed. In Claude Code, the end-of-run check asks for this when it passes; in Copilot, lbbexley-check offers **Commit the work**. Don't commit before the check, which reviews the uncommitted changes, and don't make branches, push or open pull requests unless the person asks.

## Always

1. Work only in the dev environment above, with fictional data (data-protection skill, `test-data.md`). Never ask for, read or write real resident or staff data.
2. Apply the Bexley skills for whatever you build: brand, accessibility and content-style, plus the skill for the platform. Apply publicity, data-protection, equality and ai-transparency whenever they're relevant.
3. Use the Bexley design tokens for every colour, font and size. Lato only.
4. Give every input, image and icon an accessible label that makes sense on its own. One H1 per screen or page. Visible focus on everything interactive. Targets at least 24 by 24.
5. Write everything users read in plain English.
6. Prefix every solution component and environment variable with `lbbexley`.
7. Keep source under `src/` and commit it, so every change is reviewed.
8. Add every page and screen to `tests/accessibility/targets.json`, and every agent topic to `tests/agent-test-set.md`, in the same change that builds it.
9. Zero findings of any severity is the definition of done. Never weaken a check, delete a test target or add a suppression without a written reason.

## Never

- Deploy, import solutions or upload sites to test or production. Pipelines do that.
- Run `pac solution import`, `pac solution delete`, `pac solution upgrade`, `pac pipeline deploy` or `pac admin` commands.
- Delete Dataverse tables, columns or records.
- Add analytics, tracking or advertising scripts, or load fonts from Google.
- Put personal data in prompts, code, test files, screenshots, commit messages or pull requests.
- Read an original meeting transcript, a recording or a `.roles.json` file, or run `npm run transcript:clean`. People clean transcripts themselves; you only read the cleaned copies in `docs/discovery/`, and stop if they still contain personal data.
- Edit the synced Bexley files (`.github/skills/lbbexley-*`, `.github/agents/lbbexley-*`, `.github/instructions/lbbexley-*`, `.claude/rules/lbbexley-*`, `.github/hooks/lbbexley.json`, `.lbbexley/standards/`). Propose changes to the standards instead (improve skill).

## Repository layout

| Folder | Contents |
|---|---|
| `src/` | Solution source: canvas apps (`.pa.yaml`), Power Pages site, agent (`.mcs.yml`), flows, Dataverse |
| `docs/discovery/` | What the person said at set-up (`service-introduction.md`), cleaned meeting transcripts and notes. Stays on each person's computer: Git ignores everything here except the README |
| `docs/requirements.md` | The requirements: users and their needs, user stories with acceptance criteria, rules, data, duties, open questions |
| `docs/architecture.md` | The service's design: users, components, data flow, duties, diagram |
| `docs/plans/` | One plan per change |
| `docs/compliance/` | Accessibility statement, DPIA screening, equality impact, publicity check, ATRS record, retention |
| `tests/accessibility/` | `targets.json`: every page and screen the accessibility tests open. The test code is synced into `.lbbexley/standards/` |
| `tests/` | Agent test set and the accessibility test log |
| `test-data/` | Fictional test data and the scripts that make it |
| `.lbbexley/` | Harness improvement ideas (`improvements.md`), the synced standards scripts and accessibility test runner, and local state |

## Quality checks

| Check | Command |
|---|---|
| Standards check on changed files (also runs on every save and before you finish) | `npm run check` |
| Standards check on everything | `npm run check:all` |
| Accessibility tests, WCAG 2.2 AA | `npm run test:a11y` |
| Save a sign-in for the accessibility tests | `npm run test:a11y:login` |
| Release check: compliance documents complete | `npm run check:release` |
| Review before a story is done, or before sharing the work | `/lbbexley:review` in Claude Code, `/lbbexley-review` in Copilot |
| Update to a new release of the standards | `npm run standards:update -- <version>` |
| Clean a Teams meeting transcript (people only, never the assistant) | `npm run transcript:clean -- <path to the transcript>` |
| Sign in to the dev environment | `pac auth create --environment {{DEV_ENVIRONMENT_URL}}` |

## Decisions and exceptions

Record each deliberate exception to the standards here, with the reason and who agreed it.

- None yet.
