# delega.ai for AWS Pricing Calculator

Official MCP connection guide for the hosted delega.ai AWS Pricing Calculator server.

Enable AI agents to create, edit, save, and load AWS Pricing Calculator estimates via MCP. The toolset lets agents estimate deployment costs and generate official shareable calculator.aws URLs.

Generated estimates are saved to the delega.ai dashboard, so users can revisit and manage their work. Team plans add customer and opportunity tracking, shared notes, and AWS Co-Sell pipeline tracking.

## Hosted MCP server

```text
https://calculator.delega.ai/mcp
```

The server is hosted by delega.ai. You do not need to run a local Node, Python, or Docker process to connect to it.

## What this server does

- Create AWS Pricing Calculator estimates from natural-language requirements.
- Edit existing estimates and compare configurations.
- Save estimates to the delega.ai dashboard.
- Load estimates from previous delega.ai workspaces.
- Generate official shareable `calculator.aws` URLs.

## What this server does not do

- It does not provision AWS infrastructure.
- It does not read your AWS account.
- It does not require AWS credentials.
- It does not manage IAM, billing accounts, or deployed workloads.

When a user asks to generate or load an official AWS Pricing Calculator share URL, delega.ai sends the relevant estimate configuration to AWS at the user's request.

## Authentication

delega.ai is a hosted commercial service. Some clients can connect through remote MCP OAuth. Other clients may require an API key or bearer-token style header.

Start here:

```text
https://calculator.delega.ai/start/client
```

## Client setup

- [Cline](clients/cline.md)
- [Cursor](clients/cursor.md)
- [Claude](clients/claude.md)
- [mcpc](clients/mcpc.md)
- [Docker MCP Toolkit](clients/docker-mcp-toolkit.md)

For LLM agents and marketplace reviewers, see [llms-install.md](llms-install.md).

## Generic remote MCP config

Use this for clients that support hosted Streamable HTTP MCP servers:

```json
{
  "mcpServers": {
    "delega-ai-aws-pricing-calculator": {
      "url": "https://calculator.delega.ai/mcp"
    }
  }
}
```

If your client needs a bearer token:

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

## Support

See [SUPPORT.md](SUPPORT.md).

## Security

See [SECURITY.md](SECURITY.md).
