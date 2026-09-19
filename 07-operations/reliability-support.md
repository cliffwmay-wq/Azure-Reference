---
title: Reliability and Support
status: candidate
owner: Product Group Production Engineering
review_cycle: quarterly
source_posture: internal-governing
last_reviewed: 2026-09-19
---

# Reliability and Support

## Current Microsoft qualifications

- Azure Well-Architected guidance distinguishes workload SLOs, measured SLIs, contractual SLAs, recovery time objective, and recovery point objective. Product owners and business stakeholders set workload targets; a Microsoft service SLA is an input, not the workload SLO.
- Reliability targets apply to critical user and business flows across all dependencies and should cover availability, correctness, and recovery. Component availability percentages alone don't prove the end-to-end outcome.
- Reliability testing should exercise complete flows against SLO, RTO, and RPO pass/fail criteria. Recovery evidence must include detection, response, dependency restoration, failover, and failback—not only a platform feature being enabled.
- Azure Status provides broad public status, Service Health provides personalized service/region communications and planned maintenance, and Resource Health reports individual resource condition. These signals supplement, but don't replace, application health, synthetic transactions, and business outcome monitoring.
- Reliability patterns such as retry, circuit breaker, bulkhead, queue buffering, idempotent consumer, and deployment stamps require workload-specific tradeoff analysis. Applying a pattern by name doesn't prove reliability.

## Reliability record

Every production capability defines:

- service-level objective and user consequence;
- dependency map and failure modes;
- regional and zone posture;
- capacity, quotas, and throttling;
- timeout/retry/circuit/idempotency behavior;
- graceful degradation and offline/fallback behavior;
- backup, restore, and disaster-recovery expectations;
- release rollback;
- monitoring and alert thresholds;
- support owner, escalation, and vendor dependency;
- recovery testing cadence.

Record the critical flow, SLI formula, measurement source, target and window, exclusions, error budget, RTO, RPO, dependency assumptions, support hours, escalation path, and authority to declare or close an incident.

## AI-specific degradation

Define what happens when:

- a model deployment is unavailable or throttled;
- the agent cannot obtain a tool result;
- retrieval finds no trustworthy evidence;
- structured output validation fails;
- safety control blocks the request;
- latency exceeds the operational window;
- model or tool behavior changes after an update.

The product must distinguish unavailable, insufficient evidence, low confidence, not authorized, and actual negative findings.

## Support tiers

Assign ownership for:

- user/device/application support;
- platform/runtime support;
- domain/API support;
- data/knowledge quality;
- model/agent quality;
- infrastructure/network;
- Information Assurance incident response;
- Microsoft/vendor escalation.

## Production readiness gate

Architecture review, security/data review, tested deployment, performance/capacity evidence, golden-case evaluation, operational dashboard, alerts, runbook, ownership, communication, rollback, and recovery evidence must be complete at the level appropriate to risk.

This is a candidate Product Group gate. Enterprise Production Engineering, Information Assurance, and product owners must approve reliability tiers, incident severity, support hours, communications, RTO/RPO classes, and exception authority.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Define reliability targets](https://learn.microsoft.com/azure/well-architected/reliability/metrics) | 2026-09-19 | SLO, SLI, SLA, RTO, RPO, availability, correctness, recovery, and stakeholder responsibility |
| [Monitor workload reliability](https://learn.microsoft.com/azure/well-architected/reliability/monitoring) | 2026-09-19 | Health models, critical-flow monitoring, synthetic transactions, correlation, and retained evidence |
| [Reliability testing](https://learn.microsoft.com/azure/well-architected/reliability/reliability-test) | 2026-09-19 | End-to-end failure testing, chaos/fault injection, recovery targets, error budgets, and cadence |
| [Azure Service Health](https://learn.microsoft.com/azure/service-health/overview) | 2026-09-19 | Azure Status, personalized Service Health, Resource Health, maintenance, advisories, and alerts |
| [Azure Resource Health](https://learn.microsoft.com/azure/service-health/resource-health-overview) | 2026-09-19 | Individual-resource health signals, status categories, support, and SLA evidence context |
| [Reliability design patterns](https://learn.microsoft.com/azure/well-architected/reliability/design-patterns) | 2026-09-19 | Reliability patterns and their availability, isolation, recovery, and integrity tradeoffs |

Research detail and unresolved enterprise facts are recorded in [Source Record — Operations and Delivery](../sources/2026-09-19-operations-delivery.md).
