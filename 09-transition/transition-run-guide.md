---
title: Transition Run Guide
status: approved-baseline
owner: Product Group
review_cycle: active-during-transition
source_posture: operational-run-guide
---

# Transition Run Guide

This guide turns the portable Azure Reference into an enterprise-valid Product Group source of truth.

## Phase 1 — Establish ownership and storage

- Select the authoritative Git repository and default branch.
- Assign Product Group owner, editors, reviewers, and GitBook publishers.
- Confirm visibility and sensitivity classification.
- Add CODEOWNERS/review rules if supported.
- Decide issue/change-request workflow.
- Record the source-of-truth relationship between Git and GitBook.

## Phase 2 — Capture tenant and commercial reality

Complete the environment/licensing inventory for:

- tenant, management groups, subscriptions, resource groups, regions;
- Azure agreement and chargeback/showback;
- active SKUs, reservations, quotas, and support plan;
- Foundry accounts/projects, model availability, quotas, and approved regions;
- APIM instances/tiers/capacity;
- Fabric capacities/workspaces;
- Purview and Defender capabilities;
- Entra licensing, PIM, Conditional Access, and workload identity standards;
- GitHub/Azure DevOps and GitBook plans;
- third-party model/data/connector terms.

Do not turn unverified assumptions into reference facts. Mark unknowns with an owner and due date.

## Phase 3 — Map enterprise controls

- Azure Policy assignments and initiatives;
- landing-zone requirements;
- naming/tagging standards;
- approved IaC and pipeline patterns;
- network topology, private DNS, ingress/egress, hybrid connectivity;
- Key Vault and certificate standards;
- logging workspaces, retention, SIEM, audit requirements;
- data classification, Purview, retention, and regional constraints;
- vulnerability, dependency, container, and open-source scanning;
- architecture and IA review processes.

## Phase 4 — Inventory current capabilities

- APIs and APIM operations;
- MCP servers and tool surfaces;
- Foundry projects, agents, Toolboxes, models, connections, evaluations;
- Azure ML workspaces, registries, endpoints, datasets;
- storage accounts, databases, AI Search, Fabric/OneLake assets;
- Functions, Container Apps, App Services, Logic Apps;
- Service Bus, Event Grid, Event Hubs, Data Factory;
- dashboards, alerts, runbooks, owners, and support paths.

Register approved APIs and MCP servers in API Center if adopted.

## Phase 5 — Validate reference decisions

For each candidate page:

1. Research current Microsoft Learn through the connected Learn MCP.
2. Add enterprise facts and limitations.
3. Review with the responsible enterprise owner.
4. Resolve candidate/deferred/standard status.
5. Record material selections through ADRs.
6. Mark the page `approved-baseline` only when the owner agrees.

## Phase 6 — Build the first product fork

- Select the greenfield reference implementation.
- Create its Knowledge Base and Technical Documentation from templates.
- Link inherited Azure reference pages.
- Record real services, contracts, environments, security, data, evaluations, deployment, support, and licensing.
- Capture gaps discovered during delivery back into the Azure Reference.

This is the learning loop:

```text
Principle → Reference implementation → Learn → Synthesize → Standardize
```

## Phase 7 — Publish and operate

- Configure GitBook spaces and access.
- Validate navigation and link behavior.
- Publish approved downstream content.
- Establish monthly fast-changing service review and quarterly platform review.
- Track stale pages and unresolved unknowns.
- Review downstream impact when a platform decision changes.

## Transition completion criteria

- owners and review workflow established;
- tenant/licensing inventory complete enough for selected products;
- applicable enterprise controls documented;
- source catalog refreshed through Learn MCP;
- core reference pages approved;
- first product successfully forked;
- GitBook publication path tested;
- support and refresh cadence operating.

