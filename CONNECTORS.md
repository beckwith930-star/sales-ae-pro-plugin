# Connectors

## How tool references work

Plugin files use `~~` placeholders for optional external services. These get replaced with specific tool references when you customize the plugin for your environment.

## Connectors for this plugin

| Category | Placeholder | Default Config | Alternatives |
|----------|-------------|---------------|--------------|
| CRM | `~~salesforce-org` | Salesforce CLI (`sf` command) | Salesforce MCP if available |
| Salesforce owner filter | `~~salesforce-owner` | Your full name in Salesforce | Configure in settings.md |
| Email | `~~email` | Gmail MCP (in .mcp.json) | Outlook MCP, CLI-based `gmail-cli` |
| Chat | `~~chat` | Slack MCP (in .mcp.json) | Microsoft Teams MCP, remove if unused |
| Documents | `~~docs` | Google Drive MCP (in .mcp.json) | SharePoint, remove if unused |

## Salesforce Setup (Required)

Salesforce is accessed via the `sf` CLI — no MCP required.

1. Install the Salesforce CLI: `npm install -g @salesforce/cli`
2. Authenticate: `sf org login web --alias my-org`
3. Verify: `sf org list`
4. Add your org alias to `config/settings.md` under `SALESFORCE_ORG_ALIAS`
5. Add your full Salesforce name to `SALESFORCE_OWNER_NAME` — must match exactly

## Email Setup (Optional)

If you want Claude to read your email for call prep context:
1. Gmail MCP is pre-configured in `.mcp.json` — it will prompt for OAuth on first use
2. If you don't use Gmail, remove the `gmail` entry from `.mcp.json`

## Slack Setup (Optional)

If you want deal signals or briefings posted to Slack:
1. Slack MCP is pre-configured in `.mcp.json` — it will prompt for OAuth on first use
2. If you don't use Slack, remove the `slack` entry from `.mcp.json`

## Google Drive Setup (Optional)

If you want deliverables saved to Google Drive or want to reference Drive documents in call prep:
1. Google Drive MCP is pre-configured in `.mcp.json`
2. If you don't use Google Drive, remove the `google-drive` entry from `.mcp.json`
