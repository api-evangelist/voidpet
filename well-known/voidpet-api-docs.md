# Voidpet public discovery API

Voidpet exposes a small, read-only API for discovering its public products, pages, legal documents, and agent-facing metadata. It does not expose accounts, game state, or authenticated actions.

## Endpoints

- `GET /api/discovery` returns public site metadata and canonical URLs as JSON.
- `GET /api/health` returns the web discovery service's health as JSON.
- `POST /mcp` provides the same public metadata through a stateless Model Context Protocol endpoint.

The machine-readable OpenAPI description is available at `/.well-known/openapi.json`. The MCP server card is available at `/.well-known/mcp/server-card.json`.
