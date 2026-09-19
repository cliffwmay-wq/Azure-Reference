---
title: Data Responsibility Model
status: candidate
owner: Product Group Data Steward
review_cycle: quarterly
source_posture: internal-governing
last_reviewed: 2026-09-19
---

# Data Responsibility Model

## Data roles

| Role | Meaning |
|---|---|
| Authoritative operational data | Current business state owned by a system of record |
| Evidence | Images, documents, messages, and observations supporting later assessment |
| Derived data | Features, embeddings, summaries, classifications, or aggregates generated from sources |
| Knowledge | Curated information intended to explain or ground decisions |
| Rules | Governed deterministic standards or constraints |
| Telemetry | Technical and business signals used for operation and audit |
| Evaluation data | Controlled cases and expected outcomes used to measure fitness |
| Feedback | Human judgment or downstream outcome captured for learning and review |

Derived data never silently replaces its source. Every derived asset requires lineage to the source, process/model version, creation time, and applicable retention/deletion behavior.

## Authority boundary

Storage location, catalog registration, search indexing, certification, endorsement, or model use does not by itself make data authoritative. Authority comes from a named business owner, an approved data contract, and a defined process for correction, reconciliation, retention, and access.

For each material data element, record:

- authoritative system and business owner;
- system-of-entry and permitted writers;
- published data contract and semantic owner;
- freshness and reconciliation expectation;
- allowed derived copies, indexes, embeddings, and analytical products;
- correction and deletion propagation path;
- evidence needed to reconstruct consequential decisions.

Microsoft Purview, OneLake Catalog, and similar catalogs can describe, classify, and help users discover data. They do not replace the source system's authorization controls or the Product Group decision that identifies authoritative truth.

## Required questions

- Who owns and stewards the data?
- What is the authoritative source?
- What classification and regulatory obligations apply?
- Is the Product Group permitted to copy, transform, embed, train on, or transmit it to a model?
- What is the retention and deletion rule?
- How is access filtered by user, terminal, customer, or operational scope?
- What happens when the source changes or is deleted?
- Which region and network boundary contains it?
- What is logged, and could logs create a new sensitive copy?
- How can a decision be reconstructed later?

## AI-specific boundaries

- Training permission is distinct from inference permission.
- Retrieval permission is distinct from permission to reveal retrieved content in a response.
- Embeddings are governed derived data, not automatically non-sensitive.
- Prompt, response, and trace retention must be deliberately configured and documented.
- Human corrections require curation before they become training truth.
- Changeable standards belong in governed knowledge/rules, not solely in model weights.

## Data product handoff

Every product Technical Document records source systems, contracts, storage locations, classification, owners, lineage, retention, access, quality controls, and recovery requirements. This reference defines the questions; the product document supplies the answers.

Research detail and unresolved enterprise facts are recorded in [Source Record — Data and Governed Knowledge](../sources/2026-09-19-data-governed-knowledge.md).
