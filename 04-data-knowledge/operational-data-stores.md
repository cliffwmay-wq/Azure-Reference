---
title: Operational Data Stores
status: candidate
owner: Product Group Data Steward
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Operational Data Stores

Choose a store from access patterns, consistency, relationships, scale, operating model, and recovery requirements—not from AI fashion.

Microsoft's current architecture guidance starts with workload requirements: data format and purpose, relationships, access paths, consistency, concurrency, lifecycle, performance, scale, cost, security, governance, recovery, regional support, and team operating capability. The table below narrows candidates; it doesn't replace a measured selection or enterprise approval.

## Starting choices

| Store | Strong fit | Watch for |
|---|---|---|
| Azure SQL Database | relational transactions, mature SQL tooling, strong constraints | schema and scaling design, connection management |
| Azure Database for PostgreSQL | relational/open ecosystem, JSON plus relational needs, extension ecosystem | extension support, connection pooling, operational ownership |
| Azure Cosmos DB | globally distributed flexible documents, predictable key-based scale | partition design, request-unit cost, consistency decisions |
| Azure Managed Redis | cache, ephemeral state, acceleration | not authoritative storage by default; eviction, persistence, failover, memory, and clustering assumptions |
| Existing enterprise warehouse/lake | governed analytical facts and history | interactive operational latency and ownership boundaries |

## Product state versus agent state

Product workflow state belongs in a product/domain store. Agent conversation or run state is not automatically durable business state. If an agent produces an operationally meaningful decision, persist the structured result through a domain capability with provenance and authorization.

## Current Microsoft qualifications

- Azure SQL Database is a managed PaaS database engine with multiple service and compute tiers. Tier labels, serverless behavior, scale, zone redundancy, backup, and cost require explicit selection; the generic name doesn't establish those properties.
- Azure Database for PostgreSQL flexible server provides a managed community PostgreSQL engine with configurable versions, compute, extensions, networking, high availability, and stop/start behavior. Version and extension support, connection limits, pooling, and high-availability configuration must be verified.
- Cosmos DB is a distributed NoSQL engine with horizontal partitioning, configurable consistency, and Request Unit-based throughput/cost. The partition key shapes data distribution, transaction scope, hot-partition risk, and query efficiency, so it must be designed from measured access patterns.
- Azure Managed Redis is an in-memory data store that can support caching and other low-latency patterns. Cache-aside designs must tolerate misses, eviction, expiration, failover, and stale data; authoritative writes remain in the domain store unless an explicit durability design proves otherwise.
- Microsoft is retiring all Azure Cache for Redis SKUs. Enterprise and Enterprise Flash retire March 31, 2027; Basic, Standard, and Premium retire September 30, 2028. Inventory existing instances and plan tested migration to Azure Managed Redis rather than selecting the retiring service for new work.

## Vector storage

Vector capability does not decide the authoritative store. Embeddings may live in Azure AI Search, Cosmos DB, PostgreSQL, or another approved platform depending on retrieval, filtering, scale, and ownership. Always preserve source identifiers, access metadata, version, deletion propagation, and re-embedding strategy.

## Required selection record

- entities and access paths;
- transaction/consistency needs;
- expected volume, throughput, and growth;
- partition/index strategy;
- identity and network controls;
- encryption and backup/recovery;
- retention/deletion;
- data residency;
- cost driver and scaling trigger;
- migration/export path.

Also record engine and version, service tier/SKU, region, availability-zone configuration, connection and pool limits, transaction boundary, consistency setting, partition key where applicable, backup retention, restore test, failover behavior, maintenance window, SDK/driver, and retirement dependencies.

Sources: [Azure SQL documentation](https://learn.microsoft.com/en-us/azure/azure-sql/), [Azure Database for PostgreSQL](https://learn.microsoft.com/en-us/azure/postgresql/), and [Azure Cosmos DB](https://learn.microsoft.com/en-us/azure/cosmos-db/).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Prepare to choose a data store](https://learn.microsoft.com/azure/architecture/guide/technology-choices/data-stores-getting-started) | 2026-09-19 | Functional, performance, cost, security, governance, recovery, and operating-model selection factors |
| [Azure SQL Database overview](https://learn.microsoft.com/azure/azure-sql/database/sql-database-paas-overview?view=azuresql) | 2026-09-19 | Managed engine, service/compute tiers, availability, backup, scale, and operations |
| [Azure Database for PostgreSQL overview](https://learn.microsoft.com/azure/postgresql/overview) | 2026-09-19 | Flexible Server architecture, versions, configuration, high availability, networking, and cost controls |
| [Cosmos DB overview](https://learn.microsoft.com/cosmos-db/overview) | 2026-09-19 | Distributed NoSQL model, JSON, global distribution, consistency, partitioning, and Request Units |
| [Cosmos DB partitioning](https://learn.microsoft.com/azure/cosmos-db/partitioning-overview) | 2026-09-19 | Logical/physical partitions and partition-key design impact |
| [Azure Managed Redis overview](https://learn.microsoft.com/azure/redis/overview) | 2026-09-19 | In-memory service, cache-aside and other low-latency patterns |
| [Azure Cache for Redis retirement FAQ](https://learn.microsoft.com/azure/azure-cache-for-redis/retirement-faq) | 2026-09-19 | Retirement dates, disablement, and migration recommendation |

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).
