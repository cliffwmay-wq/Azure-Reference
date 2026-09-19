---
title: Research and Validation Backlog
status: active
owner: Product Group Documentation
review_cycle: monthly
source_posture: working-register
last_reviewed: 2026-09-19
---

# Research and Validation Backlog

This backlog records bounded work needed to turn candidate guidance into approved enterprise guidance.

| Priority | Domain | Question | Required reviewer | Result location | Status |
|---|---|---|---|---|---|
| 1 | Tenant/licensing | Which Azure, Foundry, Fabric, Purview, Defender, Entra, GitBook, and support entitlements are active? | Cloud/Procurement | Transition inventory | open |
| 1 | Landing zone | Which subscriptions, regions, policies, networking, naming, tagging, and diagnostic controls apply? | Infrastructure/IA | Environment model | open |
| 1 | Service Bus retirement | Which applications still use `WindowsAzure.ServiceBus`, `Microsoft.Azure.ServiceBus`, `com.microsoft.azure.servicebus`, or SBMP, and will they migrate and prove recovery before September 30, 2026? | Application owners/Integration Platform | Migration inventory and product evidence | open |
| 1 | Front Door retirement | Do any workloads use Azure Front Door classic, and what approved target, owner, test plan, and cutover date will complete migration before March 31, 2027? | Infrastructure/Application owners | Edge inventory and migration ADR/runbook | open |
| 1 | Foundry privacy | What model, region, logging, retention, and network settings are approved for production calls? | IA/AI Platform | Foundry pages | open |
| 1 | Model governance | Which model providers, exact models/versions, deployment types, regions, processing geographies, terms, quotas, update policies, and retirement owners are approved? | AI Platform/IA/Procurement | Models page and transition inventory | open |
| 1 | Evaluation and safety | Which datasets, human-review rubrics, judge models, thresholds, languages, red-team scenarios, trace controls, and residual-risk authorities form the production release gate? | AI Platform/IA/Product | Evaluation page and product evidence | open |
| 1 | Identity governance | Which Foundry roles, agent identities, managed identities, PIM, Conditional Access, access reviews, and on-behalf-of patterns are approved by environment and risk tier? | Identity/IA | Identity page and security source record | open |
| 1 | Network security | What inbound, outbound, DNS, delegated-subnet, private-endpoint, trusted-service-bypass, hybrid-routing, and public-access exception patterns are approved? | Infrastructure/IA | Network page and environment model | open |
| 1 | Key management | What vault topology, RBAC model, purge protection, rotation, recovery, customer-managed-key, and Foundry Key Vault connection pattern is required? | Identity/IA/Platform | Secrets page and transition inventory | open |
| 1 | APIM | Existing instances, tiers, owners, capacity, policies, and shared capability model? | Applications/Infrastructure | APIM page/inventory | open |
| 1 | API catalog | Does an enterprise API Center exist, and what plan, region, metadata, RBAC, network, ingestion, portal, MCP-registry, approval, and lifecycle model applies? | API Platform/Architecture/IA/Procurement | API Center page and platform ADR | open |
| 1 | Authoritative data | Which systems, business owners, data contracts, semantic owners, reconciliation rules, and derived copies are authoritative? | Enterprise Data/Product data owners | Data responsibility model and product Technical Documents | open |
| 1 | Redis retirement | Which Azure Cache for Redis instances, tiers, owners, dependencies, feature gaps, and reservations exist, and what tested migration plan completes before the applicable 2027 or 2028 retirement? | Data Platform/Application owners/Procurement | Data inventory and migration ADR/runbook | open |
| 1 | Operational stores | Which relational, NoSQL, and cache platforms, engines/versions, tiers, regions, HA, backup, network, encryption, maintenance, monitoring, support, and cost patterns are approved? | Data Platform/Infrastructure/IA | Operational stores page and service-selection ADR | open |
| 1 | Search and retrieval | Which AI Search tier, regions, API/SDK versions, embedding models, permission pattern, deletion SLA, capacity, and monitoring are approved? | Knowledge Platform/Infrastructure/IA | AI Search page and product evidence | open |
| 1 | Storage protection | Which Blob/ADLS account topology, hierarchical namespace, redundancy, network, encryption, immutability, retention, backup, and recovery controls are approved? | Data Platform/Infrastructure/IA/Records | Object storage page and environment inventory | open |
| 1 | Fabric and OneLake | Are Fabric and OneLake the enterprise analytical plane, and which capacities, regions, domains, workspaces, security, shortcut, mirroring, lineage, and cost patterns are approved? | Enterprise Data/Fabric admins/Procurement | Fabric page and platform ADR | open |
| 1 | Observability and audit | Which workspaces, regions, diagnostic policies, SIEM/export destinations, audit schemas, correlation, sampling, access, retention, deletion, and cost controls are required? | Infrastructure/IA/SOC/Records | Observability page and environment inventory | open |
| 1 | Reliability and support | Which SLO/SLI, error-budget, RTO/RPO, recovery-test, incident-severity, support-hours, communication, and escalation classes apply by risk tier? | Product/Production Engineering/IA | Reliability page and product runbooks | open |
| 1 | Cost and capacity | Which billing scopes, price sheets, budgets, tags, commitments, licenses, quotas, tested capacity, regional fallbacks, and approvers apply? | FinOps/Procurement/Platform owners | Cost page and environment inventory | open |
| 2 | MCP | Approved remote servers, authentication, registry, allowlists, and approval policy? | IA/Architecture | MCP/API Center pages | open |
| 2 | Policy and Defender | Which initiatives/effects/exemptions and Defender plans are active, and who owns findings, alerts, exceptions, remediation, and compliance evidence? | Cloud Governance/IA/SOC | Policy page and transition inventory | open |
| 2 | Custom ML | Is Azure Machine Learning the supported custom ML platform, and what workspace, registry, compute, endpoint, monitoring, and production-data-collection patterns are approved? | ML Platform/Architecture/IA | Azure ML page and service-selection ADR | open |
| 2 | Purview governance | Which Purview account, licensing, region, domains, collections, roles, scans, classifications, lineage, data quality, and access-request patterns are approved? | Enterprise Data/IA/Purview admins | Purview page and governance operating model | open |
| 2 | Delivery | Which Git host, pipeline, module registry, runner, environment, federated identity, checks, approvers, artifact/evidence retention, and emergency-change path are approved? | Engineering/Platform Engineering/IA | Delivery page and delivery ADR | open |
| 2 | Application platform | Which web/mobile hosting, edge/WAF, identity, MDM, accessibility, localization, offline, caching, and release patterns are supported? | Application Platform/UX/IA | Application-layer page and service-selection ADR | open |
| 2 | Legacy integration | Which legacy interfaces, owners, domain mappings, identities, routes, transaction rules, maintenance windows, and replacement roadmaps are authoritative? | Enterprise Applications/Infrastructure/Domain owners | Legacy-integration page and product Technical Documents | open |
| 2 | GitBook | Plan, access model, Git sync direction, spaces, and publishing owners? | Documentation/Procurement | GitBook page | open |
| 3 | Service selection | Validate Functions vs Container Apps vs App Service defaults against enterprise support | Architecture | ADR/service selection | open |

## Completion rule

Close an item only when the answer is cited or linked, owned, dated, and incorporated into the applicable reference page or ADR.
