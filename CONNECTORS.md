# Connectors

This plugin brings its own connector: the Protime MCP server.

| Connector | Endpoint | Authentication |
|-----------|----------|----------------|
| **Protime** | `https://mcp.protime.ai/mcp` | OAuth 2.0 with PKCE (Dynamic Client Registration) |

The server is declared in `.mcp.json` and activates when you install the plugin. On first use you sign in with your Protime account.

## What the connector provides

| Area | Tools |
|------|-------|
| **Swiss register** | `search_shab`, `check_companies`, `search_persons`, `search_revisions`, `search_building_permits`, `estimate_company_size`, `verify_claims` |
| **Briefings** | `create_briefing`, `get_briefings`, `get_issues`, `get_issue`, `search_issues`, `manage_config`, `manage_sources` |
| **Story Pool** (requires a Story Pool API key) | `search_news`, `get_story` |

The register tools work for every account within a free quota. Without a Story Pool API key, those two tools answer that access is required.

## Optional integrations

These connectors fit well alongside Protime when installed separately:

| Connector | Use |
|-----------|-----|
| Google Calendar | Match briefing content to upcoming meetings |
| Gmail / Outlook | Check the companies in a client mail against the register |
| Slack | Share briefing highlights with a channel |
