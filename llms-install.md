# Installing the Brix36 video library for Claude

The Brix36 video library is a hosted, remote MCP server. It works only with finished Brix36 videos already in the signed-in account. There is nothing to run locally.

- Endpoint: `https://api.brix36.com/mcp/anthropic-library`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 with PKCE and dynamic client registration. The user signs in on Brix36's own sign-in page. No API key is needed and none should go in the config.

## Claude Code

```
/plugin marketplace add https://github.com/socialiserapp-design/brix36-plugin.git
/plugin install brix36@brix36
```

The plugin brings the connector from `plugins/brix36/.mcp.json` and the skill `find-play-and-download-your-videos`. Sign in to Brix36 when asked, or run `/mcp` and choose `brix36`.

## Claude custom connector

In Claude, open Settings, then Connectors, then Add custom connector, and enter `https://api.brix36.com/mcp/anthropic-library`. Claude opens the Brix36 sign-in page.

## Tools

All five tools work on finished videos already in the account.

- `studio_projects_list` lists finished videos, newest first.
- `studio_artists_list` lists the account's artists, for filtering by artist.
- `studio_video_preview` returns a temporary playback link.
- `studio_video_export` returns a temporary download link.
- `studio_project_rename` renames one finished video. It is the only tool that changes anything.

A good first check is to ask for the user's latest Brix36 videos.

## Notes

- This connector never makes new videos and never spends credits.
- Before sign-in, a tool call answers HTTP 401 with an OAuth challenge. That is expected.
- Privacy: https://legal.brix36.com/privacy
- Terms: https://legal.brix36.com/terms
- Support: https://legal.brix36.com/support
