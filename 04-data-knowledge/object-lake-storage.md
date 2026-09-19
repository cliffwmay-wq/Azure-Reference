---
title: Object and Lake Storage
status: candidate
owner: Product Group Data Steward
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Object and Lake Storage

Azure Blob Storage is the default candidate for images, documents, binary artifacts, exports, and other object data. Azure Data Lake Storage Gen2 adds hierarchical namespace and data-lake semantics where analytical organization and filesystem-style access are required.

This is a Product Group candidate, not confirmation of an approved storage-account topology, region, redundancy option, network boundary, retention policy, or backup service.

## Current Microsoft qualifications

- Azure Data Lake Storage is a capability set on Blob Storage enabled through hierarchical namespace; it adds directory semantics, atomic directory operations, and file/directory ACLs alongside Azure RBAC.
- Blob data-protection features are not interchangeable. Soft delete, versioning, snapshots, point-in-time restore, immutability, redundancy, and vaulted backup protect different failure modes and have different account and hierarchical-namespace support.
- Microsoft documents that blob versioning and point-in-time restore aren't available for hierarchical-namespace accounts. ADLS designs therefore require an explicit recovery design rather than copying a general Blob protection baseline.
- Soft delete is time limited and remains an in-account protection. Microsoft recommends considering Azure Backup for broader scenarios such as account deletion or ransomware.
- Immutability policies can protect data from overwrite and deletion using time-based retention or legal hold. Their use requires records-management and legal approval; immutability is not a general substitute for backup.
- Storage redundancy protects availability and durability during infrastructure or regional failures. It does not independently provide historical recovery from authorized deletion, corruption, or application error.

## Typical Product Group uses

- original operational images and documents;
- curated ML datasets and labels;
- model/evaluation artifacts where an ML registry is not the owning service;
- batch input/output;
- immutable evidence packages;
- published documentation assets;
- archival and retention-controlled records.

## Design decisions

- account/container boundary by product, data class, and lifecycle;
- hierarchical namespace requirement;
- region, redundancy, and durability tier;
- hot/cool/cold/archive lifecycle;
- object versioning, soft delete, immutability, and legal hold;
- managed identity and RBAC versus scoped delegation;
- private endpoint/firewall posture;
- encryption and customer-managed key requirement;
- event notification and downstream processing;
- metadata, naming, and lineage;
- backup/recovery versus native redundancy assumptions.

## Image evidence pattern

Store the original object separately from model output. Link using a stable observation/event identifier. The metadata record should include capture source, time, operational reference, hash where appropriate, classification, retention, and access scope. Model output records the exact source object version and inference version.

## Guardrails

- Do not expose long-lived storage keys to clients.
- Do not use public container access for operational data.
- Do not assume an object URL is authorization.
- Do not place unrestricted production datasets in developer-accessible accounts.
- Do not treat geo-redundancy as a complete backup and recovery plan.

See [Azure Blob Storage documentation](https://learn.microsoft.com/en-us/azure/storage/blobs/) and [ADLS Gen2 introduction](https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Introduction to Azure Blob Storage](https://learn.microsoft.com/azure/storage/blobs/storage-blobs-introduction) | 2026-09-19 | Object-storage purposes, containers, tiers, and ADLS relationship |
| [Introduction to Azure Data Lake Storage](https://learn.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) | 2026-09-19 | Hierarchical namespace, directory semantics, RBAC and ACLs, and feature-support qualification |
| [Data protection overview](https://learn.microsoft.com/azure/storage/blobs/data-protection-overview) | 2026-09-19 | Protection options, hierarchical-namespace support, recovery and backup distinctions |
| [Soft delete for blobs](https://learn.microsoft.com/azure/storage/blobs/soft-delete-blob-overview) | 2026-09-19 | Retention behavior, recovery scope, cost, and broader backup recommendation |
| [Immutable storage for blobs](https://learn.microsoft.com/azure/storage/blobs/immutable-storage-overview) | 2026-09-19 | WORM behavior, time-based retention, legal hold, and write/delete effects |
| [Azure Storage redundancy](https://learn.microsoft.com/azure/storage/common/storage-redundancy) | 2026-09-19 | LRS, ZRS, geo-replication, availability, durability, and account-wide setting |

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).
