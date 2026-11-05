> [!NOTE]
> **This is the Bexley app template.** Don't work in it or change it. To create your own repository for your service, in your own account, sign in to GitHub and select **Use this template** at the top right of this page, beside **Star**. Then run `/lbbexley:new-app` in Claude Code, or ask GitHub Copilot to use the lbbexley-new-app skill. That fills in this README and removes this note. The [harness README](https://github.com/dbraben/lbbexley-digital-standards#readme) explains the rest.

<img src=".github/skills/lbbexley-brand/assets/bexley-logo.png" alt="London Borough of Bexley" width="240">

# {{SERVICE_NAME}}

{{SERVICE_SUMMARY}}

A London Borough of Bexley service built on the Power Platform to the council's digital standards.

## New repository from this template?

1. Open the folder in VS Code and run `claude` in VS Code's terminal. Trust the folder, and accept the offer to add the Bexley and Microsoft plugin marketplaces.
2. Run `/lbbexley:new-app` and answer the questions. (In GitHub Copilot, ask it to use the lbbexley-new-app skill.)
3. Run `/lbbexley:requirements`. It asks about the service in the chat, a few questions at a time, or gives you the questions as a table to answer with the service team and paste back later. Ask the service owner to agree the summary, then design the service with `/lbbexley:architect`. (In Copilot, use the lbbexley-requirements and lbbexley-architect skills with the lbbexley-plan agent.)
4. Follow the onboarding guide in the **lbbexley-digital-standards** repository (`docs/onboarding.md`).

## Working on this service

- Read `AGENTS.md`: the service details, how work runs and the rules that always apply.
- Plan, build, check: start each change in plan mode (Claude Code) or with the lbbexley-plan agent (Copilot). The end-of-run check runs before the assistant can finish.
- The assistant builds in the dev environment, with fictional data only, using Microsoft's tools. This repository keeps the guidelines and the latest version of the service, synced from the dev environment.
- Once the end-of-run check passes, the assistant commits the latest version and pushes it to GitHub, on the branch you're on. You don't need to run Git.
- Run `/lbbexley:review` (Copilot: `/lbbexley-review`) before you call a story done. On GitHub, the Quality workflow runs the Bexley standards check on every push and, once set up, the accessibility tests.
- Keep the documents in `docs/compliance/` up to date as the service changes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full workflow.

## Contact

Owner: {{SERVICE_OWNER}}. For the Bexley standards, see the standards repository's [SUPPORT.md](https://github.com/dbraben/lbbexley-digital-standards/blob/main/SUPPORT.md).
