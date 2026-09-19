---
title: Azure AI Search and Retrieval
status: candidate
owner: Product Group Knowledge Platform
review_cycle: monthly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Azure AI Search and Retrieval

Azure AI Search is the primary candidate for full-text, vector, and hybrid retrieval used by products and Foundry agents.

## Responsibilities

- indexing governed content and metadata;
- lexical, vector, and hybrid retrieval;
- filters and facets;
- semantic ranking where selected;
- retrieval for RAG and agent knowledge;
- permission-aware filtering when implemented with reliable security metadata.

AI Search is not the authoritative source repository. The index is a derived retrieval asset that must be rebuildable and synchronized with source permissions and deletions.

## Current Microsoft qualifications

- Azure AI Search supports full-text, vector, hybrid, and multimodal retrieval. Hybrid search runs text and vector queries in parallel and merges the result sets using Reciprocal Rank Fusion; semantic ranking can rerank the initial result set where selected.
- Document-level authorization is not automatic merely because content is indexed. Generally available security filters depend on the application supplying correct identity or group values and applying the filter on every query.
- Native query-time enforcement for ADLS POSIX-style ACLs, Azure RBAC scopes, and Microsoft Purview sensitivity labels is documented as preview. Do not make a production authorization boundary depend on these paths without an approved preview exception and representative tests.
- Indexers detect changed content, but deletion detection requires a supported deletion policy. For Azure Storage indexers, Microsoft states that the policy must exist from the first indexer run; otherwise deleted source objects can remain as orphaned search documents.
- Search limits and capacity depend on pricing model and tier. The Serverless Developer tier is preview and is not a default production choice.

## Retrieval pipeline

```text
Source inventory → extraction → normalization → chunking → metadata/security
→ embedding/indexing → retrieval → reranking/filtering → cited context
→ model/agent → response evaluation
```

## Required design decisions

- authoritative sources and ingestion owner;
- document/chunk identity and version;
- chunking by content type;
- embedding model and migration strategy;
- metadata and filters;
- permission trimming;
- index refresh and deletion propagation;
- hybrid/vector/semantic query strategy;
- citation and provenance format;
- retrieval evaluation dataset;
- prompt-injection and untrusted-content handling;
- capacity, partitions, replicas, and cost.

Record the exact Search API version, SDK version, service tier, region, index schema version, embedding/vectorizer version, permission-trimming approach, and deletion policy. Preview status is feature-specific and must be checked for each selected capability.

## Evaluation

Measure retrieval independently from generation:

- relevant source found at K;
- irrelevant or forbidden content retrieved;
- freshness and deletion behavior;
- citation/source accuracy;
- performance by query type and terminology;
- impact of chunking and embedding changes.

See [Azure AI Search documentation](https://learn.microsoft.com/en-us/azure/search/).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [What is Azure AI Search?](https://learn.microsoft.com/azure/search/search-what-is-azure-search) | 2026-09-19 | Search architecture, indexing, retrieval modes, enrichment, and Foundry relationship |
| [Create a hybrid query](https://learn.microsoft.com/azure/search/hybrid-search-how-to-query) | 2026-09-19 | Parallel text/vector retrieval, RRF, filters, semantic ranking, and preview qualification |
| [Document-level access control](https://learn.microsoft.com/azure/search/search-document-level-access-overview) | 2026-09-19 | Security filters and preview native ACL, RBAC-scope, and sensitivity-label enforcement |
| [Change and delete detection](https://learn.microsoft.com/azure/search/search-how-to-index-azure-blob-changed-deleted) | 2026-09-19 | Change detection, deletion-policy requirements, and orphaned-index risk |
| [Azure AI Search service limits](https://learn.microsoft.com/azure/search/search-limits-quotas-capacity) | 2026-09-19 | Tier-specific quotas, capacity, pricing models, and Serverless Developer preview status |
| [Azure AI Search transparency note](https://learn.microsoft.com/azure/foundry/responsible-ai/search/transparency-note) | 2026-09-19 | System limitations, evaluation responsibility, enrichment, vector, and semantic-search qualifications |

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).
