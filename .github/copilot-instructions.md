# Copilot instructions

Follow `AGENTS.md` in the repository root. It has the service details, how work runs (plan, build in the dev environment, check) and the rules that always apply.

The London Borough of Bexley standards come in four parts, all synced from the standards repository:

- skills in `.github/skills/lbbexley-*`: brand, accessibility, content style, publicity, data protection, equality, AI transparency, one skill for each platform, and the requirements, architect, plan, quality-checks, review, improve and sync skills
- agents in `.github/agents/`: lbbexley-plan (strongest model), lbbexley-build (everyday model) and lbbexley-check (smaller model), which hand over to each other, plus read-only reviewers
- path instructions in `.github/instructions/lbbexley-*`, which apply automatically to the files they cover
- hooks in `.github/hooks/lbbexley.json` (preview), which keep the agent to the dev environment, run the standards check after each edit, and hold the agent back until the latest version is in the repository and everything it changed passes

Everything is built in the dev environment named in `AGENTS.md`, with Microsoft's tools, never as files on their own. This repository holds the guidelines and the latest version of the service: after a change in the dev environment, add any new flow or table to the solution (`pac solution add-solution-component`), then run `pac solution sync` in the solution's project folder under `src/solution`. Nobody edits the synced files by hand.

Start a new service with the lbbexley-plan agent and the lbbexley-requirements skill, which asks about the service in the chat, and every change with the lbbexley-plan agent. Build with lbbexley-build, then hand over to lbbexley-check; when it finds nothing outstanding, **Commit the work** commits the latest version and pushes it to GitHub, so the person never runs Git. Never force-push, and never make a branch or open a pull request unless the person asks.

Never read an original meeting transcript, a recording or a `.roles.json` file, and never run `npm run transcript:clean`: people clean transcripts themselves. If the hooks aren't running in your setup, run `npm run check` after each change and hand over to lbbexley-check before you finish: zero findings of any severity is the definition of done. Never ask for, read or write real personal data; use the formats in `.github/skills/lbbexley-data-protection/test-data.md`. When VS Code asks to run a Dataverse, canvas or Power Automate tool, or a `pac` command, it must be against the dev environment; never approve a delete, and never run a flow or call a connector with real recipients.
