# ConnectWise AI Ticket Triage (n8n)

n8n workflow that reads new ConnectWise tickets, classifies them with AI, assigns an available technician,
escalates when needed, alerts Teams for high-priority tickets and sends an out-of-scope reply for non-IT requests.

## Contents
| Path | What it is |
|---|---|
| `workflow/CW_AI_Ticket_Triage_n8n_Workflow.json` | Importable n8n workflow (dry run is ON by default) |
| `test-page/cw_triage_test_page.html` | Open in a browser to try the routing logic with sample tickets (simulation only) |
| `.devcontainer/` | Lets you run n8n inside GitHub Codespaces |
| `.github/workflows/validate.yml` | Checks the workflow JSON is valid and has no pasted secrets |

## Run it
1. Start n8n (on your computer: `npx n8n`, or in a Codespace: `n8n start`) and open the editor.
2. Create the owner account.
3. Import the workflow: open the JSON file, copy everything, and paste it onto the n8n canvas (or use Import from File on a local install).
4. Add credentials inside n8n (ConnectWise, OpenAI, Outlook, Teams). Edit the **Config** and **Route Ticket** nodes.
5. Test with `dryRun = true` on a test board before going live.

## Rules for this repository
- Never commit API keys, passwords or exported credentials. Credentials stay inside n8n.
- Keep `clientId`, `boardName` and roster names as placeholders in committed files.
- Keep the repository private.
- Commit changes to the workflow with a clear message, so you can roll back with a revert.
