---
title: Agents, Tools, and Toolboxes
status: candidate
owner: Product Group AI Platform
review_cycle: monthly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Agents, Tools, and Toolboxes

## Agent responsibility

An agent combines a model, instructions, context, state, tools, and orchestration to pursue a bounded objective. It may assess, retrieve, sequence, explain, or propose. It should not become the hidden owner of business transactions or policy.

## Agent types and local pattern

The Product Group should explicitly distinguish:

- **Prompt agent (Microsoft product type):** configuration-led agent with managed runtime behavior.
- **Hosted agent (Microsoft product type):** code-defined orchestration hosted through the supported Foundry runtime.
- **Deterministic service with a model call (Product Group pattern):** conventional application code using a model without delegating workflow control to an agent.

Choose the simplest form that satisfies the need. Agentic orchestration is justified when the runtime must select or sequence capabilities based on context, not merely because an LLM is present.

## Tool contract

Each tool declares:

- unique task-oriented name;
- precise description and non-goals;
- typed input and output schema;
- caller and downstream authorization;
- data classification;
- read/write and reversibility classification;
- timeout, retry, and idempotency behavior;
- approval requirement;
- audit fields and correlation ID;
- owner, version, and retirement path.

Prefer `get_shipment_details` or `propose_pickup_reassignment` over `query_data` or `update_record`.

## Risk tiers

| Tier | Behavior | Default control |
|---|---|---|
| 0 | Static/read-only public context | allowlisted and logged |
| 1 | Internal read with limited sensitivity | identity, authorization, filtering, logging |
| 2 | Recommendation or draft | structured result, provenance, human review |
| 3 | Reversible write | explicit authority, validation, confirmation/approval, audit |
| 4 | High-impact or irreversible action | deterministic workflow; agent cannot independently authorize |

## Toolboxes

A Foundry Toolbox groups reusable tools and centralizes connection, credential, version, and policy management. Microsoft exposes a toolbox through a managed MCP-compatible endpoint for reuse across agents and runtimes. Toolboxes should be organized around a product/domain or task family rather than becoming an enterprise-wide collection.

Document:

- intended agents and runtimes;
- exact allowed tools;
- connection and identity strategy;
- approval behavior;
- version and change policy;
- environment and network boundary;
- downstream service owners;
- evaluation coverage for tool selection.

Foundry Toolboxes can expose an MCP-compatible endpoint, allowing compatible runtimes to consume the curated set. This makes the Toolbox a useful policy boundary, but the underlying domain services remain authoritative.

## Agent lifecycle

```text
Constitution → Specification → Source → Prompts/Tools → Contracts
→ Golden Cases/Evaluations → Deployment → CI/CD → Versioned Agent
→ Traces/Human Outcomes → Next Evaluated Version
```

## Current Microsoft qualifications

- Core Foundry Agents and Toolboxes are GA, but individual tools and toolbox features can remain preview.
- Tool availability depends on both the project region and selected model; verify the compatibility table before design approval.
- MCP connections support key-based, Microsoft Entra, OAuth identity-passthrough, and unauthenticated patterns. The Product Group has not yet selected an enterprise default for every risk tier.
- Foundry Agents (classic) are deprecated and Microsoft states they will retire on March 31, 2027. Do not start new designs on classic agent APIs.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Agents in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/agents/overview) | 2026-09-19 | Prompt and hosted agent types, runtime, tools, observability, identity |
| [What is a toolbox?](https://learn.microsoft.com/azure/foundry/agents/concepts/toolbox-overview) | 2026-09-19 | Managed MCP endpoint, reuse, governance, authentication, versioning |
| [Foundry Agent Service limits, quotas, and regional support](https://learn.microsoft.com/azure/foundry/agents/concepts/limits-quotas-regions) | 2026-09-19 | Region/model/tool compatibility and limits |
| [Set up authentication for MCP tools](https://learn.microsoft.com/azure/foundry/agents/how-to/mcp-authentication) | 2026-09-19 | Supported MCP authentication and identity patterns |
| [Migrate to the new agents developer experience](https://learn.microsoft.com/azure/foundry/agents/how-to/migrate) | 2026-09-19 | Classic-agent migration path and verification steps |
| [What's new in Foundry Agent Service (classic)](https://learn.microsoft.com/azure/foundry-classic/agents/whats-new) | 2026-09-19 | Classic-agent deprecation and March 31, 2027 retirement date |

Research detail and unresolved enterprise facts are recorded in [Source Record — Microsoft Foundry and MCP](../sources/2026-09-19-foundry-mcp.md).
