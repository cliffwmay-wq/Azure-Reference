---
title: Observability and Audit
status: candidate
owner: Product Group Production Engineering
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Observability and Audit

Azure Monitor, Application Insights, and Log Analytics are the primary candidates for platform telemetry, application performance, traces, logs, metrics, alerts, and dashboards.

This is a candidate Product Group stack. Workspace topology, SIEM integration, regions, retention, access, sampling, and audit requirements remain enterprise decisions.

## Current Microsoft qualifications

- Azure Monitor brings together metrics, logs, traces, and events, but data collection isn't automatic for every signal. Platform metrics and Activity Log entries are collected by Azure; most resource logs require a diagnostic setting.
- Diagnostic settings are configured per resource and select categories and destinations. Destination, region, firewall, latency, and service-specific category support must be validated. Enabling a setting doesn't reconstruct events that weren't previously collected.
- Activity Log records Azure control-plane changes and normally doesn't capture reads or service data-plane activity. Azure retains Activity Log events for 90 days by default; longer retention requires export through a diagnostic setting.
- Application Insights stores application telemetry in a Log Analytics workspace. Custom fields, prompts, responses, tool arguments, user identifiers, and exception data can introduce personal or sensitive data.
- Sampling reduces volume and cost by dropping telemetry. Adaptive sampling is enabled by default for some Application Insights SDKs and Azure Functions. Sampling configuration must be recorded, queries must account for it, and mandatory audit events must use a separately assured path.
- Log Analytics supports analytics and long-term retention with table-specific behavior. Retention, query availability, deletion, archive, and cost must be designed by data class rather than assumed from a workspace default.

## End-to-end correlation

One operational request should be traceable across:

```text
Client → APIM → service/function → agent/model/tool → integration → system of record
```

Propagate a correlation identifier and capture meaningful dependency spans without logging secrets or unrestricted sensitive bodies.

## Telemetry classes

| Class | Examples |
|---|---|
| Platform | CPU/memory, scaling, availability, throttling |
| Application | request rate, latency, failures, dependencies |
| Integration | queue depth, dead letters, retries, backend timeouts |
| AI runtime | model/agent version, tokens, tool calls, evaluation signals |
| Business operation | capability outcome, human review, accepted/corrected result |
| Security/audit | caller, authorization, approval, write result, policy exception |

## Logging rules

- Default to metadata and structured safe fields.
- Classify prompt, response, image, document, and tool arguments before logging them.
- Redact secrets and sensitive identifiers.
- Define retention, access, export, and deletion.
- Separate debugging convenience from production audit requirements.
- Record sampling decisions; do not sample away mandatory audit events.
- Treat log schemas, data-collection rules, transformations, diagnostic settings, alerts, workbooks, and retention as versioned configuration.
- Prove that each required audit event reaches its destination and remains queryable for the mandated period.

## Minimum dashboards and alerts

- availability and error rate;
- latency percentiles by capability;
- dependency and backend failures;
- queue/dead-letter health;
- model/tool failure and throttling;
- cost/capacity indicators;
- security and policy events;
- business quality/human correction trend where appropriate.

See [Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/) and [Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Azure Monitor overview](https://learn.microsoft.com/azure/azure-monitor/fundamentals/overview) | 2026-09-19 | Unified telemetry platform, workspace types, queries, dashboards, alerts, and agent observability |
| [Diagnostic settings](https://learn.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) | 2026-09-19 | Per-resource collection, resource-log defaults, destinations, regional and firewall constraints |
| [Activity Log](https://learn.microsoft.com/azure/azure-monitor/platform/activity-log) | 2026-09-19 | Control-plane scope, data-plane distinction, read limitations, latency, and 90-day retention |
| [Application Insights overview](https://learn.microsoft.com/azure/azure-monitor/app/app-insights-overview) | 2026-09-19 | Application telemetry, OpenTelemetry, transactions, dependencies, availability, and AI-agent views |
| [Application Insights sampling](https://learn.microsoft.com/azure/azure-monitor/app/sampling-classic-api) | 2026-09-19 | Adaptive, fixed-rate, and ingestion sampling; SDK defaults and query implications |
| [Manage personal data in Azure Monitor Logs](https://learn.microsoft.com/azure/azure-monitor/logs/personal-data-mgmt) | 2026-09-19 | Personal-data inventory, minimization, transformations, access, export, deletion, and purge |
| [Log Analytics data retention](https://learn.microsoft.com/azure/azure-monitor/logs/data-retention-configure) | 2026-09-19 | Analytics versus long-term retention, table plans, query availability, and deletion behavior |

Research detail and unresolved enterprise facts are recorded in [Source Record — Operations and Delivery](../sources/2026-09-19-operations-delivery.md).
