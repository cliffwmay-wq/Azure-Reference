---
title: Source Record — Architecture, Integration, and Application Platform
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Architecture, Integration, and Application Platform

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate platform map, compute and integration selections, environment model, API catalog, experience layer, and legacy-modernization boundaries?

## Primary Microsoft Learn sources

### Architecture and environment

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Choose an Azure compute service | https://learn.microsoft.com/azure/architecture/guide/technology-choices/compute-decision-tree | 2026-09-19 | Compute decision factors, hosting models, and per-component selection |
| Choose a compute option for microservices | https://learn.microsoft.com/azure/architecture/microservices/design/compute-options | 2026-09-19 | Container Apps, AKS, Functions, and App Service selection boundaries |
| Resource organization | https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone/design-area/resource-org | 2026-09-19 | Naming, tagging, management groups, subscriptions, regions, and platform/workload separation |
| Manage application development environments in Azure landing zones | https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone/design-area/management-application-environments | 2026-09-19 | Subscription isolation, shared-subscription exceptions, governance, and management models |
| Anti-Corruption Layer pattern | https://learn.microsoft.com/azure/architecture/patterns/anti-corruption-layer | 2026-09-19 | Facade/adapter isolation, semantic translation, gradual modernization, and product neutrality |
| Gateway Routing pattern | https://learn.microsoft.com/azure/architecture/patterns/gateway-routing | 2026-09-19 | Layer-7 routing, single client endpoint, and backend decoupling |

### Compute and workflows

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Azure Functions hosting options | https://learn.microsoft.com/azure/azure-functions/functions-scale | 2026-09-19 | Hosting plans, scale/network/container differences, and legacy Consumption-plan status |
| App Service overview | https://learn.microsoft.com/azure/app-service/overview | 2026-09-19 | Managed web, API, mobile-backend, runtime, and custom-container hosting |
| What is Azure Logic Apps? | https://learn.microsoft.com/azure/logic-apps/logic-apps-overview | 2026-09-19 | Managed integration workflows, connectors, hybrid operation, and hosting choices |
| Durable Functions overview | https://learn.microsoft.com/azure/durable-task/durable-functions/durable-functions-overview | 2026-09-19 | Code-centric stateful workflows, runtime-managed state, checkpoints, retries, and recovery |

### Messaging and catalog

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Choose between Azure Event Grid, Event Hubs, and Service Bus | https://learn.microsoft.com/azure/service-bus-messaging/compare-messaging-services | 2026-09-19 | Event/message distinction, service purpose, delivery, ordering, transactions, scale, and combined use |
| Use legacy WindowsAzure.ServiceBus .NET framework library with AMQP 1.0 | https://learn.microsoft.com/azure/service-bus-messaging/service-bus-amqp-dotnet | 2026-09-19 | Legacy SDK and SBMP retirement on September 30, 2026 |
| What is Azure API Center? | https://learn.microsoft.com/azure/api-center/overview | 2026-09-19 | Design-time inventory/governance, discovery, plans, and APIM distinction |
| Azure API Center — key concepts | https://learn.microsoft.com/azure/api-center/key-concepts | 2026-09-19 | API types and API/version/definition/deployment/environment data model |
| Register and discover MCP servers in your API inventory | https://learn.microsoft.com/azure/api-center/register-discover-mcp-server | 2026-09-19 | Local/remote MCP registration, discovery, registry endpoint, and metadata |
| Azure subscription and service limits — API Center limits | https://learn.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits#azure-api-center-limits | 2026-09-19 | Free/Standard resource, workspace, metadata, request, analysis, and integrated-source limits |

### Experience layer

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| What is Azure Static Web Apps? | https://learn.microsoft.com/azure/static-web-apps/overview | 2026-09-19 | Repository-driven deployment, distributed static assets, and integrated/linked API options |
| Azure Front Door routing architecture | https://learn.microsoft.com/azure/frontdoor/front-door-routing-architecture | 2026-09-19 | Standard/Premium routing stages, WAF and rules influence, and classic-tier retirement |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| Microsoft compute guidance is a candidate-selection starting point; distinct workload components can use different compute services. | Compute decision tree | High; final fit depends on workload and enterprise constraints. |
| Microsoft positions Container Apps as a microservices starting point without cluster management, Functions for event-driven workloads, App Service for straightforward HTTP workloads, and AKS for direct Kubernetes and cluster control. | Microservices compute options | High; feature, region, quota, cost, and operating-model validation remains required. |
| The Azure Functions Consumption plan is labeled legacy; Microsoft recommends Flex Consumption for new serverless function apps. | Functions hosting options | High and time-sensitive; existing application migration and regional fit must be assessed. |
| Logic Apps is connector- and workflow-oriented; Durable Functions provides code-defined stateful workflows whose runtime manages checkpoints, retries, state, and recovery. | Logic Apps; Durable Functions | High; they overlap and can also be combined. |
| Event Grid, Event Hubs, and Service Bus target reactive routing, event streaming, and transactional messaging respectively. | Messaging-service comparison | High; detailed guarantees vary by tier and configuration. |
| Microsoft retires the legacy Service Bus SDK libraries and SBMP support on September 30, 2026. | Legacy Service Bus AMQP guidance | High and time-sensitive. |
| API Center is a design-time inventory/governance service; APIM is a distinct runtime gateway/governance service. | API Center overview | High. |
| API Center can inventory diverse API types plus local/remote MCP servers and A2A agents; its data model separates APIs, versions, definitions, deployments, environments, and metadata. | API Center key concepts | High. |
| API Center Free and Standard plans differ in support, capabilities, and limits. The catalog MCP endpoint requires Standard, and current limits list one default workspace for either plan. | API Center overview; service limits; MCP discovery | High but time-sensitive. |
| Azure landing-zone guidance prefers separate subscriptions for application environments but permits documented shared-subscription cases. | Application-environment guidance | High; the enterprise's actual topology is unknown. |
| The anti-corruption-layer pattern isolates modern semantics from external or legacy models; Azure products can help implement it but don't define its domain mapping. | Anti-Corruption Layer pattern | High. |
| Azure Front Door (classic) retires March 31, 2027 and shouldn't be selected for new work. | Front Door routing architecture | High and time-sensitive. |

