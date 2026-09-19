---
title: Legacy and Hybrid Integration
status: candidate
owner: Applications and Infrastructure
review_cycle: quarterly
source_posture: enterprise-alignment-required
last_reviewed: 2026-09-19
---

# Legacy and Hybrid Integration

Legacy integration is treated as a product capability boundary, not exposed implementation detail.

This page defines the boundary and required evidence. It doesn't establish that a specific IBM i, API, middleware, queue, database, network route, or support arrangement exists in the enterprise.

## Preferred pattern

```text
Experience/agent → APIM → domain capability → approved enterprise interface
                 → legacy application/business logic → legacy database
```

For IBM i or comparable platforms, expose specific operations through approved HTTP/service interfaces and existing business logic. Do not give models or general clients arbitrary database, command-line, or program execution access.

This follows Microsoft's anti-corruption-layer pattern: a facade or adapter translates between subsystems with different semantics so legacy schemas, protocols, and implementation choices don't become the modern domain contract. APIM or Functions can help with exposure and translation, but neither product alone supplies the domain mapping, authorization, or transaction rules.

## Capability examples

- Get Shipment Details
- Get Trailer Contents
- Propose Pickup Reassignment
- Report OS&D Exception
- Submit Approved Closeout

Names describe business meaning. The caller should not need to know whether the implementation uses Apache, RPG, DB2, middleware, message queues, or a future replacement platform.

## Required controls

- operation owner and authoritative system;
- input/state validation;
- identity mapping and authorization;
- duplicate/idempotency behavior;
- timeout, retry, and circuit behavior;
- transaction boundary and rollback;
- audit propagation;
- network route and encryption;
- maintenance/outage expectations;
- response contract independent of screen or database layout;
- replacement/migration path.

## Modernization test

Every new legacy integration should answer: does this create a reusable business capability that can survive the eventual replacement of the underlying system? If not, document why the short-lived coupling is justified.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Anti-Corruption Layer pattern](https://learn.microsoft.com/azure/architecture/patterns/anti-corruption-layer) | 2026-09-19 | Facade/adapter isolation, semantic translation, legacy coexistence, and product-neutral boundary |
| [Gateway Routing pattern](https://learn.microsoft.com/azure/architecture/patterns/gateway-routing) | 2026-09-19 | Single endpoint, layer-7 routing, and client/backend decoupling |

Research detail and unresolved enterprise facts are recorded in [Source Record — Architecture, Integration, and Application Platform](../sources/2026-09-19-architecture-integration-application.md).
