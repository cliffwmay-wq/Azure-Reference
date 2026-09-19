---
title: Vocabulary and Status Model
status: approved-baseline
owner: Product Group
review_cycle: quarterly
source_posture: internal-governing
---

# Vocabulary and Status Model

## Core vocabulary

| Term | Product Group meaning |
|---|---|
| Experience | Mobile, web, conversational, or operational surface used by a person or system. |
| Capability | Stable business operation exposed through a governed contract. |
| Intelligence | Models, retrieval, reasoning, rules, and context used to assess or recommend. |
| System of record | Authoritative system that preserves operational state and transaction history. |
| Domain service | Service containing business rules and integration behavior for a bounded domain. |
| Tool | Bounded function an agent may request through a declared schema. |
| Toolbox | Governed, reusable collection of tools made available to compatible agents or runtimes. |
| MCP server | Service that exposes tools, resources, or prompts through the Model Context Protocol. |
| Agent | Versioned component that uses instructions, models, context, tools, and orchestration to pursue a bounded objective. |
| Knowledge | Curated explanatory or evidentiary material with provenance and lifecycle. |
| Rule | Deterministic, governed constraint or policy that should not depend on probabilistic model recall. |
| Evaluation | Repeatable measurement of quality, safety, reliability, cost, and operational fitness. |
| Human review | Authorized judgment captured as an auditable outcome and potential learning signal. |

## Selection status

| Status | Meaning |
|---|---|
| standard | Default for the stated scenario. |
| conditional | Approved when documented conditions are met. |
| candidate | Under evaluation; not yet a default. |
| deferred | Intentionally postponed until scale or risk justifies it. |
| prohibited | Not permitted for the stated use. |
| external dependency | Owned outside the Product Group but required by the pattern. |

## Decision language

- **Must:** non-negotiable Product Group or enterprise requirement.
- **Should:** expected default; deviations require explanation.
- **May:** supported option selected by context.
- **Do not:** explicit boundary or prohibited behavior.

Use these terms only for internal decisions. Microsoft feature descriptions should use factual language and cite the current source.

