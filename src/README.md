# Source

Everything that makes up the service, as text, so every change is reviewed in a pull request.

| Folder | What goes in it | How it gets there |
|---|---|---|
| `solution/` | The unpacked Dataverse solution: tables, columns, choices, security roles, flows, environment variables, connection references | `pac solution clone`, then `pac solution sync` after changes in the dev environment |
| `canvas/<app name>/` | Canvas app source (`.pa.yaml`) | Microsoft's canvas app authoring tools |
| `pages/` | Power Pages site source | `pac pages download`, or Microsoft's power-pages plugin |
| `agent/` | Copilot Studio agent source (`.mcs.yml`) | The Copilot Studio extension for VS Code |

Don't commit solution zip files, `.msapp` files, secrets or exported data.
