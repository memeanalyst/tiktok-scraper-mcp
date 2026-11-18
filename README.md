# TikTok Scraper — MCP Server

Scrape TikTok profiles and videos from your AI agent or MCP client — no login, no cookies, no account involved. Get structured profile records (followers, following, total likes, video count, verified and TikTok Shop seller flags) and video records (views, likes, comments, shares, saves, duration, music, thumbnails) for any public account or video URL.

This repo is the MCP listing for the [TikTok Scraper](https://apify.com/magnova/tiktok-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--tiktok-scraper** — Fetch TikTok profiles plus their most recent videos, or full records for individual video URLs. Returns structured PROFILE and VIDEO records: follower and like counts, views, comments, shares, saves, music title and author, thumbnails, and download links where TikTok offers them.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/tiktok-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "tiktok-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/tiktok-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "tiktok-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/tiktok-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/tiktok-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.001 per result record returned — $1 per 1,000 records**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/tiktok-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/tiktok-scraper

*Profile and video data comes from TikTok's public pages, read logged out. Emails and phone numbers are removed from bios and captions.*
