# Cursor

Use the hosted delega.ai MCP endpoint in Cursor's MCP configuration.

```json
{
  "mcpServers": {
    "delega-ai-aws-pricing-calculator": {
      "url": "https://calculator.delega.ai/mcp"
    }
  }
}
```

If Cursor requires explicit authorization headers for your setup:

```json
{
  "mcpServers": {
    "delega-ai-aws-pricing-calculator": {
      "url": "https://calculator.delega.ai/mcp",
      "headers": {
        "Authorization": "Bearer <DELEGA_API_KEY>"
      }
    }
  }
}
```

