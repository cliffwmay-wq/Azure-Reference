---
title: API Center and Capability Catalog
status: candidate
owner: Product Group Platform
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# API Center and Capability Catalog

Azure API Center is the candidate enterprise catalog for discovering and describing APIs and remote MCP servers regardless of where they are hosted.

This is a Product Group candidate, not a claim that an enterprise API Center exists or that its Standard plan is licensed.

## Purpose

API Center answers:

- What capabilities exist?
- Who owns them?
- Which environments and versions are available?
- What lifecycle and approval state applies?
- Where are definitions and documentation?
- Which MCP servers are approved for agent consumption?

API Center is a catalog, not necessarily the traffic gateway. API Management governs runtime traffic; API Center governs discovery and inventory.

Microsoft describes API Center as design-time governance and centralized discovery, while APIM is runtime governance and observability. API Center can inventory managed and unmanaged REST, GraphQL, gRPC, SOAP, WebSocket, Webhook, local/remote MCP-server, and A2A-agent assets.

## Minimum catalog metadata

- capability/API/MCP name and bounded domain;
- business and technical owner;
- description and consumers;
- lifecycle and approval state;
- environment and endpoint classification;
- API definition or MCP tool inventory;
- data classification;
- authentication method;
- network exposure;
- support/SLA reference;
- source repository and technical documentation;
- replacement/deprecation links.

Map these fields to API Center's API, version, definition, deployment, environment, and custom-metadata entities. Preserve the business-capability identity above any protocol-specific registration so REST, event, MCP, and replacement assets can be related without being conflated.

## MCP registry qualification

API Center can register local and remote MCP servers and expose discovery metadata. Registration establishes inventory and discoverability; it doesn't prove owner approval, tool safety, identity suitability, network reachability, data handling, runtime health, or support status. Those controls remain separate release and consumption gates.

The Free and Standard plans have different feature and scale limits. Microsoft support isn't available for the Free plan, and the API Center MCP endpoint for catalog discovery requires Standard. The current service limits page lists only the default workspace in both plans and finite limits for APIs, versions, metadata properties, requests, definition analysis, and integrated sources. Validate current plan, region, limits, private-access pattern, and cost before an enterprise selection.

## Relationship to product documentation

The catalog entry points to the current Product Technical Documentation. It should not contain the complete implementation narrative. The Azure Reference defines the catalog standard; product teams maintain their own catalog metadata as part of release readiness.

See [Azure API Center documentation](https://learn.microsoft.com/en-us/azure/api-center/).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [API Center overview](https://learn.microsoft.com/azure/api-center/overview) | 2026-09-19 | Design-time governance, discovery, plans, and APIM distinction |
| [API Center key concepts](https://learn.microsoft.com/azure/api-center/key-concepts) | 2026-09-19 | Asset types and API/version/definition/deployment/environment data model |
| [Register and discover MCP servers](https://learn.microsoft.com/azure/api-center/register-discover-mcp-server) | 2026-09-19 | Local/remote MCP inventory, registry metadata, and discovery |
| [Azure service limits — API Center](https://learn.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits#azure-api-center-limits) | 2026-09-19 | Free/Standard scale, workspace, metadata, request, analysis, and source limits |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
