---
title: Source Record — Azure Security Controls
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Azure Security Controls

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate guidance for identity, authorization, network isolation, secrets and keys, Azure Policy, Defender for Cloud, and Foundry security controls?

## Primary Microsoft Learn sources

| Page title | URL | Page date | Retrieved |
|---|---|---|---|
| What is managed identities for Azure resources? | https://learn.microsoft.com/entra/identity/managed-identities-azure-resources/overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Azure role-based access control? | https://learn.microsoft.com/azure/role-based-access-control/overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Role-based access control for Microsoft Foundry | https://learn.microsoft.com/azure/foundry/concepts/rbac-foundry | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Agent identity concepts in Microsoft Foundry | https://learn.microsoft.com/azure/foundry/agents/concepts/agent-identity | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Conditional Access for workload identities | https://learn.microsoft.com/entra/identity/conditional-access/workload-identity | Not exposed by Learn MCP retrieval | 2026-09-19 |
| How to configure network isolation for Microsoft Foundry | https://learn.microsoft.com/azure/foundry/how-to/configure-private-link | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Azure Private Link? | https://learn.microsoft.com/azure/private-link/private-link-overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Secure your Azure Key Vault | https://learn.microsoft.com/azure/key-vault/general/security-features | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Azure Key Vault soft-delete overview | https://learn.microsoft.com/azure/key-vault/general/soft-delete-overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Provide Key Vault access with Azure RBAC | https://learn.microsoft.com/azure/key-vault/general/rbac-guide | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Configure network security for Azure Key Vault | https://learn.microsoft.com/azure/key-vault/general/network-security | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Set up an Azure Key Vault connection in Microsoft Foundry | https://learn.microsoft.com/azure/foundry/how-to/set-up-key-vault-connection | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Azure Policy overview | https://learn.microsoft.com/azure/governance/policy/overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Azure Policy definitions effect basics | https://learn.microsoft.com/azure/governance/policy/concepts/effect-basics | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Azure Policy exemption structure | https://learn.microsoft.com/azure/governance/policy/concepts/exemption-structure | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Microsoft Defender for Cloud? | https://learn.microsoft.com/azure/defender-for-cloud/defender-for-cloud-introduction | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Regulatory compliance standards in Defender for Cloud | https://learn.microsoft.com/azure/defender-for-cloud/concept-regulatory-compliance-standards | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Disable preview features in Microsoft Foundry | https://learn.microsoft.com/azure/foundry/how-to/disable-preview-features | Not exposed by Learn MCP retrieval | 2026-09-19 |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| Managed identities remove the need to manage credentials; system-assigned identities share a resource lifecycle, while user-assigned identities have independent lifecycles and can be reused. | Managed identities overview | High; service support and authorization remain separate requirements. |
| An Azure RBAC assignment combines a security principal, role definition, and scope. | Azure RBAC overview | High. |
| Foundry RBAC roles require Entra authentication; key authentication does not apply granular RBAC role restrictions. | Foundry RBAC | High; tenant policy is unverified. |
| Unpublished Foundry agents use a shared project agent identity; published agents receive unique identities that require downstream permission assignments. | Agent identity concepts | High; lifecycle is specific to current Foundry Agent Service. |
| Conditional Access for workload identities targets eligible service principals, does not cover managed identities, and requires applicable Workload Identities Premium licensing to create or modify policies. | Conditional Access for workload identities | High; tenant licensing and policy are unknown. |
| Foundry network isolation has separate inbound, resource-outbound, and Agent-client-outbound paths; connected Azure resources require their own network controls. | Foundry network isolation; Foundry architecture | High; region and feature support are time-sensitive. |
| Private endpoints require correct private DNS resolution; public DNS visibility alone does not establish whether public data-plane access is allowed. | Foundry network isolation; Key Vault network security | High. |
| Key Vault control-plane and data-plane authorization are separate; Microsoft recommends RBAC and warns against legacy access policies for critical workloads. | Key Vault security; Key Vault RBAC | High; migration can cause outages if roles are not staged. |
| Key Vault soft delete is enabled by default for new vaults, while purge protection is not; recovery does not restore associated RBAC assignments or Event Grid subscriptions. | Key Vault soft-delete overview | High. |
| Without a customer Key Vault connection, Foundry stores connection details in a Microsoft-managed Key Vault outside the customer subscription; a customer vault connection has one-per-resource and migration limitations. | Foundry Key Vault connection | High; selected enterprise pattern remains unknown. |
| Azure Policy governs resource state and is distinct from RBAC; effect choice and remediation determine whether it audits, blocks, changes, or deploys configuration. | Azure Policy overview; effects | High. |
| Policy exemptions can record waivers or mitigations and an expiration; expired exemption objects remain for evidence but no longer apply. | Policy exemption structure | High. |
| Defender capabilities and recommendation coverage vary by enabled plan; Foundational CSPM does not imply all workload protections are enabled. | Defender for Cloud overview | High; actual plans and coverage are enterprise facts. |
| Defender regulatory views assess automatable controls; unavailable or manual controls are not automatically determined compliant. | Defender regulatory compliance | High; dashboard state is not certification. |
| Foundry's preview-suppression tag hides portal surfaces, while custom RBAC roles can block specified preview API operations. | Disable preview features in Foundry | High; enterprise preview policy is unknown. |

