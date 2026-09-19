---
title: Policy, Defender, and Compliance
status: candidate
owner: Information Assurance and Cloud Governance
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Policy, Defender, and Compliance

## Azure Policy

Azure Policy evaluates and enforces resource configuration standards. Product teams must know inherited assignments and initiatives before selecting services or tiers.

Relevant controls may include:

- allowed regions and resource types;
- required tags;
- diagnostic settings;
- encryption and key requirements;
- public-network restrictions;
- private endpoint requirements;
- approved SKUs;
- managed identity;
- Defender enablement;
- resource naming and lifecycle controls.

Policy exceptions must be explicit, time-bounded, owned, and reviewed.

Azure Policy and Azure RBAC solve different problems. RBAC controls who can perform actions at a scope; Policy evaluates or changes resource state through effects such as audit, deny, modify, and deploy-if-not-exists. Existing noncompliant resources can require a remediation task rather than becoming compliant merely because a policy was assigned.

Use Policy exemptions—not undocumented exclusions—for approved exceptions. Record the assignment, affected definition, category, requester, approver, ticket, compensating control, and expiration. An expired exemption object remains as evidence, but the exemption is no longer honored.

## Defender for Cloud

Defender for Cloud provides security posture and workload protection capabilities depending on enabled plans. Transition must identify which plans are licensed, where coverage applies, alert routing, remediation ownership, and how findings enter engineering work.

Foundational CSPM provides baseline posture capabilities, while advanced posture and workload protections depend on additional Defender plans. Recommendation visibility and workload coverage are therefore plan- and resource-specific; do not infer coverage from the presence of the Defender for Cloud portal alone.

## Compliance evidence

Production readiness should be able to produce:

- architecture and data-flow diagrams;
- threat model or security review;
- identity and access matrix;
- policy compliance state and exceptions;
- vulnerability/dependency scan evidence;
- deployment and configuration provenance;
- logging/retention settings;
- recovery test evidence;
- model/agent evaluation and safety evidence;
- support and incident ownership.

## AI risk boundary

Platform security compliance does not prove agent safety or business fitness. AI products require additional evidence for prompt injection, tool misuse, data leakage, hallucination/grounding, human oversight, model/version change, and feedback handling.

Defender's regulatory-compliance view evaluates controls that can be assessed automatically. Grey or unavailable controls and manual evidence remain outside that automated conclusion; dashboard status is not certification.

## Foundry preview governance

Microsoft documents two different controls for Foundry preview features: a tag that suppresses preview surfaces in the portal and custom RBAC roles that block specified preview operations at the API level. Portal suppression is not an authorization control. The enterprise must decide whether preview use is prohibited, exception-based, or permitted by environment and must implement enforcement accordingly.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Azure Policy overview](https://learn.microsoft.com/azure/governance/policy/overview) | 2026-09-19 | Policy/RBAC distinction, assignments, compliance, remediation |
| [Azure Policy effects](https://learn.microsoft.com/azure/governance/policy/concepts/effect-basics) | 2026-09-19 | Audit, deny, modify, deploy, and evaluation behavior |
| [Azure Policy exemption structure](https://learn.microsoft.com/azure/governance/policy/concepts/exemption-structure) | 2026-09-19 | Exemption scope, categories, metadata, and expiration |
| [What is Microsoft Defender for Cloud?](https://learn.microsoft.com/azure/defender-for-cloud/defender-for-cloud-introduction) | 2026-09-19 | Foundational CSPM and plan-dependent protections |
| [Regulatory compliance standards in Defender for Cloud](https://learn.microsoft.com/azure/defender-for-cloud/concept-regulatory-compliance-standards) | 2026-09-19 | Automated assessment scope and unavailable controls |
| [Disable preview features in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/how-to/disable-preview-features) | 2026-09-19 | Portal suppression tag and API-level custom RBAC controls |
| [Azure Well-Architected Framework](https://learn.microsoft.com/azure/well-architected/) | 2026-09-19 | Cross-cutting workload review guidance |

Research detail and unresolved enterprise facts are recorded in [Source Record — Azure Security Controls](../sources/2026-09-19-security-controls.md).
