---
title: Fabric, OneLake, and Data Movement
status: candidate
owner: Enterprise Data with Product Group
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Fabric, OneLake, and Data Movement

Microsoft Fabric and OneLake may provide the enterprise analytical data plane. Product teams should consume governed data products and contribute approved outputs without creating parallel, undocumented analytical silos.

Catalog presence, a Fabric workspace, or a OneLake path does not establish enterprise truth. The named data owner and published data contract remain authoritative.

## Current Microsoft qualifications

- Fabric is a SaaS analytics platform whose workloads use OneLake as a centralized logical data lake. Every Fabric tenant has one OneLake; workspaces are assigned to capacities tied to regions and billing.
- OneLake stores data and can also present data that remains in another source. A unified namespace must not be interpreted as one physical copy or one authoritative owner.
- Shortcuts are references to internal or external data. Deleting a shortcut doesn't delete its target, while moving, renaming, or deleting the target can break the shortcut.
- Shortcuts and mirroring serve different purposes: shortcuts virtualize selected open-format data in place; mirroring can access or continuously replicate a supported database or catalog. Pipelines, dataflows, copy jobs, or eventstreams remain appropriate when transformations, orchestration, or movement controls are required.
- OneLake shortcut access can use the querying user's identity or delegated credentials depending on shortcut type and configuration. Source and destination permissions, credential ownership, rotation, and incident response must be designed explicitly.
- OneLake security roles can grant table, folder, row, and column access, but workspace and item permissions also affect effective access. Validate behavior through every engine used by the product.

## Responsibility split

| Responsibility | Product Group | Enterprise Data |
|---|---|---|
| Operational product state | owns product/domain contract | advises/integrates |
| Enterprise analytical truth | consumes and validates use | owns platform and data products |
| Product telemetry/outcomes | defines and emits | ingests/governs as agreed |
| AI feature/training datasets | co-owns purpose and labels | co-governs sourcing, quality, access |
| Semantic models/reporting | supplies product meaning | owns or shares based on operating model |

## Data movement choices

- API for synchronous operational facts.
- Events/messages for operational change propagation.
- Data Factory/Fabric pipelines for batch ingestion and transformation.
- Shortcuts/OneLake patterns when enterprise architecture approves them.
- Event Hubs for high-throughput telemetry streams.

Do not use direct database access as a substitute for a stable capability when business rules or operational authorization are required.

## Required alignment

- authoritative source and semantic ownership;
- refresh/latency expectation;
- schema and compatibility;
- data quality and reconciliation;
- classification and access;
- lineage and catalog registration;
- deletion/retention;
- cost and capacity owner;
- incident/support path.

For every shortcut, mirror, pipeline, or copy, record the source owner, access identity, physical location, whether data is virtualized or replicated, freshness, schema-change behavior, delete propagation, security enforcement point, lineage, recovery, and cost owner.

See [Microsoft Fabric documentation](https://learn.microsoft.com/en-us/fabric/) and [OneLake overview](https://learn.microsoft.com/en-us/fabric/onelake/onelake-overview).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [What is Microsoft Fabric?](https://learn.microsoft.com/fabric/fundamentals/microsoft-fabric-overview) | 2026-09-19 | SaaS architecture, workloads, OneLake, governance, and Fabric capacity context |
| [What is OneLake?](https://learn.microsoft.com/fabric/onelake/onelake-overview) | 2026-09-19 | Tenant-wide logical lake, hierarchy, workspaces, regions, catalog, and security |
| [OneLake shortcuts](https://learn.microsoft.com/fabric/onelake/onelake-shortcuts) | 2026-09-19 | Virtual references, supported locations, synchronization, deletion behavior, and lineage |
| [Unify data with shortcuts and mirroring](https://learn.microsoft.com/fabric/onelake/unify-data) | 2026-09-19 | Virtualization versus replication and when movement tools remain necessary |
| [How OneLake security controls access](https://learn.microsoft.com/fabric/onelake/security/data-access-control-model) | 2026-09-19 | Roles, permissions, identities, effective access, and shortcut authentication |
| [OneLake architecture patterns](https://learn.microsoft.com/fabric/onelake/architecture-patterns) | 2026-09-19 | Minimal-replication, medallion, data-mesh, consolidation, and sharing patterns |

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).
