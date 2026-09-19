---
title: Identity and Access
status: candidate
owner: Information Assurance and Platform
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Identity and Access

Microsoft Entra ID is the identity plane for people, applications, agents, and Azure workloads. Authorization uses the narrowest practical combination of Azure RBAC, application roles/scopes, domain authorization, and resource-specific permissions.

## Identity types

| Identity | Use |
|---|---|
| Human user | interactive access and attributable approval |
| Group | role assignment and lifecycle management |
| App registration/service principal | application identity where required |
| System-assigned managed identity | identity bound to one Azure resource lifecycle |
| User-assigned managed identity | reusable workload identity with independent lifecycle |
| Agent identity | supported bounded identity for agent runtime/tool access |

Prefer managed identity over stored credentials for Azure-to-Azure access.

Microsoft distinguishes system-assigned managed identities, whose lifecycle is tied to one Azure resource, from user-assigned managed identities, which are independent Azure resources and can be assigned to multiple supported resources. That technical capability does not by itself justify sharing an identity across unrelated products or trust boundaries.

## Authorization layers

1. Authenticate the caller.
2. Authorize access to the gateway or service.
3. Authorize the named business capability.
4. Apply domain scope such as terminal, customer, shipment, or operating role.
5. Authorize downstream resource access using workload identity.
6. Require approval for consequential actions.

Passing APIM authentication does not automatically authorize an operational transaction.

## Required records

- caller populations and workload identities;
- token audience, scopes, and roles;
- RBAC assignments and scope;
- conditional access implications;
- managed-identity ownership;
- privileged access and break-glass procedure;
- joiner/mover/leaver and access-review process;
- service-to-service and on-behalf-of behavior;
- audit identity propagated to downstream transactions.

## Agent rule

An agent must not gain broader authority than the initiating user or approved workload unless a separately governed service identity and purpose explicitly justify it. Tool calls need attributable caller, agent/version, tool, authorization result, and approval state.

## Current Microsoft qualifications

- An Azure RBAC assignment combines a security principal, role definition, and scope. Foundry supports scopes including the Foundry resource, project, and—in limited scenarios—an individual agent.
- Foundry RBAC roles apply with Microsoft Entra authentication. Microsoft states that key-based authentication grants access without RBAC's granular role restrictions. Under this candidate guidance, production key use requires explicit enterprise review rather than being treated as equivalent to RBAC.
- Unpublished Foundry agents authenticate to tools through a shared project agent identity. A published agent receives a unique agent identity, and required downstream RBAC permissions must be assigned to that new identity.
- Conditional Access for workload identities can target eligible service principals, but the documented feature does not cover managed identities. It also has licensing requirements. Conditional Access, PIM, access reviews, and workload-identity governance must therefore be designed by identity type rather than assumed to apply uniformly.
- Correct token audience and downstream authorization remain required even after a caller or agent has authenticated.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Managed identities for Azure resources](https://learn.microsoft.com/entra/identity/managed-identities-azure-resources/overview) | 2026-09-19 | Credential elimination, identity types, lifecycle, and sharing characteristics |
| [Azure role-based access control](https://learn.microsoft.com/azure/role-based-access-control/overview) | 2026-09-19 | Principal-role-scope authorization model |
| [RBAC for Microsoft Foundry](https://learn.microsoft.com/azure/foundry/concepts/rbac-foundry) | 2026-09-19 | Foundry scopes, built-in roles, Entra-versus-key authorization qualification |
| [Agent identity concepts in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/agents/concepts/agent-identity) | 2026-09-19 | Agent identity lifecycle, token audience, tool authentication, and RBAC |
| [Conditional Access for workload identities](https://learn.microsoft.com/entra/identity/conditional-access/workload-identity) | 2026-09-19 | Service-principal scope, managed-identity exclusion, and licensing qualification |

Research detail and unresolved enterprise facts are recorded in [Source Record — Azure Security Controls](../sources/2026-09-19-security-controls.md).
