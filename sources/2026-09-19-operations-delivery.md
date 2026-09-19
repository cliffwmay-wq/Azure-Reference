---
title: Source Record — Operations and Delivery
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Operations and Delivery

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate guidance for observability, audit, reliability, support, cost, capacity, licensing, infrastructure as code, and controlled delivery?

## Primary Microsoft Learn sources

### Observability and audit

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Azure Monitor overview | https://learn.microsoft.com/azure/azure-monitor/fundamentals/overview | 2026-09-19 | Metrics, logs, traces, events, workspace types, queries, dashboards, alerts, and agent monitoring |
| Diagnostic settings in Azure Monitor | https://learn.microsoft.com/azure/azure-monitor/platform/diagnostic-settings | 2026-09-19 | Per-resource collection, categories, destinations, resource-log defaults, region and firewall constraints |
| Activity Log in Azure Monitor | https://learn.microsoft.com/azure/azure-monitor/platform/activity-log | 2026-09-19 | Control-plane scope, data-plane distinction, read limitations, latency, and 90-day default retention |
| Application Insights overview | https://learn.microsoft.com/azure/azure-monitor/app/app-insights-overview | 2026-09-19 | OpenTelemetry, application transactions, dependencies, availability, failures, and AI-agent views |
| Sampling in Application Insights | https://learn.microsoft.com/azure/azure-monitor/app/sampling-classic-api | 2026-09-19 | Sampling types, SDK defaults, retained relationships, cost, and query implications |
| Manage personal data in Azure Monitor Logs | https://learn.microsoft.com/azure/azure-monitor/logs/personal-data-mgmt | 2026-09-19 | Data minimization, transformations, access, export, deletion, purge, and personal-data inventory |
| Manage Log Analytics data retention | https://learn.microsoft.com/azure/azure-monitor/logs/data-retention-configure | 2026-09-19 | Analytics and long-term retention, table plans, search jobs, and deletion behavior |

### Reliability and support

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Architecture strategies for defining reliability targets | https://learn.microsoft.com/azure/well-architected/reliability/metrics | 2026-09-19 | SLO, SLI, SLA, MTTR, RTO, RPO, availability, correctness, recovery, and stakeholder ownership |
| Architecture strategies for monitoring workload reliability | https://learn.microsoft.com/azure/well-architected/reliability/monitoring | 2026-09-19 | Health models, critical-flow monitoring, synthetic transactions, correlation, and evidence retention |
| Architecture strategies for reliability testing | https://learn.microsoft.com/azure/well-architected/reliability/reliability-test | 2026-09-19 | End-to-end tests, fault injection, RTO/RPO criteria, failover/failback, error budgets, and cadence |
| What is Azure Service Health? | https://learn.microsoft.com/azure/service-health/overview | 2026-09-19 | Azure Status, personalized Service Health, Resource Health, maintenance, advisories, and alerts |
| Azure Resource Health overview | https://learn.microsoft.com/azure/service-health/resource-health-overview | 2026-09-19 | Individual-resource health, status categories, support context, and SLA evidence |
| Architecture design patterns that support reliability | https://learn.microsoft.com/azure/well-architected/reliability/design-patterns | 2026-09-19 | Reliability patterns and availability, isolation, recovery, and integrity tradeoffs |