## Limitations, previews, and deprecations

- Foundry roles have undergone naming changes; use stable role IDs in automation and verify current role semantics.
- Conditional Access coverage differs between human users, service principals, managed identities, and agent identities.
- Foundry network controls, Agent VNet injection, and connected-resource support must be checked for the intended region and feature set.
- Key Vault ABAC conditions for secret data actions are documented as preview and were not adopted as a Product Group standard.
- Network Security Perimeter availability and service support must be verified before selection.
- Policy compliance can require remediation tasks for existing resources and can lag assignment or resource changes.
- Defender recommendations, protection, retention, and alerting depend on enabled plans and resource coverage.
- Learn MCP retrieval did not expose source-page update dates; retrieval dates are recorded instead.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Approved Foundry roles, agent identity lifecycle, managed-identity patterns, privileged access, access reviews, and on-behalf-of requirements | Identity / Information Assurance |
| Entra Workload ID licensing and Conditional Access coverage for service principals | Identity / Procurement |
| Approved production inbound/outbound design, private DNS ownership, delegated subnets, egress filtering, hybrid routing, and public-access exceptions | Infrastructure / Information Assurance |
| Whether trusted-service firewall bypasses are permitted and how they are inventoried and reviewed | Infrastructure / Information Assurance |
| Required Key Vault boundaries, RBAC model, purge protection, retention, rotation, recovery tests, and customer-managed-key use | Identity / Information Assurance / Platform |
| Whether Foundry must use a customer-managed Key Vault connection and how its one-per-resource lifecycle is governed | AI Platform / Information Assurance |
| Inherited Azure Policy initiatives, effects, parameters, remediation identities, exemptions, owners, and exception workflow | Cloud Governance |
| Enabled Defender plans, covered subscriptions/resources, data collection, retention, alert routing, remediation SLAs, and SOC ownership | Information Assurance / SOC / Procurement |
| Production policy for Foundry preview features and technical enforcement method | Architecture / Information Assurance |

## Product Group decision impact

**security**

The candidate principles remain valid, but implementation guidance is now explicitly qualified by identity type, authorization mode, network path, vault recovery behavior, policy effect, and Defender plan. No enterprise setting or Product Group decision was inferred from Microsoft product capability, and no page was promoted beyond candidate status.

## Reference pages affected

- `05-security-governance/identity-access.md`
- `05-security-governance/network-isolation.md`
- `05-security-governance/secrets-key-management.md`
- `05-security-governance/policy-defender-compliance.md`
- `sources/microsoft-learn-catalog.md`
- `sources/research-backlog.md`

## Downstream impact note

Product Technical Documentation should be reviewed if it assumes Conditional Access covers managed identities, uses Foundry account keys as equivalent to RBAC, treats a private endpoint as complete network isolation, assumes Key Vault purge protection is on by default, treats project connections as user-private secret storage, or treats Defender regulatory status as certification. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: Information Assurance / Identity / Infrastructure / Cloud Governance (pending)

Review date: pending
