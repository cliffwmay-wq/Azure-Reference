---
title: Source Record — Data and Governed Knowledge
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Data and Governed Knowledge

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate guidance for operational data stores, Azure AI Search, Blob and Data Lake Storage, Fabric and OneLake, Microsoft Purview, and authoritative-data boundaries?

## Primary Microsoft Learn sources

### Operational data stores

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Prepare to choose a data store in Azure | https://learn.microsoft.com/azure/architecture/guide/technology-choices/data-stores-getting-started | 2026-09-19 | Functional, performance, cost, security, governance, recovery, and operating-model selection factors |
| What is Azure SQL Database? | https://learn.microsoft.com/azure/azure-sql/database/sql-database-paas-overview?view=azuresql | 2026-09-19 | Managed PaaS engine, service and compute tiers, availability, backup, scale, and operations |
| What is Azure Database for PostgreSQL flexible server? | https://learn.microsoft.com/azure/postgresql/overview | 2026-09-19 | Architecture, versions, configuration, high availability, networking, and cost controls |
| What is Cosmos DB? | https://learn.microsoft.com/cosmos-db/overview | 2026-09-19 | Distributed NoSQL model, global distribution, consistency, partitioning, indexing, and Request Units |
| Partitioning and horizontal scaling in Azure Cosmos DB | https://learn.microsoft.com/azure/cosmos-db/partitioning-overview | 2026-09-19 | Logical/physical partitions and partition-key design impact |
| What is Azure Managed Redis? | https://learn.microsoft.com/azure/redis/overview | 2026-09-19 | In-memory service and caching/low-latency application patterns |
| Azure Cache for Redis retirement FAQ | https://learn.microsoft.com/azure/azure-cache-for-redis/retirement-faq | 2026-09-19 | Retirement and disablement dates plus migration recommendation |

### Azure AI Search

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| What is Azure AI Search? | https://learn.microsoft.com/azure/search/search-what-is-azure-search | 2026-09-19 | Managed search architecture, indexing, enrichment, classic and agentic retrieval |
| Create a hybrid query in Azure AI Search | https://learn.microsoft.com/azure/search/hybrid-search-how-to-query | 2026-09-19 | Parallel keyword/vector execution, Reciprocal Rank Fusion, filters, semantic ranking |
| Document-level access control in Azure AI Search | https://learn.microsoft.com/azure/search/search-document-level-access-overview | 2026-09-19 | Security-filter pattern and preview native ACL, RBAC-scope, and sensitivity-label paths |
| Change and delete detection using indexers for Azure Storage | https://learn.microsoft.com/azure/search/search-how-to-index-azure-blob-changed-deleted | 2026-09-19 | Change detection, required deletion policy, and orphaned-index risk |
| Service limits in Azure AI Search | https://learn.microsoft.com/azure/search/search-limits-quotas-capacity | 2026-09-19 | Tier and pricing-model limits; Serverless Developer preview |
| Transparency note: Azure AI Search | https://learn.microsoft.com/azure/foundry/responsible-ai/search/transparency-note | 2026-09-19 | Retrieval and AI-enrichment capabilities, limitations, and system-owner responsibilities |

### Blob and Data Lake Storage

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Introduction to Azure Blob Storage | https://learn.microsoft.com/azure/storage/blobs/storage-blobs-introduction | 2026-09-19 | Blob purposes, containers, tiers, and ADLS relationship |
| Introduction to Azure Data Lake Storage | https://learn.microsoft.com/azure/storage/blobs/data-lake-storage-introduction | 2026-09-19 | Hierarchical namespace, atomic directory operations, RBAC, ACLs, and support variability |
| Data protection overview | https://learn.microsoft.com/azure/storage/blobs/data-protection-overview | 2026-09-19 | Protection-option scope and hierarchical-namespace support matrix |
| Soft delete for blobs | https://learn.microsoft.com/azure/storage/blobs/soft-delete-blob-overview | 2026-09-19 | Retention, restoration scope, in-account protection, and backup recommendation |
| Immutable storage for Azure Blob Storage | https://learn.microsoft.com/azure/storage/blobs/immutable-storage-overview | 2026-09-19 | WORM, time-based retention, legal hold, and mutation effects |
| Azure Storage redundancy | https://learn.microsoft.com/azure/storage/common/storage-redundancy | 2026-09-19 | LRS, ZRS, geo-replication, availability, durability, and account-level setting |

