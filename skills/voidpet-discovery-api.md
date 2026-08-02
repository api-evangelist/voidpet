---
name: voidpet-discovery-api
description: Read Voidpet's public discovery document and check service health via the read-only Public Discovery API. Use when an agent needs canonical Voidpet product/page URLs or wants to confirm the discovery service is up.
api: openapi/voidpet-discovery-openapi.json
operations: [getPublicDiscovery, getDiscoveryHealth]
---

# Voidpet Public Discovery API

The Voidpet Public Discovery API is public, read-only, and requires no
authentication. It exposes only public metadata — never accounts or game state.

Base URL: `https://voidpet.com`

## Get the public discovery document

Call `getPublicDiscovery` — `GET /api/discovery`. Returns a JSON
`DiscoveryDocument` with:

- `products[]` — Voidpet products (e.g. Voidpet Dungeon, Voidpet Garden) with `name`, `description`, `url`.
- `pages[]` — curated public `PublicPage` entries (`path`, `title`, `description`, `url`), including legal pages (`/o/privacy`, `/o/terms`).
- `discovery{}` — canonical machine-readable endpoints (api-catalog, openapi, agent-skills, mcp server card, sitemap).

Always use the `url` values returned here as canonical links rather than
constructing paths from titles. Fall back to `https://voidpet.com/sitemap.xml`
when a page you need is not in the curated list.

## Check service health

Call `getDiscoveryHealth` — `GET /api/health`. Returns
`{"status":"ok","service":"voidpet-web"}` when the discovery service is live.

## Boundaries

- Read-only: there are no write operations and no idempotency-key contract.
- No authentication; do not attempt to infer authenticated account or
  game-state endpoints from this document.
- The same public metadata is available over MCP at `POST https://voidpet.com/mcp`.
