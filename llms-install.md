# Installing the Brix36 MCP server

Brix36 is a hosted, remote MCP server. There is nothing to clone, build or run locally.

- Endpoint: `https://api.brix36.com/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with PKCE and dynamic client registration. The user signs in on Brix36's own sign-in page. No API key is needed and none should be put in the config.

## Steps

1. Add this server to the MCP settings file (for Cline, `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "brix36": {
      "type": "streamableHttp",
      "url": "https://api.brix36.com/mcp"
    }
  }
}
```

2. When the client connects, it opens the Brix36 sign-in page in the browser. Ask the user to sign in (or create an account at https://brix36.com) and approve access.
3. After sign-in the tools appear. A good first check is to ask for the user's recent Brix36 videos.

## Notes

- Making a film, music video or image uses credits on the user's own Brix36 account. The tools show the price first and spend nothing until the user says yes.
- If the client does not support OAuth for remote servers, update it to a version that does. The server answers HTTP 401 with an OAuth challenge until the user signs in; that is expected.
- Setup guide: https://brix36.com/connect
- Support: https://legal.brix36.com/support