### Fabric and OneLake

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| What is Microsoft Fabric? | https://learn.microsoft.com/fabric/fundamentals/microsoft-fabric-overview | 2026-09-19 | Fabric SaaS architecture, workloads, OneLake, and built-in governance context |
| What is OneLake? | https://learn.microsoft.com/fabric/onelake/onelake-overview | 2026-09-19 | Tenant-wide logical lake, hierarchy, workspaces, capacity/region relationship, and security |
| OneLake shortcuts | https://learn.microsoft.com/fabric/onelake/onelake-shortcuts | 2026-09-19 | Reference semantics, internal/external targets, supported locations, breakage, and lineage |
| Unify data with OneLake shortcuts and mirroring | https://learn.microsoft.com/fabric/onelake/unify-data | 2026-09-19 | Virtualization versus replication and continuing data-movement use cases |
| How OneLake security controls data access | https://learn.microsoft.com/fabric/onelake/security/data-access-control-model | 2026-09-19 | Roles, permissions, effective access, identities, and shortcut authentication modes |
| Microsoft OneLake patterns and foundational capabilities | https://learn.microsoft.com/fabric/onelake/architecture-patterns | 2026-09-19 | Minimal replication, medallion, data mesh, consolidation, and sharing patterns |

### Microsoft Purview

| Page title | URL | Retrieved | Material facts supported |
|---|---|---|---|
| Data governance with Microsoft Purview | https://learn.microsoft.com/purview/data-governance-overview | 2026-09-19 | Data Map and Unified Catalog roles, metadata boundary, and federated governance |
| Scans and ingestion in Data Map | https://learn.microsoft.com/purview/data-map-scan-ingestion | 2026-09-19 | Metadata capture, schemas, classifications, scan scope, schedule, and authentication |
| Data governance roles and permissions | https://learn.microsoft.com/purview/data-governance-roles-permissions | 2026-09-19 | Tenant, catalog, domain, collection, and account-type permission layers |
| Plan for data governance with Microsoft Purview | https://learn.microsoft.com/purview/data-governance-plan | 2026-09-19 | Data Map/Unified Catalog relationship, regions, roles, domains, collections, and rollout |
| Data lineage user guide for classic Data Catalog | https://learn.microsoft.com/purview/data-gov-classic-lineage-user-guide | 2026-09-19 | Lineage integrations, custom lineage, platform-specific scope, known limitations, and current Unified Catalog viewing route |
| Data governance FAQ | https://learn.microsoft.com/purview/data-governance-faq | 2026-09-19 | Supported-source variability, scan sampling and load, and lineage coverage |
| Free version of data governance solutions | https://learn.microsoft.com/purview/data-governance-free-version | 2026-09-19 | Preview status, automatic availability, supported-source and asset limits |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| Microsoft data-store guidance begins with workload functional, performance, cost, security, governance, recovery, regional, and operational requirements rather than a universal default. | Data-store selection guidance | High. |
| Azure SQL Database and Azure Database for PostgreSQL are managed relational candidates with distinct engines, service tiers, versions, high-availability options, limits, and operating characteristics. | SQL Database; PostgreSQL | High; enterprise engine and tier selection is unknown. |
| Cosmos DB's partition key affects distribution, transaction scope, hot partitions, and query efficiency; consistency and Request Units are explicit design and cost dimensions. | Cosmos DB overview and partitioning | High. |
| Azure Managed Redis is an in-memory store suited to caching and other low-latency patterns; cache semantics don't establish source-of-record authority. | Azure Managed Redis | High; durability depends on the selected configuration and application design. |
| Azure Cache for Redis Enterprise/Enterprise Flash retires March 31, 2027; Basic/Standard/Premium retires September 30, 2028. Microsoft recommends migration to Azure Managed Redis. | Retirement FAQ | High and time-sensitive. |
| Azure AI Search indexes are derived search assets supporting keyword, vector, hybrid, semantic, and other retrieval patterns. | AI Search overview and hybrid query | High; selected features, tiers, and APIs have separate status and limits. |
| Generally available security filters require correct identity metadata and application-supplied filters; multiple native identity-aware enforcement paths remain preview. | Document-level access control | High; authorization behavior must be tested end to end. |
| Indexer change detection doesn't imply deletion detection; a supported deletion policy is required from the first run to avoid orphan documents. | Change and delete detection | High; source/index synchronization is an application operating responsibility. |
| ADLS capabilities are enabled on Blob Storage through hierarchical namespace and add directory semantics and ACLs. | ADLS introduction | High; individual Blob features have separate support statements. |
| Blob recovery, immutability, redundancy, and backup mechanisms cover different failure modes; versioning and point-in-time restore aren't supported for hierarchical-namespace accounts. | Data protection overview | High; protection design is account- and workload-specific. |
| OneLake is one logical tenant-wide lake, but its namespace can include source-resident data and synchronized copies. | OneLake overview; shortcuts and mirroring | High; logical unification doesn't establish ownership or authority. |
| Shortcuts are independent references: deleting one doesn't delete the target, while target changes can break it. | OneLake shortcuts | High. |
| Effective OneLake access depends on OneLake roles plus workspace, item, source, destination, engine, and shortcut authentication behavior. | OneLake security | High; configuration and engine-specific validation are required. |
| Purview Data Map and Unified Catalog contain metadata, and Purview governance roles don't grant access to underlying data. | Purview overview and planning | High; source authorization remains separate. |
| Purview scan, classification, and lineage coverage vary by source and can be incomplete; scanning can add source load. | Scan ingestion, lineage guide, FAQ | High; coverage and impact must be validated per connector. |
| The automatically available free Purview governance version is preview and limited. | Free governance version | High; tenant entitlement and enterprise selection remain unknown. |

