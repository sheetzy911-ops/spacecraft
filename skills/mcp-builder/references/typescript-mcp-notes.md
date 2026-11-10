# TypeScript MCP Server Notes

Use the official `@modelcontextprotocol/sdk` package.

Key points:
- Prefer stdio transport for local tools.
- Define tools with zod or JSON Schema for inputs.
- Keep tool handlers pure and side-effect controlled.
- Surface errors via the MCP error protocol rather than throwing unhandled exceptions.

Minimal skeleton is available in the official MCP TypeScript examples. Prefer generating a clean, documented project rather than a single-file script when the surface area grows beyond two or three tools.
