---
name: mcp-builder
description: Teach and enable agents to design, implement, and register custom Model Context Protocol (MCP) servers in Python (FastMCP) or TypeScript so new tools, APIs, data sources, and cloud services can be dynamically integrated. Use when the user needs a new MCP server, custom tool exposure, or dynamic capability extension for an agent.
---

# MCP Builder

## Overview

Enable the agent to create production-ready Model Context Protocol servers on demand. The resulting servers expose tools, resources, and prompts that other agents or clients can discover and call.

## When to Use

- User asks to “create an MCP server”, “expose this API as tools”, “build a custom MCP”, or “add a new tool via MCP”.
- Need to integrate a new external service, database, or internal API into an agent’s toolset.
- Building reusable capability packages that multiple agents can consume.

## Supported Stacks

Primary targets:
- **Python** — FastMCP (preferred for rapid development)
- **TypeScript / Node** — official MCP SDK

## Instructions

### 1. Clarify the contract

- List the tools (name, description, input schema, expected output).
- Identify any resources (URI templates, MIME types) or prompts that should be exposed.
- Determine authentication, rate limits, and error-handling requirements.
- Choose language (Python FastMCP by default unless the user specifies otherwise).

### 2. Scaffold the server

- Create a minimal, runnable project structure.
- Declare tools with clear names, descriptions, and JSON-schema inputs.
- Implement each tool as a pure, side-effect-aware function.
- Add basic logging and structured error responses.

### 3. Security and robustness

- Never hard-code secrets; require environment variables or secure configuration.
- Validate all inputs against the declared schema.
- Return actionable error messages; never leak stack traces or internal details to the caller.
- Prefer least-privilege access to underlying systems.

### 4. Packaging and registration

- Produce a complete, self-contained server that can be started with a single command.
- Document the exact start command, required environment variables, and example client configuration.
- When appropriate, include a simple test or smoke-check that exercises each tool.

### 5. Delivery

- Hand the user a ready-to-run directory or repository.
- Provide the MCP client configuration snippet (stdio or SSE/HTTP transport).
- Note any follow-up steps (secrets, network access, deployment).

## Quality bar

- Every tool has a precise description and typed input schema.
- The server starts cleanly and reports its tools on the MCP initialize handshake.
- Failures are handled gracefully and return MCP-compatible error structures.
- No unnecessary dependencies.

## References

- See `references/fastmcp-template.md` for a minimal Python FastMCP skeleton.
- See `references/typescript-mcp-notes.md` for TypeScript guidance.
