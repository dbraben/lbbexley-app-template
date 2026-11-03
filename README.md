> [!NOTE]
> **This is the Bexley app template.** Don't work in it or change it. Select **Use this template** to create your own repository for your service, in your own account, then run `/lbbexley:new-app` in Claude Code, or ask GitHub Copilot to use the lbbexley-new-app skill. That fills in this README and removes this note. The [harness README](https://github.com/dbraben/lbbexley-digital-standards#readme) explains the rest.

<img src=".github/skills/lbbexley-brand/assets/bexley-logo.png" alt="London Borough of Bexley" width="240">

# {{SERVICE_NAME}}

{{SERVICE_SUMMARY}}

A London Borough of Bexley service built on the Power Platform to the council's digital standards.

## New repository from this template?

1. Open the folder in VS Code and start Claude Code. Trust the folder, and accept the offer to add the Bexley and Microsoft plugin marketplaces.
2. Run `/lbbexley:new-app` and answer the questions. (In GitHub Copilot, ask it to use the lbbexley-new-app skill.)
3. Capture the requirements in `docs/discovery/`: a Teams meeting transcript cleaned with `npm run transcript:clean`, your own requirement prompt, or both. [docs/discovery/README.md](docs/discovery/README.md) says how.
4. Run `/lbbexley:requirements`, ask the service owner to check `docs/requirements.md`, then design the service with `/lbbexley:architect`. (In Copilot, use the lbbexley-requirements and lbbexley-architect skills with the lbbexley-plan agent.)
5. Follow the onboarding guide in the **lbbexley-digital-standards** repository (`docs/onboarding.md`).

## Working on this service

- Read `AGENTS.md`: the service details, how work runs and the rules that always apply.
- Plan, build, check: start each change in plan mode (Claude Code) or with the lbbexley-plan agent (Copilot). The end-of-run check runs before the assistant can finish.
- Build in the dev environment with fictional data only.
- Run `npm run verify` and `/lbbexley:review` (Copilot: `/lbbexley-review`) before opening a pull request. Every pull request runs the Bexley standards check and, once set up, the accessibility tests.
- Keep the documents in `docs/compliance/` up to date as the service changes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full workflow.

## Contact

Owner: {{SERVICE_OWNER}}. For the Bexley standards, see the standards repository's [SUPPORT.md](https://github.com/dbraben/lbbexley-digital-standards/blob/main/SUPPORT.md).
