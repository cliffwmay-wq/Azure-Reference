---
title: Source Record — Microsoft Foundry and MCP
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Microsoft Foundry and MCP

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate guidance for Microsoft Foundry, agents, Toolboxes, and Azure-hosted or governed MCP surfaces?

## Primary Microsoft Learn sources

| Page title | URL | Page date | Retrieved |
|---|---|---|---|
| What is Microsoft Foundry? | https://learn.microsoft.com/azure/foundry/what-is-foundry | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Microsoft Foundry architecture | https://learn.microsoft.com/azure/foundry/concepts/architecture | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Microsoft Foundry general availability | https://learn.microsoft.com/azure/foundry/concepts/general-availability | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Agents in Microsoft Foundry | https://learn.microsoft.com/azure/foundry/agents/overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is a toolbox? | https://learn.microsoft.com/azure/foundry/agents/concepts/toolbox-overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Foundry Agent Service limits, quotas, and regional support | https://learn.microsoft.com/azure/foundry/agents/concepts/limits-quotas-regions | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Connect agents to Model Context Protocol servers | https://learn.microsoft.com/azure/foundry/agents/how-to/tools/model-context-protocol | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Set up authentication for Model Context Protocol tools | https://learn.microsoft.com/azure/foundry/agents/how-to/mcp-authentication | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Migrate to the new agents developer experience | https://learn.microsoft.com/azure/foundry/agents/how-to/migrate | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What's new in Foundry Agent Service (classic) | https://learn.microsoft.com/azure/foundry-classic/agents/whats-new | Not exposed by Learn MCP retrieval | 2026-09-19 |
| About MCP servers in Azure API Management | https://learn.microsoft.com/azure/api-management/mcp-server-overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Expose REST API in API Management as an MCP server | https://learn.microsoft.com/azure/api-management/export-rest-mcp-server | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Model Context Protocol bindings for Azure Functions overview | https://learn.microsoft.com/azure/azure-functions/functions-bindings-mcp | Not exposed by Learn MCP retrieval | 2026-09-19 |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| The new Foundry portal is GA for defined core scenarios, but feature status varies and some Build and Operate capabilities remain preview or partial GA. | Foundry general availability | High; status must be checked per named capability and region. |
| A Foundry resource is the top-level governance boundary; projects provide development isolation; connected Storage, Key Vault, and AI Search resources retain separate governance boundaries. | Foundry architecture | High. |
| Prompt agents and hosted agents are the two current Foundry agent types. | Agents in Microsoft Foundry | High. A conventional service making a model call is a Product Group pattern, not a third Microsoft agent type. |
| A Toolbox exposes curated tools through a managed MCP-compatible endpoint and centralizes authentication, governance, observability, and versioning. | What is a toolbox? | High; individual toolbox features and tools can have different release status. |
| Agent, model, tool, private-network, and regional support must be validated together. | Agent Service limits, quotas, and regional support | High; tables are time-sensitive. |
| Foundry Agents (classic) are deprecated and Microsoft states they will retire on March 31, 2027. | What's new in Foundry Agent Service (classic) | High; migration scope and timing must be verified for each existing workload. |
| Foundry MCP connections support key-based, Microsoft Entra identity, OAuth identity passthrough, and unauthenticated patterns. | MCP authentication | High; suitability remains scenario- and policy-dependent. |
| API Management can expose managed REST operations as MCP tools or govern an existing remote MCP server. | APIM MCP overview | High. |
| API Management currently supports MCP tools but not resources or prompts, and MCP server capabilities are not supported in APIM workspaces. | APIM MCP overview; Expose REST API as MCP | High; time-sensitive limitation. |
| The APIM MCP documentation applies to Developer, Basic, Basic v2, Standard, Standard v2, Premium, and Premium v2 tiers. | Expose REST API as MCP | High; this does not establish Product Group entitlement or deployed tier. |
| The Azure Functions MCP extension supports tool, resource, and prompt triggers and documents Streamable HTTP as the preferred modern transport. | MCP bindings for Azure Functions | High; language, package, storage, and authorization prerequisites vary. |

## Limitations, previews, and deprecations

- Foundry GA does not imply that every tool, evaluator, monitoring view, networking experience, or deployment type is GA.
- Hub-based projects (classic) are not supported in the new Foundry portal.
- Microsoft states that Foundry Agents (classic) are deprecated and will retire on March 31, 2027.
- APIM's generated MCP surface is tool-only and unavailable in APIM workspaces at retrieval time.
- Functions MCP language/runtime support and minimum package versions vary; recheck before implementation.
- Source-page update dates were not present in the Learn MCP payload. Retrieval date is recorded; a reviewer can confirm page-history dates if needed.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Approved Foundry regions, resource topology, public/private network posture, and data boundaries | Infrastructure / Information Assurance |
| Permitted GA/preview policy for production and exception process | Architecture / Information Assurance |
| Existing Foundry classic or classic Agent workloads requiring migration before retirement | AI Platform |
| Default MCP authentication pattern by risk tier, including when user identity passthrough is required | Identity / Information Assurance |
| APIM instances, tiers, workspace use, owners, capacity, and MCP enablement | Platform / Infrastructure |
| Supported Functions languages, runtime baselines, hosting plan, storage, and authorization pattern | Platform Engineering |
| Foundry, model, APIM, Functions, monitoring, and connected-service entitlement and budget | Procurement / FinOps |

## Product Group decision impact

**implementation**

The existing candidate direction remains intact: Foundry is the candidate AI control/runtime plane, domain APIs remain authoritative, and MCP remains an edge protocol. Implementations must now validate capability-level release status, region/model/tool compatibility, authentication, APIM limitations and tier, and Functions prerequisites. No Product Group decision was promoted to approved status, so no ADR is required for this research-only update.

## Reference pages affected

- `02-ai-foundry/microsoft-foundry.md`
- `02-ai-foundry/agents-tools-toolboxes.md`
- `03-api-integration/model-context-protocol.md`
- `03-api-integration/api-management.md`
- `03-api-integration/functions-container-apps.md`
- `sources/microsoft-learn-catalog.md`

## Downstream impact note

Product Knowledge Base or Technical Documentation that uses Azure AI Foundry naming, classic hub projects, classic Agent APIs, assumes all Foundry capabilities are GA, assumes APIM exposes MCP resources/prompts, or uses HTTP+SSE as the default transport should be reviewed. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: Product Group Architecture / AI Platform (pending)

Review date: pending
