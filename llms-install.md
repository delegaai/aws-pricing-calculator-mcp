# LLM Install Guide

This file is written for AI coding agents and MCP marketplace reviewers that need to configure delega.ai for AWS Pricing Calculator.

## Summary

delega.ai for AWS Pricing Calculator is a hosted remote MCP server. Do not install or build a local server from this repository. This repository contains connection guidance, client configs, and public metadata for the hosted service.

## Endpoint

```text
https://calculator.delega.ai/mcp
```

## Recommended setup

1. Open the user's MCP client settings.
2. Add a remote MCP server.
3. Use the server name `delega-ai-aws-pricing-calculator`.
4. Use the URL `https://calculator.delega.ai/mcp`.
5. If the client supports OAuth for remote MCP, complete the browser sign-in flow.
6. If the client requires explicit headers, ask the user for a delega.ai API key and configure `Authorization: Bearer <DELEGA_API_KEY>`.
7. Connect and list tools.

## Cline Streamable HTTP config

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

## Bearer-token config

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

## Validation

After connecting, list tools. The server should expose tools for creating, editing, saving, loading, and searching AWS Pricing Calculator estimates.

Do not expect prompts or resources unless the client displays optional MCP capabilities separately from tools.

## Product constraints

- No AWS credentials are required.
- No AWS infrastructure is provisioned.
- Official `calculator.aws` share URLs are generated only when the user requests that action.
- Saved estimates are stored in the user's delega.ai dashboard.

## Useful links

- Dashboard and client setup: <https://calculator.delega.ai/start/client>
- App dashboard: <https://calculator.delega.ai/app>
