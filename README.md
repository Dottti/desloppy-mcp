<p align="center"><img src="icon.png" width="96" alt="Desloppy"></p>

# Desloppy MCP server

Find the lines that make your writing sound like AI, and fix them in your own voice.

Desloppy is a hosted, remote MCP server. Connect it to Claude, Cursor, VS Code or any MCP client, then ask:
"Check this with Desloppy and make it sound like me."

- **Server URL:** `https://desloppy.com/mcp` (Streamable HTTP)
- **Sign-in:** OAuth. Paste a Desloppy key, or create a free key with just an email (5,000 words, no card).
- **Website and docs:** https://desloppy.com · https://desloppy.com/docs
- **Official MCP Registry:** `com.desloppy/desloppy`
- **Smithery:** https://smithery.ai/servers/m-alshakaa/desloppy

## What it does

You get an AI score, the passages to rewrite first, and line-by-line notes on what sounds machine-made:
stock phrases, rule-of-three lists, hedging, flat sentence rhythm and more. Claude rewrites only the flagged lines,
keeps every fact, name and number, and runs the check again.

Each kind of writing gets its own rules: `email`, `essay`, `presentation`, `social`, `fiction`, `general`, or `auto`.

## Tools

All tools are read-only.

| Tool | What it returns |
|---|---|
| `check_writing` | Full check: verdict, AI score, passages to rewrite first, line-numbered fixes and a ready-made summary |
| `quick_fixes` | Instant rule checks with a plain fix for each line. Free and unlimited |
| `ai_score` | Detector score only, per ~300-word chunk |
| `check_file` | The full check for a `.docx`, `.pptx` (slides and speaker notes), `.pdf`, `.txt` or `.md` file |
| `compare` | Before and after scores, to show a rewrite worked |

There is also one prompt, **Make it sound human**, and a resource with writing tips per kind: `desloppy://tips/{kind}`.

## Connect

**Claude (web and desktop):** Settings → Connectors → Add custom connector. Name `Desloppy`, URL `https://desloppy.com/mcp`. Click Connect and sign in.

**Claude Code:**

```bash
claude mcp add --transport http desloppy https://desloppy.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "desloppy": { "url": "https://desloppy.com/mcp" }
  }
}
```

**VS Code** (`.vscode/mcp.json`):

```json
{
  "servers": {
    "desloppy": { "type": "http", "url": "https://desloppy.com/mcp" }
  }
}
```

Clients without OAuth can send a key as a header: `Authorization: Bearer gk_...`. Keys in URLs are refused.

## Plans

Free: 5,000 words of AI checks plus unlimited quick fixes. Paid plans start at $9 a month. See https://desloppy.com.

## Privacy

Text is processed in memory and never stored. The detector runs on Desloppy's own server, and your text is not sent
to any outside AI service. Full policy: https://desloppy.com/privacy

AI detection is a probability. A score is never proof that a person used AI, so never use it as evidence against
anyone.

## Support

support@desloppy.com

This repository holds the public listing and client setup. The server itself is a hosted service.
