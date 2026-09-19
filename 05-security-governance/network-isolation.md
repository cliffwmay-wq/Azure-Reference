---
title: Network Isolation
status: candidate
owner: Infrastructure and Information Assurance
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Network Isolation

Network design limits exposure after identity and authorization; it does not replace them.

## Capabilities

- virtual networks and subnets;
- network security groups;
- private endpoints and Private Link;
- service endpoints where approved;
- Azure Firewall and egress controls;
- private DNS zones and resolution;
- VPN/ExpressRoute hybrid connectivity;
- WAF/Front Door/Application Gateway as applicable;
- service-specific firewall rules.

## Product Group expectation

Production data, model, search, and integration services should use private connectivity where required by enterprise policy and supported by the chosen service/tier. Every public endpoint needs explicit justification, authenticated access, and exposure controls.

This is a candidate Product Group expectation, not a confirmed enterprise mandate. Infrastructure and Information Assurance must confirm the required pattern, supported regions and tiers, approved egress, and exception process.

## Foundry network boundaries

Microsoft documents separate Foundry controls for:

- inbound access to the Foundry resource and projects through public access, selected IP addresses, or private endpoints;
- outbound access from the Foundry resource to connected Azure services;
- outbound access from the Agent client through virtual-network injection into a delegated customer subnet.

Private-linking the Foundry resource does not automatically private-link Storage, Key Vault, Azure AI Search, monitoring, or other connected resources. Those services retain their own governance boundaries and require separate endpoint, firewall, DNS, identity, and policy decisions.

## Required diagram and inventory

Each product Technical Document includes:

- ingress path;
- egress destinations;
- VNet/subnet placement;
- private endpoints;
- DNS ownership and zones;
- on-premises routes;
- firewall/NSG responsibility;
- platform service exceptions;
- environment separation;
- diagnostic/log flow.

## Common failure modes

- private endpoint created but public access left enabled;
- DNS resolves differently across developer, Azure, and on-premises networks;
- a service can reach Azure resources but not the legacy backend;
- required model or connector egress is blocked or uncontrolled;
- shared subnet delegation conflicts with another service;
- logging and deployment paths were not included in network design.

## Current Microsoft qualifications

- Private Link carries supported service traffic over the Microsoft backbone through a private endpoint, but service availability and limitations remain service-specific.
- Foundry private endpoints depend on correct private DNS-zone records and links. A private endpoint without working DNS resolution does not create a usable private path.
- Inbound and outbound isolation are separate design problems; securing one does not secure the other.
- Key Vault can disable ordinary public data-plane access, but Microsoft documents that the trusted-services bypass can continue to apply unless a Network Security Perimeter overrides it. Treat bypass settings as explicit exposure paths.
- Public DNS records can remain resolvable after public access is disabled. Validation must test the actual route and authorization result, not treat DNS visibility alone as proof of exposure.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Configure network isolation for Microsoft Foundry](https://learn.microsoft.com/azure/foundry/how-to/configure-private-link) | 2026-09-19 | Foundry inbound/outbound model, private endpoints, VNet injection, roles, and DNS |
| [Microsoft Foundry architecture](https://learn.microsoft.com/azure/foundry/concepts/architecture) | 2026-09-19 | Separate governance boundaries for connected Azure resources |
| [Azure Private Link overview](https://learn.microsoft.com/azure/private-link/private-link-overview) | 2026-09-19 | Private endpoints, backbone routing, service-specific availability |
| [Configure network security for Azure Key Vault](https://learn.microsoft.com/azure/key-vault/general/network-security) | 2026-09-19 | Firewall modes, trusted-service bypass, public-access behavior, private endpoints |
| [Azure networking architecture](https://learn.microsoft.com/azure/architecture/networking/) | 2026-09-19 | Cross-service architecture guidance |

Research detail and unresolved enterprise facts are recorded in [Source Record — Azure Security Controls](../sources/2026-09-19-security-controls.md).
