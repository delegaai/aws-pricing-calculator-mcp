# Cline

Cline supports remote MCP servers over Streamable HTTP or SSE.

## Remote server setup

1. Open Cline.
2. Open MCP Servers.
3. Choose the Remote Servers setup path.
4. Add:

```text
Server name: delega-ai-aws-pricing-calculator
Server URL: https://calculator.delega.ai/mcp
Transport: Streamable HTTP
```

## JSON config

```json
{
  "mcpServers": {
    "delega-ai-aws-pricing-calculator": {
      "url": "https://calculator.delega.ai/mcp",
      "type": "streamableHttp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

If your setup requires an API key:

```json
{
  "mcpServers": {
    "delega-ai-aws-pricing-calculator": {
      "url": "https://calculator.delega.ai/mcp",
      "type": "streamableHttp",
      "headers": {
        "Authorization": "Bearer <DELEGA_API_KEY>"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

## Test prompt

```text
Create an AWS Pricing Calculator estimate for a small production web app with one load balancer, two EC2 instances, an RDS PostgreSQL database, and S3 storage. Save the estimate and return the shareable calculator.aws URL.
```
