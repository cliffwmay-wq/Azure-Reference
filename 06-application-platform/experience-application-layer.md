---
title: Experience and Application Layer
status: candidate
owner: Product Group Engineering
review_cycle: quarterly
source_posture: internal-governing
last_reviewed: 2026-09-19
---

# Experience and Application Layer

## Thin experience principle

> The client captures and displays. The service thinks.

Mobile, web, and conversational experiences should consume stable product capabilities through governed APIs. Secrets, system credentials, model orchestration, complex policy, and authoritative transactions remain server-side.

## Mobile responsibilities

- user authentication and token handling;
- capture of images, scans, location/context where approved;
- input validation and clear consent;
- bounded offline cache and queued work where required;
- presentation of structured decisions and uncertainty;
- human confirmation/correction;
- device/app telemetry without sensitive over-collection;
- version and environment awareness.

For managed operational tablets, document MDM deployment, Dev/UAT/Prod application identity, device permissions, offline behavior, update/rollback, and support diagnostics.

## Web/API hosting candidates

- Static Web Apps for appropriate static/front-end applications with managed integration.
- App Service for conventional managed web and API hosting.
- Container Apps for containerized services and jobs.
- Functions for event/request functions.
- Front Door/WAF for approved global entry, routing, acceleration, and web protection.

Selection follows [Service Selection](../01-architecture/service-selection.md), not a blanket standard.

## Current Microsoft qualifications

- Static Web Apps is oriented to repository-driven deployment of static front ends, with distributed static assets and integrated or linked API options. Its fit depends on repository, identity, API-region, plan, network, and enterprise CI/CD requirements.
- App Service is a managed host for web applications, mobile back ends, REST APIs, supported runtimes, and custom containers.
- Container Apps, Functions, and App Service overlap. Select by runtime, trigger model, hosting plan, networking, scale behavior, deployment model, regional support, and operating capability rather than by a generic "serverless" label.
- Azure Front Door Standard/Premium can provide global HTTP routing and WAF integration. Azure Front Door (classic) retires March 31, 2027; no new design should select the classic tier, and any existing dependency requires a migration owner and date.

## Contract requirements

Every client-facing capability defines:

- versioned request/response schema;
- authentication and authorization;
- validation and error codes;
- timeout/retry/idempotency;
- offline or unavailable behavior;
- accessibility and localization expectations;
- telemetry and correlation;
- compatibility and deprecation;
- sensitive-data display and caching rules.

## Structured intelligence result

Intelligent responses should provide machine-readable status, observations, evidence/provenance, confidence or uncertainty representation, recommended next action, human-review requirement, model/agent version, and correlation identifier. Narrative explanation is supplementary.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Static Web Apps overview](https://learn.microsoft.com/azure/static-web-apps/overview) | 2026-09-19 | Repository-driven deployment, distributed static hosting, and linked/integrated APIs |
| [App Service overview](https://learn.microsoft.com/azure/app-service/overview) | 2026-09-19 | Managed web, API, mobile-backend, runtime, and custom-container hosting |
| [Choose a compute option for microservices](https://learn.microsoft.com/azure/architecture/microservices/design/compute-options) | 2026-09-19 | Selection boundaries across Container Apps, Functions, App Service, and AKS |
| [Azure Front Door routing architecture](https://learn.microsoft.com/azure/frontdoor/front-door-routing-architecture) | 2026-09-19 | Standard/Premium routing stages, WAF influence, and classic-tier retirement |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
