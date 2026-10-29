# Close

Cursor plugin that connects agents to [Close](https://close.com) CRM through Close's hosted [Model Context Protocol](https://modelcontextprotocol.io/) server.

Use the Close plugin to search, manage, or analyze CRM records and communication activities. The plugin also includes tools to create Workflows, manage Voice Agents, and more.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Close**.
3. Click **Install**, then select **Connect** when Cursor shows that Close needs authentication.

Or run `/add-plugin close` in chat.

## MCP

```json
{
  "mcpServers": {
    "close": {
      "type": "http",
      "url": "https://mcp.close.com/mcp"
    }
  }
}
```

The server is Close's hosted MCP (Streamable HTTP). When you connect, choose your Close organization and access scope, then approve the connection. Close supports three OAuth scopes:

- `mcp.read` — search and read Close data;
- `mcp.write_safe` — read plus create and update records;
- `mcp.write_destructive` — read, create, update, and delete records.

Choose the least-privileged scope that covers your work. You can revoke the connection from Close at any time. Available tools depend on the scope you approve.

The plugin contains no API keys, local server process, or additional data proxy.

## Included skills

| Skill | Purpose |
| --- | --- |
| `close-crm` | Choose appropriate Close tools, research records, answer product questions, and handle CRM writes safely. |
| `account-brief` | Prepare a lead brief from contacts, opportunities, recent activity, and tasks. |
| `pipeline-review` | Identify pipeline risk, stale deals, and next actions. |
| `follow-up-plan` | Prepare a follow-up plan from recent conversations and open work. |

The brief, pipeline review, and follow-up plan skills produce read-only analysis. CRM changes require a user request; OAuth access alone does not authorize an action.

## Try asking

- “Brief me on Acme before my call.”
- “Which active opportunities need attention this week?”
- “Prepare a follow-up plan for Acme.”
- “Find my overdue Close tasks and prioritize them.”
- “How many calls did our team make last week?”
- “Create a follow-up task for Friday on this lead.”

## Docs

- Close MCP documentation: https://developer.close.com/mcp
- Close MCP tool reference: https://developer.close.com/mcp/tools
- Close Help Center: https://help.close.com
- Close support: support@close.com

Skills and logo are from Close's [agent-plugin](https://github.com/closeio/agent-plugin) repository.

## License

MIT
