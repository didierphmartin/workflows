# SynergyAI workflows

Workflow packages for [SynergyAI](https://synergyaichat.com). Each `.zip` is one workflow as SynergyAI exports it, with
everything it needs: the workflow, the code components it uses and the MCP servers it calls (their code and settings
form, never their settings). Import one in SynergyAI with **Import → From GitHub** and the link to the zip, or download
it and import the file.

| Package | What it does | MCP servers | Code components |
|---|---|---|---|
| `Move_Email_to_Sharepoint.zip` | An email dragged into an Outlook folder is turned into a PDF and filed, with its attachments, in a SharePoint folder (one subfolder per email) | Outlook (`outlook_mcp`), SharePoint (`sharepoint_mcp`) | Outlook: On dropped email, PDF: convert document, SharePoint: move |
| `A_code_node_test.zip` | Takes the oldest open SynergyAI task from ServiceNow, runs the playbook its tag names, then closes the task, or hands it back to a human group with the playbook's failure reason | ServiceNow (registration only: its code is not in the package; install the server separately) | ServiceNow: get new job, ServiceNow: complete job, ServiceNow: hand back |

The servers are also in [didierphmartin/mcps](https://github.com/didierphmartin/mcps) and the components in
[didierphmartin/Code_component](https://github.com/didierphmartin/Code_component); a package carries its own copies,
the versions it was tested with.

Settings asked at import for this workflow: for each server, the Entra ID app (client) ID and an encryption key for
the stored sign-ins; for filing per VIP mailbox, the Outlook organization connection (tenant, app ID, client secret,
VIP group). The servers' READMEs say where each one is found.