## Limitations, previews, and deprecations

- Feature, tier, region, quota, scale, networking, availability-zone, runtime, SDK, and pricing details change independently; verify the exact selected configuration at implementation and review time.
- The Functions recommendation doesn't establish that Flex Consumption meets a workload's region, networking, runtime, cold-start, cost, or support requirements.
- Broker features don't establish end-to-end exactly-once business processing. Application idempotency, transaction boundaries, retry behavior, and recovery must be tested.
- The September 30, 2026 Service Bus deadline is imminent relative to this record's retrieval date; inventory and migration evidence are urgent.
- API Center registration is inventory, not security approval, runtime health, support entitlement, or authorization to consume an API, agent, or MCP tool.
- API Center plan features and limits are service facts, not evidence that the enterprise owns a Standard plan or has approved a region or topology.
- Landing-zone documents are framework guidance, not tenant facts. No subscription, management-group, network, policy, naming, tagging, or shared-service configuration was inferred.
- Front Door Standard/Premium still requires an enterprise edge, certificate, WAF, origin, logging, and ownership design; classic retirement doesn't select a replacement architecture by itself.
- Learn MCP retrieval didn't expose reliable page-update dates; retrieval dates are recorded instead.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Management groups, subscriptions, regions, environment boundaries, naming, tags, policies, shared-resource topology, and subscription-vending process | Cloud Platform / Infrastructure / Information Assurance |
| Approved compute services and plans, regions, quotas, network modes, runtime baselines, container registries, scale controls, and AKS support capability | Architecture / Platform Engineering / Infrastructure |
| Approved Service Bus, Event Grid, Event Hubs, Logic Apps, and Durable Functions tiers, namespaces, identities, networks, schemas, ownership, support, and recovery patterns | Integration Platform / Infrastructure / Production Engineering |
| Inventory of legacy Service Bus SDK and SBMP dependencies, migration owners, test evidence, and completion dates before September 30, 2026 | Application owners / Integration Platform |
| Whether API Center exists; plan, region, owners, RBAC, network access, metadata schema, ingestion sources, portal, MCP registry, approval states, and lifecycle workflow | API Platform / Architecture / Information Assurance / Procurement |
| Approved web/mobile hosting, edge, WAF, identity, device-management, accessibility, localization, offline, caching, and release patterns | Application Platform / UX / Information Assurance |
| Inventory of Azure Front Door classic profiles and a Standard/Premium or alternate migration plan before March 31, 2027 | Infrastructure / Application owners |
| Legacy-system interfaces, business owners, domain mappings, identities, routes, encryption, transaction semantics, maintenance windows, support, and replacement roadmaps | Enterprise Applications / Infrastructure / Domain owners |

## Product Group decision impact

**architectural and operational**

The candidate direction remains bounded: select compute per component; separate transactional messages, reactive events, and streams; catalog assets at design time and govern traffic at runtime; isolate environments according to enterprise landing-zone decisions; and protect modern domain contracts from legacy semantics. The research adds urgent migration checks for Service Bus SDK/SBMP and Front Door classic plus a current Functions hosting-plan correction. It does not select an enterprise subscription topology, API Center plan, integration namespace, compute SKU, web edge, or legacy interface.

No ADR was created because no material Product Group selection changed. An ADR is required if reviewers promote API Center, a shared integration platform, an environment topology, a default compute platform, or a Front Door migration target into an approved standard.

## Reference pages affected

- `01-architecture/platform-map.md`
- `01-architecture/reference-patterns.md`
- `01-architecture/service-selection.md`
- `01-architecture/environment-resource-model.md`
- `03-api-integration/messaging-events-workflows.md`
- `03-api-integration/api-center.md`
- `06-application-platform/experience-application-layer.md`
- `06-application-platform/legacy-hybrid-integration.md`
- `sources/microsoft-learn-catalog.md`
- `sources/research-backlog.md`

## Downstream impact note

Review product documentation that selects the Functions legacy Consumption plan for new applications, uses a retired Service Bus SDK or SBMP, treats broker features as an end-to-end exactly-once guarantee, conflates API Center with an API gateway, treats API/MCP catalog registration as approval, assumes a tenant subscription topology, exposes legacy schemas as domain contracts, or depends on Azure Front Door classic. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: Architecture / Platform Engineering / Integration Platform / Infrastructure / Information Assurance / Enterprise Applications / Procurement (pending)

Review date: pending
