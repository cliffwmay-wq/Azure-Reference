---
title: Service Selection
status: candidate
owner: Product Group Architecture
review_cycle: quarterly
source_posture: synthesized-reference
last_reviewed: 2026-09-19
---

# Service Selection

## Compute

| Need | Default candidate | Select when | Reconsider when |
|---|---|---|---|
| Short event/API function | Azure Functions | Event-driven, bursty, bounded execution | Complex runtime, persistent process, or container dependency dominates |
| Containerized service | Azure Container Apps | Custom runtime, HTTP/service workload, jobs, scale-to-zero | Full Kubernetes control is truly required |
| Managed web/API app | App Service | Conventional web/API hosting with managed platform features | Container-first orchestration or event function is a better fit |
| Workflow integration | Logic Apps | Connector-rich, visible business/integration workflow | Core domain logic or high-throughput code path |
| Kubernetes platform | AKS | Proven orchestration requirement and operating capability | Selected only for perceived future scale |

AKS is deferred by default for early Product Group capabilities. Complexity must be justified by a real workload and operating model.

These are Product Group starting candidates, not enterprise standards. Microsoft recommends evaluating each compute component separately; a workload can legitimately combine services.

## Current compute qualifications

- For microservices, Microsoft positions Container Apps as the starting point when built-in application primitives and per-app scaling are needed without direct cluster management. Select AKS when direct Kubernetes API access, custom mesh behavior, or fine-grained cluster control is a demonstrated requirement.
- Functions fits trigger-led, event-driven components. The hosting plan determines scaling, networking, container support, cost, and other behavior.
- Microsoft now labels the Functions Consumption plan as legacy and recommends Flex Consumption for new serverless function apps. Existing apps require a documented migration assessment; Flex Consumption availability and feature fit still require region and workload validation.
- App Service remains a managed host for web applications, mobile back ends, REST APIs, and supported custom containers. Container Apps is a stronger candidate when revision-based container operation, event-driven scaling, or microservice primitives dominate.
- Logic Apps is a managed integration-workflow platform with cloud, on-premises, and hybrid connectors. Durable Functions is a code-centric stateful-workflow extension whose runtime manages checkpoints, retries, state, and recovery. Hosting model, connector, network, execution, and support requirements determine the choice.

## Integration

| Interaction | Preferred starting point |
|---|---|
| Synchronous business capability | REST API behind APIM |
| Durable command or work queue | Service Bus queue |
| Publish/subscribe business message | Service Bus topic |
| Discrete Azure/resource event | Event Grid |
| High-volume telemetry stream | Event Hubs |
| Data movement and transformation | Data Factory/Fabric Data Factory |
| Human-visible connector workflow | Logic Apps |
| Portable agent tool exposure | MCP through a governed endpoint |

## Data

| Need | Preferred starting point |
|---|---|
| Images, documents, large objects | Blob Storage / ADLS Gen2 |
| Relational product state | Azure SQL or Azure Database for PostgreSQL |
| Globally distributed flexible JSON with predictable access paths | Cosmos DB |
| Search, vector, hybrid retrieval | Azure AI Search |
| Analytics lake and enterprise data plane | Fabric OneLake or governed enterprise platform |
| Secrets, keys, certificates | Key Vault; never a general data store |

## Intelligence

| Need | Preferred starting point |
|---|---|
| Hosted models and agent orchestration | Microsoft Foundry |
| Custom ML/CV training and MLOps | Azure Machine Learning |
| Knowledge retrieval | Azure AI Search plus governed source system |
| Deterministic policy | Domain service/rules implementation, not model recall |
| Cross-runtime tool portability | MCP at the edge of stable APIs |

## Selection record

Every production selection records: use case, alternatives, why selected, data classification, identity, network, estimated cost driver, support owner, exit strategy, and linked ADR.

Record the exact service plan/SKU, region, runtime or SDK version, scale floor and ceiling, network mode, quota, availability-zone posture, deployment model, and retirement dependencies. Validate current support before relying on a feature shown in a comparison table.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Choose an Azure compute service](https://learn.microsoft.com/azure/architecture/guide/technology-choices/compute-decision-tree) | 2026-09-19 | Compute decision factors, hosting models, and per-component selection |
| [Choose a compute option for microservices](https://learn.microsoft.com/azure/architecture/microservices/design/compute-options) | 2026-09-19 | Container Apps, AKS, Functions, and App Service selection boundaries |
| [Azure Functions hosting options](https://learn.microsoft.com/azure/azure-functions/functions-scale) | 2026-09-19 | Hosting-plan behavior, Flex Consumption recommendation, and legacy Consumption qualification |
| [App Service overview](https://learn.microsoft.com/azure/app-service/overview) | 2026-09-19 | Managed web, API, mobile-backend, runtime, and container hosting |
| [Logic Apps overview](https://learn.microsoft.com/azure/logic-apps/logic-apps-overview) | 2026-09-19 | Managed workflows, connectors, hybrid integration, and hosting choices |
| [Durable Functions overview](https://learn.microsoft.com/azure/durable-task/durable-functions/durable-functions-overview) | 2026-09-19 | Code-based stateful workflows, checkpoints, retries, state, and recovery |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
