---
title: Secrets and Key Management
status: candidate
owner: Information Assurance and Platform
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Secrets and Key Management

Azure Key Vault is the default candidate for secrets, keys, and certificates that cannot be eliminated through managed identity.

## Governing order

1. Use managed identity and token-based access.
2. Use platform-managed connection/credential capability where it provides approved governance.
3. Store unavoidable secrets, keys, and certificates in Key Vault.
4. Never place secrets in source, prompts, wiki pages, client applications, tool descriptions, or deployment output.

## Required controls

- vault boundary and owner;
- RBAC/access model;
- private endpoint and firewall posture;
- soft delete and purge protection;
- logging and alerting;
- secret rotation and expiry owner;
- certificate lifecycle;
- customer-managed key requirements;
- backup/recovery and regional dependencies;
- emergency access.

## Documentation rule

Documentation records secret **names, purpose, owner, consumer, rotation expectation, and location class**—never values. Examples must use placeholders that cannot be mistaken for live credentials.

## Application rule

Applications retrieve secrets at runtime or use platform references. Avoid copying secrets into environment-specific files or CI/CD variables when workload identity can access Key Vault directly.

## Key Vault product facts

- Key Vault has separate control-plane and data-plane permissions. Resource management access does not automatically grant permission to read secret values, and data-plane access must be deliberately assigned.
- Microsoft recommends Azure RBAC for Key Vault authorization and cautions against legacy access policies for critical workloads. Migration between permission models must be planned because enabling the RBAC model invalidates existing access-policy permissions.
- Soft delete is enabled by default for new vaults and retains deleted vaults and objects for a configured 7–90 day period. Recovering a soft-deleted vault does not restore associated RBAC assignments or Event Grid subscriptions.
- Purge protection is not enabled by default. Once enabled, deleted vaults and objects cannot be purged until the retention period expires.
- Network restriction and authorization are complementary: reaching a vault through an allowed network path does not grant access to keys, secrets, or certificates.

## Foundry connection qualifications

Microsoft documents that, without a customer Key Vault connection, Foundry stores connection details in a Microsoft-managed Key Vault outside the customer's subscription. A customer-managed Key Vault connection is limited to one per Foundry resource, has no automatic secret-migration path, and becomes a dependency for non-Entra connections. Deleting the vault or managed connection secrets can break dependent Foundry connections.

Project connections are appropriate only for shared credentials. Microsoft warns that project users can access secrets stored in a project connection; user-specific authorization should use identity passthrough where supported.

These capabilities do not establish the Product Group's required vault topology, RBAC model, purge-protection setting, connection pattern, rotation period, or customer-managed-key requirement. Those remain enterprise decisions.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Secure your Azure Key Vault](https://learn.microsoft.com/azure/key-vault/general/security-features) | 2026-09-19 | Managed identity, RBAC, network, recovery, rotation, logging, and backup guidance |
| [Key Vault soft-delete overview](https://learn.microsoft.com/azure/key-vault/general/soft-delete-overview) | 2026-09-19 | Retention, recovery, purge protection, and recovery limitations |
| [Azure RBAC for Key Vault data-plane operations](https://learn.microsoft.com/azure/key-vault/general/rbac-guide) | 2026-09-19 | Control/data planes, RBAC scopes, legacy access-policy migration risk |
| [Configure Key Vault network security](https://learn.microsoft.com/azure/key-vault/general/network-security) | 2026-09-19 | Firewall, public access, private endpoint, trusted-service behavior |
| [Set up a Key Vault connection in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/how-to/set-up-key-vault-connection) | 2026-09-19 | Microsoft-managed storage default, customer-vault limits, RBAC, and secret lifecycle |
| [MCP authentication in Foundry](https://learn.microsoft.com/azure/foundry/agents/how-to/mcp-authentication) | 2026-09-19 | Shared project-connection credentials and identity-passthrough alternative |

Research detail and unresolved enterprise facts are recorded in [Source Record — Azure Security Controls](../sources/2026-09-19-security-controls.md).
