# Copilot instructions

Follow `AGENTS.md` in the repository root. It has the service details, how work runs (plan, build, check) and the rules that always apply.

The London Borough of Bexley standards come in four parts, all synced from the standards repository:

- skills in `.github/skills/lbbexley-*`: brand, accessibility, content style, publicity, data protection, equality, AI transparency, one skill for each platform, and the requirements, architect, plan, quality-checks, review and improve skills
- agents in `.github/agents/`: lbbexley-plan (strongest model), lbbexley-build (everyday model) and lbbexley-check (smaller model), which hand over to each other, plus read-only reviewers
- path instructions in `.github/instructions/lbbexley-*`, which apply automatically to the files they cover
- hooks in `.github/hooks/lbbexley.json` (preview), which run the standards check after each edit and hold the agent back until everything it changed passes

Start a new service with the lbbexley-plan agent and the lbbexley-requirements skill, from the cleaned material in `docs/discovery/`, and every change with the lbbexley-plan agent. Never read an original meeting transcript, a recording or a `.roles.json` file, and never run `npm run transcript:clean`: people clean transcripts themselves. If the hooks aren't running in your setup, run `npm run check` after each change and hand over to lbbexley-check before you finish: zero findings of any severity is the definition of done. Never ask for, read or write real personal data; use the formats in `.github/skills/lbbexley-data-protection/test-data.md`. When VS Code asks to run a Dataverse MCP tool, it must be against the dev environment, and never approve a delete.