### Cost, capacity, and licensing

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| What is Microsoft Cost Management? | https://learn.microsoft.com/azure/cost-management-billing/costs/overview-cost-management | 2026-09-19 | Analysis, allocation, exports, alerts, commerce processing, rated cost, credits, and invoices |
| Create and manage budgets | https://learn.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-create-budgets | 2026-09-19 | Alerts, no automatic stop, cost-data latency, evaluation cadence, scopes, and reset behavior |
| Use cost alerts to monitor usage and spending | https://learn.microsoft.com/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending | 2026-09-19 | Budget, credit, department-spending, and anomaly alert types and permissions |
| Azure quotas overview | https://learn.microsoft.com/azure/quotas/quotas-overview | 2026-09-19 | Subscription quotas, usage alerts, adjustable and non-adjustable quotas, and requests |
| Troubleshoot non-zone-redundant quota requests for Azure App Service | https://learn.microsoft.com/troubleshoot/azure/app-service/troubleshoot-non-zone-redundant-quota-requests | 2026-09-19 | App Service-specific distinction between subscription quota and physical regional SKU capacity |
| What are Azure Reservations? | https://learn.microsoft.com/azure/cost-management-billing/reservations/save-compute-costs-reservations | 2026-09-19 | Billing discounts, commitments, scope, matching usage, and utilization analysis |
| Changes to the Azure reservation exchange policy | https://learn.microsoft.com/azure/cost-management-billing/reservations/reservation-exchange-policy-changes | 2026-09-19 | February 1, 2027 policy change, savings-plan qualification, refunds, and trade-in context |

### Delivery and infrastructure as code

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| What is Bicep? | https://learn.microsoft.com/azure/azure-resource-manager/bicep/overview | 2026-09-19 | Declarative and idempotent deployment, API-version support, consistency, and what-if integration |
| Bicep what-if | https://learn.microsoft.com/azure/azure-resource-manager/bicep/deploy-what-if | 2026-09-19 | Non-mutating predictions, permissions, validation levels, nested expansion, and limitations |
| Define approvals and checks | https://learn.microsoft.com/azure/devops/pipelines/process/approvals?view=azure-devops | 2026-09-19 | Resource-owner checks, protected resources, approvals, branch control, external checks, and locks |
| Use GitHub Actions to connect to Azure | https://learn.microsoft.com/azure/developer/github/connect-from-azure | 2026-09-19 | OIDC, managed identity, service-principal secret option, and recommendation status |
| Deploy to Azure infrastructure with GitHub Actions | https://learn.microsoft.com/devops/deliver/iac-github-actions | 2026-09-19 | Pull-request validation, IaC previews, protected environments, reviewed deployment, and federation |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| Platform metrics and Activity Log events are collected by Azure, while most resource logs require per-resource diagnostic settings. | Diagnostic settings; Activity Log | High; category and destination support varies by resource. |
| Activity Log focuses on control-plane operations, doesn't normally capture reads, and is retained for 90 days unless exported. | Activity Log | High. |
| Application telemetry and custom log fields can contain personal data; minimization before ingestion is Microsoft's preferred technical approach. | Personal-data management; Application Insights | High; classification remains an enterprise responsibility. |
| Sampling can drop application telemetry and is enabled by default for some SDK/runtime combinations. | Application Insights sampling | High; required audit evidence needs an assured unsampled path. |
| Workload reliability targets are business-owned, measurable across critical flows and dependencies, and separate from vendor SLAs. | Reliability targets and monitoring | High. |
| Recovery must be tested end to end against RTO/RPO, including detection, response, dependencies, failover, and failback. | Reliability testing | High; test safety and scope are workload-specific. |
| Azure Status, Service Health, and Resource Health provide different platform signals and don't replace workload monitoring. | Service Health; Resource Health | High. |
| Cost budgets alert but don't stop resources; reported cost can lag usage by 8–24 hours and budget evaluation occurs daily. | Budget tutorial | High; not a real-time spend control. |
| Reservations are billing discounts, not runtime-capacity reservations. | Azure Reservations | High. |
| Azure quotas constrain permitted resource use; App Service documentation explicitly distinguishes quota from physical regional SKU capacity. The Product Group uses this as a conservative validation rule for other selected services. | Quotas overview and App Service capacity guidance | High for App Service; inferred operational rule elsewhere and must be verified per service/SKU. |
| Reservation exchange rules change on February 1, 2027 for affected new purchases. | Reservation exchange-policy changes | High and time-sensitive. |
| Bicep is declarative and idempotent, but also exposes preview resource API versions. | Bicep overview | High; IaC doesn't change feature support status. |
| What-if predicts changes without applying them and has documented analysis limits. | Bicep what-if | High; human and automated review remain required. |
| Azure DevOps can place resource-owner approvals/checks outside YAML, while GitHub Actions can use OIDC federation instead of stored client secrets. | Azure Pipelines approvals; GitHub Azure connection | High; enterprise platform selection is unknown. |

