---
title: Model Context Protocol
status: candidate
owner: Product Group AI Platform
review_cycle: monthly
source_posture: Microsoft-and-protocol-grounded
last_reviewed: 2026-09-19
---

# Model Context Protocol

MCP is a standardized interface through which compatible AI hosts discover and use tools, resources, and prompts. It is an edge protocol—not the Product Group's business architecture.

## Governing position

> API-first underneath. MCP-ready at the edge. Governed throughout.

Business logic, transaction integrity, validation, and authoritative state remain in domain services and systems of record. MCP exposes selected capabilities to compatible AI runtimes.

## Microsoft component model

| Component | MCP function |
|---|---|
| Azure Functions | Builds custom tools, resources, prompts, and MCP app behavior |
| API Management | Converts REST operations to tools or governs an existing remote MCP server |
| Foundry Toolbox | Curates approved tools and can expose a reusable MCP-compatible endpoint |
| Foundry Agent Service | Consumes MCP capabilities as an agent runtime |
| Azure API Center | Catalogs and supports discovery of approved MCP servers |
| Entra ID/RBAC | Establishes identity and authorization |
| Monitor/App Insights | Observes calls, performance, and failures |

## When to use

- multiple agent clients need the same capability;
- portable tool discovery has value;
- a trusted vendor provides a supported endpoint;
- the surface can be narrowly permissioned;
- gateway, identity, logging, and approval controls are available.

Prefer a direct API or native function/tool when one controlled runtime consumes one deterministic operation and MCP adds no portability or governance benefit.

## Server design

Each server has a bounded domain and small, curated surface. Classify every capability as read, analysis/proposal, reversible write, or consequential action. Avoid generic query/execute/update tools.

Required controls:

- trusted ownership and deployment source;
- explicit tool allowlist;
- precise schemas and descriptions;
- identity propagation or documented service identity;
- least privilege;
- untrusted-input treatment for descriptions, retrieved content, and results;
- approval for high-risk calls;
- audit of server, tool, caller, arguments classification, and outcome;
- version and behavior-change review.

## Transport

Remote enterprise servers use supported HTTP transport, currently Streamable HTTP as the preferred modern protocol transport. Local standard-input/output servers are appropriate for controlled developer tooling, not shared enterprise operations.

## Current Microsoft qualifications

- Foundry Agent Service connects to remote MCP servers and can centralize reusable MCP tools through a Toolbox. Authentication can use keys, Microsoft Entra identities, OAuth identity passthrough, or no authentication when appropriate.
- API Management supports remote MCP server mode. It can expose selected operations from a managed REST API as tools or govern an existing remote MCP server.
- API Management currently supports MCP tools, not MCP resources or prompts, and its MCP server capabilities are not supported in APIM workspaces.
- Azure Functions MCP bindings can implement tool, resource, and prompt triggers. Runtime, language, extension-version, transport, storage, and authorization requirements must be validated during implementation.
- Microsoft documentation identifies Streamable HTTP as replacing the deprecated HTTP+SSE transport. Client and server compatibility must still be tested.

## Sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Model Context Protocol specification](https://modelcontextprotocol.io/specification/2026-07-28) | 2026-09-19 | Protocol concepts and transport standard |
| [Connect agents to MCP servers](https://learn.microsoft.com/azure/foundry/agents/how-to/tools/model-context-protocol) | 2026-09-19 | Foundry remote MCP connection and Toolbox guidance |
| [Set up authentication for MCP tools](https://learn.microsoft.com/azure/foundry/agents/how-to/mcp-authentication) | 2026-09-19 | Foundry MCP authentication and identity options |
| [About MCP servers in API Management](https://learn.microsoft.com/azure/api-management/mcp-server-overview) | 2026-09-19 | APIM modes, governance, transport, and current limitations |
| [MCP bindings for Azure Functions](https://learn.microsoft.com/azure/azure-functions/functions-bindings-mcp) | 2026-09-19 | Function triggers, transports, and implementation prerequisites |

Research detail and unresolved enterprise facts are recorded in [Source Record — Microsoft Foundry and MCP](../sources/2026-09-19-foundry-mcp.md).
