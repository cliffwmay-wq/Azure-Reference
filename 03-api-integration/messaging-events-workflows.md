---
title: Messaging, Events, and Workflows
status: candidate
owner: Product Group Platform
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Messaging, Events, and Workflows

## Choose by semantics

| Capability | Primary semantic | Use for |
|---|---|---|
| Service Bus queue | durable command/work item | reliable decoupled processing by a receiver |
| Service Bus topic/subscription | durable enterprise pub/sub | multiple subscribers with filters and delivery controls |
| Event Grid | event notification and routing | reacting to discrete state/resource changes |
| Event Hubs | high-throughput ordered stream | telemetry, device/event streams, replay by consumers |
| Logic Apps | managed integration workflow | connectors, visible orchestration, approvals, B2B/integration flows |
| Durable Functions | code-centric stateful orchestration | long-running application workflows with durable state |
| Data Factory/Fabric pipelines | batch/data movement | ingestion, transformation, scheduled data integration |

This table identifies a candidate by interaction semantics, not by product availability alone. Microsoft distinguishes Event Grid for reactive event routing, Event Hubs for time-ordered high-throughput streams, and Service Bus for enterprise transactional messages. The services can be combined when they fulfill different roles.

## Required messaging decisions

- command versus event versus stream;
- delivery guarantee and duplicate behavior;
- ordering scope;
- partition/session strategy;
- idempotency key;
- retry and backoff;
- poison/dead-letter handling;
- retention and replay;
- schema/version compatibility;
- identity and network access;
- trace/correlation propagation;
- operational ownership and recovery procedure.

Do not write "exactly once" as an end-to-end application guarantee. Even where a broker offers duplicate detection, transactions, sessions, or an exactly-once mode, producers and consumers still need stable identifiers, idempotent handling, and recovery tests across their complete transaction boundary.

## Time-sensitive compatibility

Microsoft retires the legacy `WindowsAzure.ServiceBus`, `Microsoft.Azure.ServiceBus`, and `com.microsoft.azure.servicebus` SDK libraries and ends SBMP protocol support on September 30, 2026. Inventory integrations now and migrate supported workloads to current Azure SDK libraries and AMQP before that date. Older libraries might continue to run afterward but will be unsupported and won't receive updates.

## Agent boundary

An agent may propose or initiate a governed command through a domain capability. It should not publish arbitrary messages directly into enterprise buses without validation, authorization, and a stable contract.

Use [Azure Service Bus documentation](https://learn.microsoft.com/en-us/azure/service-bus-messaging/), [Event Grid documentation](https://learn.microsoft.com/en-us/azure/event-grid/), [Event Hubs documentation](https://learn.microsoft.com/en-us/azure/event-hubs/), and [Logic Apps documentation](https://learn.microsoft.com/en-us/azure/logic-apps/) for current service behavior.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Choose between Event Grid, Event Hubs, and Service Bus](https://learn.microsoft.com/azure/service-bus-messaging/compare-messaging-services) | 2026-09-19 | Purpose, data model, delivery, ordering, transactions, scale, and combined use |
| [Logic Apps overview](https://learn.microsoft.com/azure/logic-apps/logic-apps-overview) | 2026-09-19 | Managed integration workflows, connectors, hybrid scenarios, and hosting choices |
| [Durable Functions overview](https://learn.microsoft.com/azure/durable-task/durable-functions/durable-functions-overview) | 2026-09-19 | Code-centric stateful orchestration and runtime-managed durability |
| [Use the legacy Service Bus .NET library with AMQP](https://learn.microsoft.com/azure/service-bus-messaging/service-bus-amqp-dotnet) | 2026-09-19 | Legacy SDK and SBMP retirement on September 30, 2026 |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
