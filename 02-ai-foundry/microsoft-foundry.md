---
title: Microsoft Foundry
status: candidate
owner: Product Group AI Platform
review_cycle: monthly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Microsoft Foundry

Microsoft Foundry is the Product Group's primary candidate environment for discovering and deploying supported models, developing agents, attaching governed tools and knowledge, evaluating behavior, and observing AI application execution.

Microsoft documents the new Foundry portal and its core scenarios as generally available. GA is capability-specific: several Build and Operate experiences remain preview or partial GA, so production designs must verify the status of every required component rather than infer readiness from the portal's overall status.

## Product Group role

Foundry is an AI application and agent control/runtime plane. It is not:

- the system of record;
- the sole repository for prompts, contracts, tests, or architecture decisions;
- a replacement for domain APIs;
- automatic Information Assurance approval for every catalog model;
- the default custom computer-vision training platform when Azure Machine Learning better fits the lifecycle.

## Core objects to document

| Object | Function | Product Group record |
|---|---|---|
| Foundry resource/project | Governance boundary and development isolation | purpose, owner, environment, region, access, network |
| Model deployment | Callable model capacity/version | model, version, region, quota, data posture, evaluation |
| Agent | Versioned instructions, model, tools, behavior | source commit, release, contracts, eval set, owner |
| Connection | Governed access to an external resource | identity, scopes, secret owner, target environment |
| Tool/Toolbox | Executable capability or curated collection | schema, risk, permission, approval, downstream owner |
| Knowledge/search connection | Retrieval capability | sources, index, permissions, freshness, evaluation |
| Evaluation/traces | Quality and execution evidence | dataset, metric, threshold, release, retention |

## Project boundaries

Create projects around a bounded product or related operational domain—not every experiment and not the entire enterprise. A project needs coherent ownership, data classification, network posture, connections, release cadence, and support.

Separate experimentation from production. Production agents and model deployments must reference versioned source and approved evaluations.

Microsoft defines the Foundry resource as the top-level governance boundary and projects as development boundaries within it. Connected services such as Storage, Key Vault, and Azure AI Search remain separate Azure resources with their own networking, access, and compliance controls.

## Source-of-truth rule

Git and the controlled documentation/specification repository remain authoritative for:

- business intent and specifications;
- constitutions and inherited constraints;
- prompt and tool definitions;
- structured schemas;
- evaluation datasets and thresholds;
- deployment definitions;
- architecture decisions.

Foundry holds deployed runtime objects and operational evidence. Every deployed asset should be traceable to its source version.

## Minimum production evidence

- business owner and technical owner;
- bounded purpose and prohibited uses;
- selected model and deployment details;
- instructions and tool inventory;
- structured input/output contracts;
- golden cases and failure taxonomy;
- security/data-flow review;
- cost and capacity expectation;
- release and rollback procedure;
- monitoring, support, and retirement plan.

## Current Microsoft qualifications

- Foundry projects support defined core GA scenarios, but individual tools, evaluators, monitoring, networking experiences, and deployment types can have different release status.
- The new portal does not support hub-based projects (classic). Existing classic workloads require an explicit migration assessment.
- Foundry Agents (classic) are deprecated and Microsoft states they will retire on March 31, 2027.
- Agent, model, tool, private-network, and region support must be checked together for the intended deployment region.
- Model usage, deployment type, quota, and connected Azure services are separate cost and capacity dimensions; tenant entitlement and approved budgets remain enterprise facts.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [What is Microsoft Foundry?](https://learn.microsoft.com/azure/foundry/what-is-foundry) | 2026-09-19 | Platform purpose, prompt and hosted agents, unified management scope |
| [Microsoft Foundry architecture](https://learn.microsoft.com/azure/foundry/concepts/architecture) | 2026-09-19 | Foundry resource hierarchy, project boundary, separately governed connected services |
| [Microsoft Foundry general availability](https://learn.microsoft.com/azure/foundry/concepts/general-availability) | 2026-09-19 | GA scope, feature-specific preview status, classic-project qualification |
| [Foundry Agent Service limits, quotas, and regional support](https://learn.microsoft.com/azure/foundry/agents/concepts/limits-quotas-regions) | 2026-09-19 | Region, model, tool, and private-network compatibility checks |
| [Plan and manage costs for Microsoft Foundry](https://learn.microsoft.com/azure/foundry/concepts/manage-costs) | 2026-09-19 | Usage-dependent billing and connected-service cost dimensions |
| [What's new in Foundry Agent Service (classic)](https://learn.microsoft.com/azure/foundry-classic/agents/whats-new) | 2026-09-19 | Classic-agent deprecation and March 31, 2027 retirement date |

Research detail and unresolved enterprise facts are recorded in [Source Record — Microsoft Foundry and MCP](../sources/2026-09-19-foundry-mcp.md).
