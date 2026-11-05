# Source

The latest version of the service from the dev environment, as text, so every change is reviewed and kept. Nobody edits it here by hand: the assistant builds in the dev environment, and each change comes back into this folder before it's reviewed, committed and pushed.

| Folder | What goes in it | How it gets there |
|---|---|---|
| `solution/` | The unpacked Dataverse solution: tables, columns, choices, security roles, flows, environment variables, connection references | `pac solution clone` once, then `pac solution sync` after every change in the dev environment |
| `canvas/<app name>/` | Canvas app source (`.pa.yaml`) | Microsoft's canvas tools work in this folder and compile it into the app open in Power Apps Studio. Their planning notes (`.md`) here are ignored by Git |
| `pages/` | Power Pages site source | Microsoft's power-pages plugin, uploaded to the dev site with `pac pages upload` |
| `agent/` | Copilot Studio agent source (`.mcs.yml`) | The Copilot Studio extension for VS Code, which applies each change to the agent |

Don't commit solution zip files, `.msapp` files, secrets or exported data.