## Limitations, previews, and deprecations

- Database features, supported engine versions/extensions, tiers, regions, limits, high availability, backup, maintenance, networking, drivers, and pricing change independently and must be verified for the exact selection.
- Azure Cache for Redis is retiring. Existing instances require inventory, compatibility review, performance/failover testing, cost validation, and a dated migration plan; the retirement notice doesn't prove Azure Managed Redis is already enterprise-approved.
- Native Azure AI Search ACL/RBAC-scope and Purview sensitivity-label enforcement paths are preview in the retrieved documentation.
- Azure AI Search Serverless Developer is preview and not recommended by Microsoft for production workloads.
- Search relevance and semantic/vector similarity are probabilistic; representative retrieval evaluation remains necessary.
- Deletion, permission, and classification changes can lag or fail between source systems and derived indexes/catalogs.
- Hierarchical-namespace accounts don't support every Blob data-protection feature; the support matrix changes over time.
- OneLake shortcut and mirroring support, identity behavior, source formats, and engine enforcement vary by source and feature.
- Purview metadata, classifications, data quality, and lineage don't establish complete source inspection or underlying-data authorization.
- Microsoft's detailed lineage guide is explicitly scoped to the classic Data Catalog; current source-specific documentation and Unified Catalog asset views must be checked for each integration.
- Purview's free governance version is preview and limited; its automatic availability isn't proof of enterprise approval.
- Learn MCP retrieval didn't expose reliable page-update dates; retrieval dates are recorded instead.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Approved relational, NoSQL, and cache platforms; engine versions, tiers, regions, identities, networks, encryption, HA, backups, maintenance, monitoring, support, cost, and migration standards | Data Platform / Infrastructure / Information Assurance / Production Engineering |
| Inventory of Azure Cache for Redis instances, tiers, owners, dependencies, feature gaps, reservations, migration targets, tests, and completion dates | Data Platform / Application owners / Procurement |
| Authoritative systems, business owners, data contracts, semantic owners, reconciliation rules, and approved derived copies | Enterprise Data / Product data owners |
| Approved Azure AI Search tier, region, capacity, API/SDK versions, embedding models, permission pattern, deletion SLA, and monitoring | Knowledge Platform / Infrastructure / Information Assurance |
| Approved storage-account topology, hierarchical namespace, region, redundancy, network, encryption, immutability, retention, backup, and recovery | Data Platform / Infrastructure / Information Assurance / Records Management |
| Whether Fabric and OneLake are the enterprise analytical plane, including tenant settings, capacities, regions, domains, workspaces, security, shortcuts, mirroring, and cost owners | Enterprise Data / Fabric administrators / Procurement |
| Purview account type, licensing, region, domains, collections, roles, scan identities, supported sources, schedules, classification, lineage, and data-quality standards | Enterprise Data / Information Assurance / Purview administrators |
| Authoritative access-request and approval system for cataloged data | Enterprise Data / Identity / Data owners |

## Product Group decision impact

**governance**

The candidate direction remains bounded: operational stores are selected from measured access, consistency, scale, recovery, and operating requirements; source systems retain authority; Azure AI Search is a rebuildable retrieval derivative; Blob/ADLS is candidate object/lake storage with workload-specific protection; Fabric/OneLake may be the enterprise analytical plane; and Purview may be the metadata-governance plane. Azure Cache for Redis retirement creates a migration requirement but doesn't silently approve Azure Managed Redis. No platform was promoted to approved enterprise status.

## Reference pages affected

- `04-data-knowledge/data-responsibility-model.md`
- `04-data-knowledge/operational-data-stores.md`
- `04-data-knowledge/ai-search-retrieval.md`
- `04-data-knowledge/object-lake-storage.md`
- `04-data-knowledge/fabric-onelake-data-movement.md`
- `04-data-knowledge/purview.md`
- `sources/microsoft-learn-catalog.md`
- `sources/research-backlog.md`

## Downstream impact note

Review product documentation that treats a cache, search index, OneLake path, catalog entry, endorsement, classification, embedding, or analytical copy as authoritative; selects a database without explicit consistency/partition/recovery evidence; depends on Azure Cache for Redis without a migration plan; assumes search permissions or deletions synchronize automatically; treats storage redundancy as backup; assumes all Blob protection features work with hierarchical namespace; or treats Purview roles as source-data access. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: Enterprise Data / Knowledge Platform / Information Assurance / Infrastructure / Records Management (pending)

Review date: pending
