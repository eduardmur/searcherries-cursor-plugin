# Searcherries for Cursor

Connect Cursor to your AI visibility and SEO data, then improve your website's pages in the editor.

[Searcherries](https://searcherries.com) tracks how ChatGPT, Perplexity, Google AI Overviews, Gemini, Claude and Grok answer the questions your customers ask, which competitors and pages they cite, and what your Google Search Console, Bing Webmaster Tools and GA4 AI-traffic data says. This plugin adds the Searcherries MCP server to Cursor, plus a skill that turns the data into concrete page changes in your repository.

## What's included

| Component | What it does |
|-----------|--------------|
| MCP server `searcherries` | Remote Streamable HTTP server at `https://app.searcherries.com/mcp/searcherries`, read-only, OAuth sign-in |
| Skill `improve-ai-visibility` | Finds the questions where AI answers leave your brand out, the competitors and sources they use instead, and maps them to the pages in your codebase |

## Requirements

A Searcherries account on a paid plan (an active trial counts) with at least one project. [Start here](https://app.searcherries.com/register).

## Install and connect

1. Install **Searcherries** from the Cursor Marketplace.
2. Open Cursor Settings → MCP and click **Connect** next to Searcherries.
3. Sign in to Searcherries in the browser and approve access.

Then ask the Agent, for example:

- "What should I work on next for my Searcherries project?"
- "Which customer questions do AI assistants answer without naming us, and which competitors do they name instead?"
- "Which pages in this repo should we update first to get recommended by ChatGPT and Perplexity? Show the evidence."

## Tools

| Tool | Returns |
|------|---------|
| `get-action-plan` | Prioritized next steps for a project, with dated evidence |
| `list-projects` | Your Searcherries projects |
| `get-project-summary` | Compact snapshot: questions, KPIs, competitors, cited domains, 30-day search and traffic totals |
| `get-ai-answers` | Stored AI answers with judgments: how prominently the brand is named, sentiment, off-topic answers |
| `get-competitors` | Brands the AI platforms name, one brand in detail, monthly history |
| `get-citations` | URLs and domains the answers cite, including your own pages |
| `get-search-performance` | Search Console and Bing data: top queries and pages, opportunities, question-shaped searches, trends |
| `get-ai-traffic` | GA4 sessions from AI assistants, landing pages, history |
| `get-project-data` | Bulk sections for deeper analysis |

The server is read-only. It cannot change projects, questions or billing, and it only returns data from the Searcherries account you authorize. Full reference: [searcherries.com/docs/mcp/tools](https://searcherries.com/docs/mcp/tools).

## Without the Marketplace

Add the server to `~/.cursor/mcp.json` (or `.cursor/mcp.json` in one project):

```json
{
  "mcpServers": {
    "searcherries": {
      "url": "https://app.searcherries.com/mcp/searcherries"
    }
  }
}
```

Setup for other clients (Claude, Claude Code, Codex, VS Code) is at [searcherries.com/docs/mcp/overview](https://searcherries.com/docs/mcp/overview).

## Support

Questions and issues: [open an issue](https://github.com/eduardmur/searcherries-cursor-plugin/issues) or write from your account at [app.searcherries.com](https://app.searcherries.com).

## License

MIT
