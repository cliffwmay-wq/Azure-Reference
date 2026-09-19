---
title: Purpose, Scope, and Boundaries
status: approved-baseline
owner: Product Group
review_cycle: quarterly
source_posture: internal-governing
---

# Purpose, Scope, and Boundaries

## Purpose

The Azure Reference gives the Product Group a shared, transparent view of the Azure platform applicable to product work. It translates Microsoft capabilities into stable architectural language, clarifies where each component belongs, and makes platform decisions discoverable before product implementation begins.

It exists to reduce three forms of waste:

- rediscovering the same Azure service for each product;
- allowing prototypes to silently become unsupported production architecture;
- mixing Microsoft product facts, enterprise decisions, and product implementation details in one document.

## In scope

- Microsoft Foundry, models, agents, tools, toolboxes, evaluation, tracing, and safety.
- Azure Machine Learning for custom model lifecycle and MLOps.
- API Management, Functions, Container Apps, API Center, MCP, messaging, events, and workflows.
- Storage, operational databases, AI Search, Fabric/OneLake, data movement, and Purview.
- Entra ID, managed identities, RBAC, Key Vault, networking, Policy, Defender, and audit controls.
- Application delivery patterns for mobile, web, APIs, hybrid connectivity, and legacy integration.
- Observability, reliability, cost, licensing placeholders, environments, IaC, release, and support.
- Documentation provenance and controlled derivation into Knowledge Base and Technical Documentation.

## Out of scope

- Reproducing Microsoft Learn articles.
- Product roadmaps, requirements, backlogs, or specifications.
- Product-specific endpoints, data schemas, prompts, model versions, or operational procedures.
- Final enterprise security approval or legal/compliance conclusions.
- Tenant-specific licensing assumptions before validation.
- An exhaustive catalog of every Azure service.

## Inclusion rule

An Azure capability belongs in this reference when at least one of the following is true:

1. It is part of an approved or candidate Product Group reference pattern.
2. It supplies a cross-product platform capability.
3. Teams must understand why it is selected, deferred, or prohibited.
4. Its configuration materially affects security, data handling, reliability, cost, or support.

Services that do not meet these tests remain in Microsoft Learn until a real product need creates a reason to interpret them.

## Authority model

| Question | Authoritative source |
|---|---|
| What does the Microsoft service support today? | Microsoft Learn and Azure service documentation |
| Which service and pattern does the Product Group approve? | This Azure Reference plus recorded architecture decisions |
| How does a particular product implement it? | Product Technical Documentation |
| How does a user or operator perform a task? | Product Knowledge Base or operational runbook |
| Is a capability licensed and approved in the enterprise tenant? | Transition inventory and enterprise system owners |

## Completion standard

“Complete” means every applicable platform responsibility has a documented home, owner, decision state, and source path. It does not mean copying every option, property, API version, or tutorial from Microsoft Learn.