## Limitations, previews, and deprecations

- Resource-log categories, diagnostic destinations, latency, retention, and regional behavior vary by Azure service.
- Observability data can be incomplete because of missing configuration, sampling, throttling, transformation, ingestion failure, retention expiry, or access restrictions.
- Dashboards and platform health signals are evidence, not proof that critical user flows or business outcomes are healthy.
- Reliability patterns and service features don't establish an SLO or recovery capability until the complete workload is measured and tested.
- Cost data and budgets are delayed; budgets don't stop consumption.
- Price, SKU, quota, capacity, agreement, tax, currency, reservation, savings-plan, licensing, and support terms are time- and tenant-sensitive.
- The documented reservation exchange-policy change takes effect after this retrieval date and must be rechecked before commitment.
- Bicep's support for an API version doesn't establish that the underlying feature is GA or enterprise-approved.
- What-if is predictive and can omit or misclassify changes in documented edge cases.
- Azure DevOps and GitHub controls differ; equivalent evidence and separation of duties must be mapped after platform selection.
- Learn MCP retrieval didn't expose reliable page-update dates; retrieval dates are recorded instead.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Log Analytics and Azure Monitor workspace topology, regions, diagnostic policy, SIEM/export destinations, data classes, access, sampling, retention, deletion, and cost ownership | Infrastructure / Information Assurance / SOC / Records Management |
| Required audit-event schema, unsampled delivery path, correlation standard, evidence retention, and audit reviewer | Information Assurance / Product / Production Engineering |
| Reliability tiers, business SLOs/SLIs, error budgets, RTO/RPO classes, recovery-test cadence, incident severity, support hours, communications, and exception authority | Product owners / Production Engineering / Information Assurance |
| Microsoft support plan, authorized support contacts, escalation workflow, data-sharing approval, and vendor dependencies | Cloud / Procurement / Support leadership |
| Billing agreement, subscriptions, cost scopes, price sheets, currency, tax, budgets, tags, allocation, reservations/savings plans, licenses, entitlements, and approvers | Cloud FinOps / Procurement / Finance |
| Service/SKU quotas, measured capacity, regional availability, lead time, fallback, performance target, and expansion owner | Platform owners / Infrastructure / Production Engineering |
| Approved Git host, pipeline platform, module registry, runners, environments, deployment identities, federation, required checks, approvers, artifacts, evidence retention, and emergency-change path | Engineering / Platform Engineering / Information Assurance |

## Product Group decision impact

**operational**

The candidate direction remains bounded: Azure Monitor/Application Insights/Log Analytics for telemetry; business-owned SLO and recovery evidence; Cost Management for delayed financial visibility rather than hard control; and versioned IaC with reviewed, least-privilege delivery. No enterprise workspace, support plan, billing agreement, commitment, quota, CI/CD platform, or production gate was inferred.

## Reference pages affected

- `07-operations/observability-audit.md`
- `07-operations/reliability-support.md`
- `07-operations/cost-capacity-licensing.md`
- `07-operations/delivery-iac-change.md`
- `sources/microsoft-learn-catalog.md`
- `sources/research-backlog.md`

## Downstream impact note

Review product documentation that assumes all resource logs are collected automatically, relies on Activity Log for data-plane audit, allows sampling to remove required audit events, equates a vendor SLA with a workload SLO, claims recovery without end-to-end tests, treats budgets as spend caps, treats reservations as capacity guarantees, assumes quota approval proves deployability, or treats Bicep what-if as a deployment guarantee. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: Production Engineering / Infrastructure / Information Assurance / SOC / FinOps / Procurement / Engineering (pending)

Review date: pending
