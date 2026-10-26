# Official Mobbin MCP server

Mobbin is available as an official plugin or connector in AI tools and MCP clients such as Claude, ChatGPT, Codex, Cursor, Grok, Figma and Antigravity. For a quick overview, visit our [MCP product page](https://mobbin.com/mcp).

> [!NOTE]
> The Mobbin plugin is set up in [mobbin/skills](https://github.com/mobbin/skills), not this repository. This repository only contains the MCP server configuration and does not include skills.

## Setup

### Recommended setup

Follow the [Mobbin MCP docs](https://docs.mobbin.com/mcp/introduction) to find the official Mobbin plugin or connector for your AI tool, with step-by-step setup instructions. Where your AI tool supports plugins, the Mobbin plugin bundles the Mobbin skills together with the MCP server. If it doesn't, install the Mobbin skills separately from [mobbin/skills](https://github.com/mobbin/skills).

### Manual setup with Streamable HTTP (not recommended)

> [!WARNING]
> Manual setup connects the MCP server only, without the Mobbin skills. Use the [recommended setup](#recommended-setup) if your AI tool is listed.

Mobbin's MCP server is hosted at `https://api.mobbin.com/mcp` and uses the Streamable HTTP transport. There is nothing to clone, install, or run locally, and no API key to configure. Add it to your MCP client as a Streamable HTTP server:

```json
{
  "mcpServers": {
    "mobbin": {
      "url": "https://api.mobbin.com/mcp"
    }
  }
}
```

Some clients need the transport stated explicitly. In Cline, add `"type": "streamableHttp"` alongside `url`, otherwise it falls back to the legacy SSE transport and the connection fails.

On first use, your client opens a browser window to sign in to Mobbin and authorize access via OAuth.

For the tools the server exposes, see [docs.mobbin.com/mcp/features](https://docs.mobbin.com/mcp/features).
