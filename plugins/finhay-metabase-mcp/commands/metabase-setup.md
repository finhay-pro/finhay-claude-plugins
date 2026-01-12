---
name: metabase-setup
description: Setup instructions for Finhay Metabase MCP server
---

# Finhay Metabase MCP Setup

Help the user set up the Metabase MCP server for their Claude Code environment.

## Default Configuration

The Finhay Metabase MCP server is pre-configured with:

- **Metabase URL**: `https://mb.vnsc.vn`
- **Export Directory**: `~/Documents/finhay-metabase-mcp`
- **Read-Only Mode**: Enabled (only SELECT queries allowed)
- **Cache TTL**: 10 minutes
- **Request Timeout**: 10 minutes

## Setup Instructions

Guide the user through these steps:

### Step 1: Add MCP Server to Claude Code

Add the following to your project's `.mcp.json` file (create if it doesn't exist):

```json
{
  "mcpServers": {
    "metabase": {
      "command": "npx",
      "args": ["-y", "@jerichosequitin/metabase-mcp"],
      "env": {
        "METABASE_URL": "https://mb.vnsc.vn",
        "METABASE_USER_EMAIL": "your.email@finhay.com.vn",
        "METABASE_PASSWORD": "your_password_here",
        "METABASE_READ_ONLY_MODE": "true",
        "EXPORT_DIRECTORY": "~/Documents/finhay-metabase-mcp",
        "LOG_LEVEL": "info",
        "CACHE_TTL_MS": "600000",
        "REQUEST_TIMEOUT_MS": "600000"
      }
    }
  }
}
```

Replace:
- `your.email@finhay.com.vn` with your Metabase login email
- `your_password_here` with your Metabase password

### Step 2: Create Export Directory

```bash
mkdir -p ~/Documents/finhay-metabase-mcp
```

### Step 3: Restart Claude Code

Restart Claude Code to load the new MCP server configuration.

## Available Tools

Once configured, the Metabase MCP server provides these tools:

- **Query execution**: Run SQL queries against Metabase databases
- **Dashboard access**: View and interact with Metabase dashboards
- **Question retrieval**: Access saved questions and their results
- **Data export**: Export query results to the configured directory

## Troubleshooting

- **Connection errors**: Verify your email and password are correct
- **Timeout errors**: Increase `REQUEST_TIMEOUT_MS` for long-running queries
- **Permission denied**: Ensure your Metabase user has access to the required databases

## Security Notes

- Never commit your credentials to version control
- Add `.mcp.json` to `.gitignore` if it contains sensitive credentials
- Read-only mode is enabled by default to prevent accidental data modifications
