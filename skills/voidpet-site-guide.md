---
name: voidpet-site-guide
description: Discover and navigate Voidpet's public products, stories, characters, gallery, and legal documents. Use when an agent needs canonical Voidpet links or public site metadata.
---

# Voidpet public site guide

Use Voidpet's read-only discovery surfaces to find canonical public information.

## Start here

1. Fetch `https://voidpet.com/api/discovery` for products, curated public pages, legal documents, and discovery endpoints.
2. Fetch `https://voidpet.com/sitemap.xml` when the curated list does not contain the page you need.
3. Request a supported public page with `Accept: text/markdown` when you want an agent-friendly representation.

## Machine-readable interfaces

- API catalog: `https://voidpet.com/.well-known/api-catalog`
- OpenAPI: `https://voidpet.com/.well-known/openapi.json`
- MCP server card: `https://voidpet.com/.well-known/mcp/server-card.json`
- MCP endpoint: `https://voidpet.com/mcp`

## Boundaries

- These interfaces are public and read-only.
- Do not infer authenticated account or game-state APIs from the public discovery document.
- Use the canonical URLs returned by the discovery API instead of constructing paths from titles.
