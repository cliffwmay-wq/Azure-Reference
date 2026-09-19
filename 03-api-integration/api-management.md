---
title: Azure API Management
status: candidate
owner: Product Group Platform
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Azure API Management

Azure API Management (APIM) is the shared governed capability gateway. It exposes stable business APIs and selected MCP tools while centralizing cross-cutting controls.

## Responsibilities

- publish and version APIs;
- authenticate and authorize calls;
- validate, transform, route, throttle, and cache where appropriate;
- apply network and policy controls;
- observe gateway traffic and correlate downstream execution;
- manage developer/product access where applicable;
- expose selected REST operations as MCP tools;
- front an existing remote MCP server.

## Non-responsibilities

APIM does not own domain rules, agent reasoning, system-of-record transactions, data persistence, or product-specific workflow orchestration. Gateway policies should not become an invisible application codebase.

## Capability orientation

Prefer shared capability namespaces such as:

```text
/freight-observation/*
/shipment-intelligence/*
/yard-operations/*
/device-operations/*
```

Avoid treating APIM as infrastructure created separately for every front-end. Products consume governed capabilities; the capability lifecycle determines gateway organization.

## Required API records

- owner and consuming products;
- business purpose and contract version;
- inbound and backend identity;
- data classification;
- rate/quota expectations;
- timeout and retry behavior;
- idempotency and error contract;
- network exposure;
- monitoring and audit fields;
- deprecation and compatibility policy.

## AI gateway concerns

For model or agent traffic, document model routing, content/logging policy, token/cost controls, correlation, safety checks, and failure behavior. Do not log sensitive prompt or response bodies by default merely because gateway diagnostics permit it.

## MCP support

APIM can expose selected operations from a managed REST API as MCP tools or govern an existing remote MCP server. Policies can apply authentication, authorization, rate limits, quotas, IP filtering, caching, and other gateway controls to the MCP server surface.

Current qualifications:

- APIM supports MCP tools but not MCP resources or prompts.
- APIM MCP server capabilities are not supported in workspaces.
- The documented supported tiers are Developer, Basic, Basic v2, Standard, Standard v2, Premium, and Premium v2; enterprise availability and the deployed tier remain unverified.
- Policies apply across the operations exposed as tools in an MCP server; product teams must test whether that policy scope fits the intended authorization model.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [About MCP servers in Azure API Management](https://learn.microsoft.com/azure/api-management/mcp-server-overview) | 2026-09-19 | Remote MCP modes, governance policies, transports, and limitations |
| [Expose a REST API as an MCP server](https://learn.microsoft.com/azure/api-management/export-rest-mcp-server) | 2026-09-19 | Supported tiers, REST-operation export, prerequisites, and tool-only limitation |
| [Expose and govern an existing MCP server](https://learn.microsoft.com/azure/api-management/expose-existing-mcp-server) | 2026-09-19 | Gateway pattern for an externally hosted MCP server |
| [Secure access to MCP servers](https://learn.microsoft.com/azure/api-management/secure-mcp-servers) | 2026-09-19 | Inbound and outbound authentication controls |

Research detail and unresolved enterprise facts are recorded in [Source Record — Microsoft Foundry and MCP](../sources/2026-09-19-foundry-mcp.md).
