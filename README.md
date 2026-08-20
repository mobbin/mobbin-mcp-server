# Official Mobbin MCP server

Mobbin's official MCP server is available at `https://api.mobbin.com/mcp` via Streamable HTTP transport. For setup instructions and usage, see the [documentation](https://docs.mobbin.com/mcp). To learn more about what you can do with the Mobbin MCP server, visit [mobbin.com/mcp](https://mobbin.com/mcp).

## Setup

Mobbin is a hosted remote MCP server — there is nothing to clone, install, or run locally, and no API key to configure. Add it to your MCP client as a Streamable HTTP server:

```json
{
  "mcpServers": {
    "mobbin": {
      "url": "https://api.mobbin.com/mcp"
    }
  }
}
```

Some clients need the transport stated explicitly — in Cline, add `"type": "streamableHttp"` alongside `url`, otherwise it falls back to the legacy SSE transport and the connection fails.

On first use, your client opens a browser window to sign in to Mobbin and authorize access via OAuth.

Per-client, step-by-step instructions are at [docs.mobbin.com/mcp/clients/overview](https://docs.mobbin.com/mcp/clients/overview). For the tools the server exposes, see [docs.mobbin.com/mcp/features](https://docs.mobbin.com/mcp/features).
