# Contributing

How changes to this service are made. The same steps apply whether you use Claude Code, GitHub Copilot or neither.

## 1. Start from the requirements

A new service, or a big change, starts with requirements: what the people who run and use it said, in a conversation with the requirements skill and any cleaned meeting transcripts in `docs/discovery/`, written up in `docs/requirements.md` and checked by the service owner. [docs/discovery/README.md](docs/discovery/README.md) says how.

Each change is then one user story from the requirements, a bug or an accessibility problem. Accessibility problems come first. If your team tracks work in GitHub issues, raise one for each, and never put personal data in an issue.

## 2. Plan

Write a plan in `docs/plans/` before building, using the plan skill's template. In Claude Code, sessions start in plan mode on Opus; in Copilot, use the lbbexley-plan agent. The plan includes the real words users will read and acceptance criteria someone can check. Someone approves it before building starts.

## 3. Build

In the dev environment, with fictional data only: the assistant builds there directly with Microsoft's tools, and nobody edits the service's source in this repository by hand. Follow `AGENTS.md` and the Bexley skills. Add each new page or screen to `tests/accessibility/targets.json` and each agent topic to `tests/agent-test-set.md` as you build them.

After any change in the dev environment, the latest version comes into the repository with `pac solution sync`, and each canvas app's source through Microsoft's canvas tools. When you change something yourself, in Power Apps Studio or the flow designer, ask the assistant to sync (`/lbbexley:sync`).

## 4. Check

- The standards check runs after every save, and the end-of-run check (standards check plus a review on a smaller model) runs before the assistant can finish.
- Run `npm run verify`: the standards check on everything, and the accessibility tests.
- Run `/lbbexley:review` (Copilot: `/lbbexley-review`) and fix everything it lists.
- Test by hand: keyboard only, a screen reader, 400% zoom and a phone. Record it in `tests/accessibility-test-log.md`.

Zero findings of any severity is the definition of done.

## 5. Save and share

- **Saving and sharing.** The assistant commits the latest version once the end-of-run check is clean, on the branch you're on, and pushes it to GitHub, so nobody has to run Git: in Claude Code the check asks it to, and in Copilot lbbexley-check offers **Commit the work**. The Quality workflow checks it on GitHub too, whichever assistant made the change, or none.
- **Working in a team?** Agree a branch each, or protect `main` and use pull requests: with `main` protected, the assistant's push to it fails, and it says so. The Quality workflow must pass, and a colleague reviews the change.

Update `docs/compliance/` in the same change if the service changed.

## Improving the harness

The end-of-run check logs ideas for improving the Bexley standards in `.lbbexley/improvements.md`. Work through them with `/lbbexley:improve`: ideas for this service are applied here, and ideas for the standards become proposals for the Digital Team. Don't edit the synced Bexley files by hand: update them with `npm run standards:update -- <version>`.
