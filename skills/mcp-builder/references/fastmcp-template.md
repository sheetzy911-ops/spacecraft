# Minimal FastMCP Server Template

```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("Example Server")

@mcp.tool()
def example_tool(param: str) -> str:
    """Clear description of what this tool does."""
    # Implementation
    return f"Processed: {param}"

if __name__ == "__main__":
    mcp.run()
```

## Recommended structure

```
my-mcp-server/
├── pyproject.toml or requirements.txt
├── src/
│   └── server.py
├── README.md
└── .env.example
```

Always document:
- Required environment variables
- Start command (`uv run` or `python -m ...`)
- Example MCP client config for Claude Desktop / Cursor / etc.
