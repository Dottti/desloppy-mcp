# Installing Desloppy (for AI agents such as Cline)

Desloppy is a hosted remote MCP server. There is nothing to clone, build or run locally.

1. Add this server to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "desloppy": {
      "type": "streamableHttp",
      "url": "https://desloppy.com/mcp"
    }
  }
}
```

2. On first use the client opens the Desloppy sign-in page (OAuth). The user pastes a Desloppy key, or enters an
   email to create a free key (5,000 words, no card).

3. If the client cannot do OAuth, ask the user for their key from https://desloppy.com and send it as a header:

```json
{
  "mcpServers": {
    "desloppy": {
      "type": "streamableHttp",
      "url": "https://desloppy.com/mcp",
      "headers": { "Authorization": "Bearer gk_..." }
    }
  }
}
```

Never put the key in the URL; the server refuses keys in URLs.

4. Test it: call `quick_fixes` with the text "In today's fast-paced world, synergy is crucial." It should return
   three findings with fixes.
