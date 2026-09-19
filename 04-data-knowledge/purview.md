---
title: Microsoft Purview
status: candidate
owner: Enterprise Data Governance
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Microsoft Purview

Microsoft Purview is the candidate enterprise metadata-governance plane for discovery, classification, lineage, business context, ownership, and data-product curation. Its use and account model require Enterprise Data, Information Assurance, and tenant-owner confirmation.

## Responsibility boundary

| Capability | Purview role | Boundary |
|---|---|---|
| Technical inventory | Data Map scans and ingests metadata from supported sources | Coverage depends on connector, scan scope, identity, schedule, and source support |
| Business catalog | Unified Catalog curates domains, data products, glossary concepts, ownership, and quality context | Catalog publication or endorsement does not make a source authoritative without an approved owner and contract |
| Classification | Scans can sample supported sources and apply system or custom classifications | Classification is evidence requiring review; it is not proof that all sensitive data was found |
| Lineage | Supported platforms can publish or expose lineage metadata | Depth and completeness vary by system and transformation type |
| Access workflow | Catalog experiences can support discovery and access requests | Purview governance roles do not grant access to underlying data |

## Current Microsoft qualifications

- Microsoft documents Data Map as the technical metadata layer and Unified Catalog as the business-facing curation and discovery layer.
- Data Map and Unified Catalog hold metadata, not the underlying business data. Their roles and permissions do not confer access to the underlying source.
- Scans capture technical metadata and can extract schema, classifications, and sensitivity labels for supported sources. Authentication options and captured capabilities vary by source; managed identity is preferred where supported.
- Classification scanning samples data rather than proving complete inspection. Microsoft notes that scan load can affect operational databases and recommends scheduling accordingly.
- Lineage coverage varies by platform and operation. Microsoft's detailed lineage guide is labeled for the classic Data Catalog, although it directs Unified Catalog users to asset details for current viewing. Unsupported or custom transformations require an explicit lineage integration or separate evidence.
- Microsoft offers different Purview account and feature experiences. The automatically available free governance version is preview and has limits; its presence must not be treated as confirmation of an approved enterprise deployment or entitlement.

## Product Group obligations

- register only approved sources using a least-privilege scan identity;
- name the source owner, data steward, domain, classification reviewer, and remediation owner;
- define scan scope, frequency, network path, expected load, failure monitoring, and credential lifecycle;
- reconcile catalog metadata with source changes and remove stale assets;
- document lineage gaps instead of presenting partial lineage as complete;
- connect access requests to the authoritative source-system approval path;
- keep product-specific schemas, classifications, and remediation runbooks in the product documentation or governed catalog, not in this reference.

## Enterprise decisions required

- Purview account type, tenant/organization instance, region, licensing, and cost owner;
- Data Map domain and collection model;
- Unified Catalog governance domains, data-product model, business glossary, and endorsement rules;
- role assignment, separation of duties, privileged access, and review cadence;
- supported sources, scan identities, integration runtimes, network paths, and scan schedules;
- classification, sensitivity-label, data-quality, and lineage standards;
- access-request integration and authoritative approval system;
- metadata retention, audit, incident response, and stale-asset removal.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Data governance with Microsoft Purview](https://learn.microsoft.com/purview/data-governance-overview) | 2026-09-19 | Data Map and Unified Catalog responsibilities, metadata boundary, and federated governance roles |
| [Scans and ingestion in Data Map](https://learn.microsoft.com/purview/data-map-scan-ingestion) | 2026-09-19 | Scan and ingestion behavior, captured metadata, scope, schedules, and authentication |
| [Data governance roles and permissions](https://learn.microsoft.com/purview/data-governance-roles-permissions) | 2026-09-19 | Tenant, Unified Catalog, Data Map, domain, and collection permission layers |
| [Plan for data governance](https://learn.microsoft.com/purview/data-governance-plan) | 2026-09-19 | Data Map/Unified Catalog relationship, regions, roles, domains, collections, and rollout |
| [Data lineage user guide for classic Data Catalog](https://learn.microsoft.com/purview/data-gov-classic-lineage-user-guide) | 2026-09-19 | Lineage sources, platform-specific coverage, custom lineage, known limitations, and current Unified Catalog viewing route |
| [Data governance FAQ](https://learn.microsoft.com/purview/data-governance-faq) | 2026-09-19 | Supported-source variability, scan sampling, source load, and changing lineage coverage |
| [Free governance version](https://learn.microsoft.com/purview/data-governance-free-version) | 2026-09-19 | Preview status, automatic availability, supported sources, and asset limits |

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).

Microsoft Purview is the candidate governance layer for discovering, classifying, cataloging, and tracing enterprise data assets. Exact tenant capabilities and responsibilities must be confirmed during transition.

## Product Group use

- register applicable data sources and products;
- apply or consume classification and glossary terms;
- expose ownership and lineage;
- support impact analysis;
- document data sharing and policy obligations;
- align AI source and derived assets with enterprise governance.

## AI-specific catalog needs

Catalog or link:

- source datasets and evidence repositories;
- curated training/evaluation datasets;
- derived features and embeddings;
- search indexes and source mappings;
- model/agent outputs with material business use;
- retention and deletion dependencies;
- data owners and permitted uses.

Purview does not replace application authorization, domain validation, or Product Technical Documentation. It provides enterprise discovery and governance context.

## Transition questions

- Which Purview capabilities and licenses are active?
- What collections/domains already exist?
- Who approves classification and glossary changes?
- Which Azure and non-Azure sources are scanned?
- How will lineage be captured from Product Group pipelines?
- What sensitive-information rules apply to prompts, traces, images, and embeddings?

See [Microsoft Purview documentation](https://learn.microsoft.com/en-us/purview/).
