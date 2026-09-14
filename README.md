# MySQL MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/mysql)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect MySQL to AI assistants: schemas, tables, SQL and database health for MySQL and MariaDB.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use MySQL from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/mysql-icon.svg" alt="MySQL MCP Server" width="64" height="64">

## MCP Server URL

```
https://mysql.insightfulmcp.com/
```

## What is MySQL MCP?

MySQL MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Browse schemas, inspect tables, and run SQL against your own MySQL or MariaDB instance. Read vs. read-write is decided by the GRANT/REVOKE privileges on the role this connector logs in as.

## Installation

### Claude

1. Copy the MCP Server URL: `https://mysql.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://mysql.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http mysql https://mysql.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "mysql": {
      "url": "https://mysql.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

8 actions: 7 read, 1 write.

### Read Actions (7)

| Action | Description |
|--------|-------------|
| `analyze_db_health` | Connection pool + buffer pool size + tables with reclaimable space |
| `explain_query` | EXPLAIN plan for a query |
| `get_table_metadata` | Full metadata: columns + constraints + indexes + estimated size |
| `get_table_schema` | Column list (name, data_type, is_nullable, default) for a table or view |
| `get_top_queries` | Heaviest queries from performance_schema.events_statements_summary_by_digest |
| `list_schemas` | List all schemas (databases) on the server |
| `list_tables` | List tables, views, or plugins in a schema |

### Write Actions (1)

| Action | Description |
|--------|-------------|
| `run_query` | Execute a SQL statement |

## Usage Examples

```
"List the tables in my database"
```

```
"Show the schema of the orders table"
```

```
"Run a query for revenue by month"
```

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [PostgreSQL MCP](https://insightfulpipe.com/mcp-servers/postgresql)
- [SQL Server MCP](https://insightfulpipe.com/mcp-servers/mssql)
- [BigQuery MCP](https://insightfulpipe.com/mcp-servers/bigquery)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
