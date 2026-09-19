---
title: Reference Patterns
status: candidate
owner: Product Group Architecture
review_cycle: quarterly
source_posture: internal-governing
last_reviewed: 2026-09-19
---

# Reference Patterns

## Interactive intelligence

Use for mobile, web, or conversational requests that need a bounded intelligent assessment.

```text
Client → Entra → APIM → Domain API/Function → Foundry agent/model/tools
       → structured result → client
```

Required controls: request identity, schema validation, timeout budget, model and agent version, trace correlation, content/data handling, fallback behavior, and explicit human-review state.

## Operational capability over a legacy system

```text
Agent or app → APIM → domain service → enterprise integration → system of record
```

Expose named business operations, not arbitrary commands, tables, or queries. The domain service validates state and authorization before reaching the legacy integration.

## Image intelligence

```text
Capture → governed object storage → observation record → perception model
        → operational facts + knowledge/rules → reasoned assessment
        → human review → persisted outcome
```

Preserve the original image, event identity, capture metadata, inference version, structured observation, and human correction. Do not treat a model's observation as an authoritative compliance or operational conclusion.

## Retrieval-grounded knowledge

```text
Governed source → ingestion → chunking/metadata → AI Search index
               → permission-aware retrieval → model/agent → cited response
```

Required controls: provenance, classification, access trimming, refresh schedule, deletion propagation, retrieval evaluation, citation behavior, and prompt-injection treatment.

## Asynchronous command

```text
Caller → API → Service Bus queue/topic → worker → system/domain action
      ← accepted/correlation ID        ← status/event
```

Use when the work must survive transient failure, exceed an interactive timeout, buffer load, or decouple producers and consumers. Define idempotency, retries, dead-letter handling, ordering assumptions, and status retrieval.

## Event notification

```text
Producer → Event Grid → interested handlers
```

Use for discrete state-change notifications where subscribers react independently. Events report what happened; they do not direct a particular consumer to perform a transaction.

## High-volume stream

```text
Producers → Event Hubs → stream processors/analytics/storage
```

Use for telemetry or high-throughput ordered streams. Partitioning, retention, checkpointing, replay, and consumer groups must be designed explicitly.

## MCP exposure

```text
Agent client → Toolbox → APIM MCP endpoint → domain APIs/services
```

Use MCP as a portable, curated agent-facing interface. Keep business logic beneath conventional service contracts. Separate read tools from consequential write tools and require approvals where risk warrants.

## Pattern qualifications

- Treat the gateway, messaging, compute, identity, and data services shown in these patterns as replaceable roles until an ADR and enterprise validation select a concrete implementation.
- Event Grid, Event Hubs, and Service Bus have distinct semantics: reactive event routing, high-throughput streams, and transactional messaging. Delivery behavior, ordering, transactions, duplicate detection, retention, and dead-letter behavior must be verified for the selected tier and configuration.
- A gateway decouples clients from internal services, but it doesn't remove the need for domain authorization, state validation, idempotency, or backend audit.
- The legacy-system boundary follows the anti-corruption-layer pattern: translate protocols and semantics without allowing legacy data models to become the new domain contract.
- The MCP pattern governs discovery and invocation of tools; it doesn't make a registered tool safe, authorized, supported, or semantically stable.

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
