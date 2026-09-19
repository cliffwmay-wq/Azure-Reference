---
title: Azure Functions and Container Apps
status: candidate
owner: Product Group Platform
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Azure Functions and Container Apps

## Azure Functions

Use Functions for bounded event-driven or request-driven compute where managed scaling and trigger/binding integration reduce operational burden.

Typical uses:

- API operations and adapters;
- event/message handlers;
- lightweight orchestration;
- scheduled jobs;
- file/image processing triggers;
- MCP-native tools, resources, and prompts through the Azure Functions MCP extension.

Do not let a collection of unrelated Functions become an undocumented distributed monolith. Group by bounded capability and document shared deployment, configuration, scaling, and failure impact.

## Azure Container Apps

Use Container Apps for containerized APIs, workers, jobs, or MCP servers requiring custom runtime control without adopting full Kubernetes operations.

Typical uses:

- long-lived HTTP services;
- custom libraries or system dependencies;
- workers consuming queues or streams;
- scheduled/triggered container jobs;
- privately hosted remote MCP servers;
- scale-to-zero workloads where supported by the workload.

## Selection

| Question | Functions | Container Apps |
|---|---|---|
| Trigger/binding-led execution? | strong fit | possible but less native |
| Custom container/runtime? | supported in some models | strong fit |
| Long-lived service process? | less natural | strong fit |
| Simple individual operation? | strong fit | may be excessive |
| Complex service with multiple endpoints? | possible | often clearer |

## Shared production requirements

- managed identity and least-privilege RBAC;
- Key Vault-backed secrets or references;
- private connectivity as required;
- explicit scaling and concurrency behavior;
- timeouts, retries, idempotency, and poison-message handling;
- deployment slots/revisions and rollback strategy;
- Application Insights/OpenTelemetry correlation;
- health checks, dependency monitoring, and support ownership.

Azure Functions can directly create remote MCP surfaces with tool, resource, and prompt triggers. Microsoft recommends Streamable HTTP for clients that do not specifically require the older SSE transport. Language support, minimum package versions, host storage permissions for SSE, the MCP system key, and any identity-based authorization layer must be verified for the selected implementation.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [MCP bindings for Azure Functions](https://learn.microsoft.com/azure/azure-functions/functions-bindings-mcp) | 2026-09-19 | Tool/resource/prompt triggers, transport, runtime prerequisites, and endpoint authorization |
| [Use AI tools and models in Azure Functions](https://learn.microsoft.com/azure/azure-functions/functions-create-ai-enabled-apps) | 2026-09-19 | MCP hosting choices and preview qualifications |
| [Azure Container Apps documentation](https://learn.microsoft.com/azure/container-apps/) | 2026-09-19 | Container Apps capability landing page; scenario details require implementation review |

Research detail and unresolved enterprise facts are recorded in [Source Record — Microsoft Foundry and MCP](../sources/2026-09-19-foundry-mcp.md).
