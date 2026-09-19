---
title: Environment and Resource Model
status: candidate
owner: Product Group Architecture
review_cycle: quarterly
source_posture: tenant-validation-required
last_reviewed: 2026-09-19
---

# Environment and Resource Model

## Environment separation

The starting model is Development, Test/UAT, and Production, with stronger isolation as data sensitivity and operational consequence increase.

Microsoft landing-zone guidance says separate subscriptions are the preferred isolation boundary for application environments, while allowing a documented shared-subscription exception when workload and platform teams agree it is appropriate. This reference therefore requires separation outcomes but does not invent the enterprise subscription topology.

| Concern | Development | Test/UAT | Production |
|---|---|---|---|
| Data | synthetic or approved masked | controlled representative | authoritative production data |
| Identity | developer and dev workload identities | test identities | managed workload and approved operator identities |
| Network | controlled developer access | production-like validation | private and restricted by default |
| Model/agent | experimental versions | release candidate | immutable approved version |
| Tool permissions | read/sandbox | production-like with nonproduction targets | least privilege, approvals, audited writes |
| Observability | debugging emphasis | validation evidence | SLO, security, audit, and support evidence |

## Resource organization

Tenant facts must be added during transition, but the reference requires explicit decisions for:

- management group and subscription placement;
- resource groups by lifecycle and ownership;
- region and paired-region posture;
- naming and tagging standards;
- production/nonproduction separation;
- shared platform versus product-owned resources;
- network topology and private DNS ownership;
- diagnostic settings and log destinations;
- budget, chargeback/showback, and cost tags;
- break-glass and privileged access.

## Shared versus product-owned

Shared services may include APIM, API Center, monitoring workspaces, registries, private DNS, policy assignments, shared model gateways, and approved knowledge services. Product-owned resources include product APIs, storage, queues, agents, search indexes, model deployments, dashboards, and runbooks unless enterprise ownership dictates otherwise.

Sharing is not automatically desirable. A shared service must have an owner, capacity model, tenant isolation, change contract, outage communication, and cost allocation.

Azure landing-zone guidance distinguishes central, application-team, and shared management models. Record responsibility separately for the Azure resource, its configuration, the hosted workload, security findings, operations, data, and cost; the party that provisions a shared service isn't automatically the owner of every workload using it.

## Promotion model

Deploy configuration and code through versioned automation. Promote immutable artifacts and declarative definitions; do not reproduce production by manual portal memory. Environment-specific values are injected through approved configuration and secret mechanisms.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Resource organization](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone/design-area/resource-org) | 2026-09-19 | Naming, tagging, subscriptions, management groups, regions, and workload/platform separation |
| [Manage application development environments](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/landing-zone/design-area/management-application-environments) | 2026-09-19 | Environment isolation, subscription preference, exceptions, and management models |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
