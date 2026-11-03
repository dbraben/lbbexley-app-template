@AGENTS.md

## Claude Code

- The lbbexley plugin provides the Bexley skills, reviewers and guardrails. If you didn't get the "Bexley standards are active" reminder at the start of this session, the plugin isn't running: ask the person to check `/plugin`.
- The skills' supporting files (screen patterns, tokens, templates) are also synced into this repository under `.github/skills/lbbexley-*/`. Read them there if you can't read the plugin's folder.
- This project uses `opusplan` and starts in plan mode: Opus plans, and approving the plan switches to Sonnet to build. The requirements, architect and plan skills also run on Opus. The end-of-run reviewer runs on Haiku. In the VS Code extension, set `claudeCode.initialPermissionMode` to `plan` in your user settings if sessions don't start in plan mode.
- Plans are saved in `docs/plans/` (the `plansDirectory` setting).
- Use Microsoft's plugins for authoring: canvas-apps (with the canvas authoring MCP server), power-pages and model-apps. `/lbbexley:new-app` turns on the ones this service needs.
- Check current Microsoft documentation with the Microsoft Learn MCP server rather than relying on memory.
- When the standards check reports problems after a save, fix them before moving on. When the stop gate asks for the end-of-run check, run the `lbbexley:end-of-run-reviewer` agent and fix everything it reports.
