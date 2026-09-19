---
title: Cost, Capacity, and Licensing
status: draft
owner: Product Group with Cloud/Procurement
review_cycle: monthly-during-transition
source_posture: tenant-validation-required
last_reviewed: 2026-09-19
---

# Cost, Capacity, and Licensing

This page defines what must be recorded. Actual enterprise pricing, agreements, reservations, quotas, and entitlements are intentionally added after transition into the company environment.

## Current Microsoft qualifications

- Microsoft Cost Management analyzes, allocates, monitors, and optimizes costs across supported scopes, but measured usage, rated cost, credits, and invoices pass through different processing stages and cadences.
- Budgets provide thresholds and notifications. Microsoft states that resources aren't affected and consumption isn't stopped when a threshold is exceeded. Cost and usage data is typically delayed 8–24 hours and budgets are evaluated every 24 hours, so budgets aren't a real-time safety boundary.
- Azure quotas are assigned limits on countable resources or operations. Microsoft explicitly documents for App Service that quota doesn't guarantee physical SKU capacity in a region at a specific time. The Product Group applies that distinction as a conservative validation rule for each selected service and SKU.
- Reservations are billing discounts for matching usage, not reserved runtime capacity. They are commitments tied to product, scope, region, term, and utilization assumptions.
- Microsoft documents a reservation exchange-policy change effective February 1, 2027 for newly purchased reservations on products covered by savings plans. Procurement must review current terms at purchase time rather than relying on historical flexibility.
- Cost allocation, inherited tags, and showback reports can improve accountability but don't change the Microsoft invoice or establish contractual ownership.

## Cost model

For each capability identify:

- fixed baseline cost;
- consumption unit and expected volume;
- scale driver;
- nonproduction cost;
- network/egress cost;
- logging and retention cost;
- data storage and transaction cost;
- model token/inference/training cost;
- search index capacity;
- support/license dependency;
- cost owner and allocation tags;
- alert and shutdown/scale-down policy.

## Capacity model

Record current quotas, requested quotas, regional capacity, rate limits, concurrency, throughput, storage growth, latency target, seasonal/operational peaks, and lead time to expand.

Maintain separate evidence for:

- configured quota and actual usage;
- service limit and tested application throughput;
- approved quota increase and deployable regional/SKU capacity;
- modeled demand, measured demand, and reserved/committed usage;
- scale-up lead time, fallback region/SKU, and financial approval.

## Licensing inventory categories

- Azure agreement/subscription model;
- APIM tier and capacity;
- Foundry model billing and quotas;
- Azure ML compute and endpoint costs;
- Fabric capacity and workspace access;
- Purview capability/licensing;
- Defender plans;
- Entra/PIM/Conditional Access requirements;
- GitHub/Azure DevOps and GitBook plans;
- third-party model, connector, data, or MCP terms;
- Microsoft support plan.

## Rule

Do not place changing price numbers into architectural guidance without date, region, currency, SKU, source, and owner. Prefer linking the validated enterprise pricing record.

Do not present a budget alert, cost forecast, quota approval, reservation, or savings-plan recommendation as a hard spend cap or capacity guarantee.

Use the [Environment and Licensing Inventory template](../templates/environment-licensing-inventory-template.md) during transition.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Microsoft Cost Management](https://learn.microsoft.com/azure/cost-management-billing/costs/overview-cost-management) | 2026-09-19 | Cost analysis, allocation, exports, alerts, commerce pipeline, rating, and invoice stages |
| [Create and manage budgets](https://learn.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-create-budgets) | 2026-09-19 | Notification behavior, no automatic consumption stop, evaluation cadence, and data latency |
| [Cost alerts](https://learn.microsoft.com/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending) | 2026-09-19 | Budget, credit, spending-quota, and anomaly-alert behavior and permissions |
| [Azure quotas overview](https://learn.microsoft.com/azure/quotas/quotas-overview) | 2026-09-19 | Subscription quotas, usage alerts, adjustable/non-adjustable limits, and request review |
| [App Service quota versus regional capacity](https://learn.microsoft.com/troubleshoot/azure/app-service/troubleshoot-non-zone-redundant-quota-requests) | 2026-09-19 | Service-specific distinction between subscription quota and deployable physical SKU capacity |
| [Azure Reservations](https://learn.microsoft.com/azure/cost-management-billing/reservations/save-compute-costs-reservations) | 2026-09-19 | Billing-discount behavior, commitments, scope, matching usage, and utilization analysis |
| [Reservation exchange-policy changes](https://learn.microsoft.com/azure/cost-management-billing/reservations/reservation-exchange-policy-changes) | 2026-09-19 | February 1, 2027 exchange change and reservation-versus-savings-plan qualification |

Research detail and unresolved enterprise facts are recorded in [Source Record — Operations and Delivery](../sources/2026-09-19-operations-delivery.md).
