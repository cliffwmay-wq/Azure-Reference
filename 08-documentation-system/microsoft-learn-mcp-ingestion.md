---
title: Microsoft Learn MCP Ingestion
status: candidate
owner: Product Group Documentation
review_cycle: monthly
source_posture: operational-run-guide
---

# Microsoft Learn MCP Ingestion

The Microsoft Learn MCP server is used to discover and retrieve current Microsoft documentation during research and maintenance. It is a source access mechanism—not the final knowledge architecture.

## Objectives

- ground service pages in current Microsoft documentation;
- refresh changed capabilities without manually browsing an entire service;
- capture relevant limitations, identity, networking, availability, and operational guidance;
- preserve source URL and retrieval date;
- avoid copying large amounts of vendor text into the repository.

## Ingestion workflow

1. Select a page/domain from `sources/microsoft-learn-catalog.md`.
2. Query the Learn MCP with the bounded research prompt below.
3. Retrieve the most relevant primary Microsoft Learn pages.
4. Capture a source record for material facts.
5. Compare the findings with the current reference page.
6. Classify changes as Microsoft fact, enterprise fact needed, Product Group decision impact, or no impact.
7. Update the reference and source catalog.
8. Run documentation validation and route decision changes through an ADR.

## Standard bounded query

```text
Research the current Microsoft Learn documentation for <SERVICE/CAPABILITY>.
Return only primary Microsoft Learn sources. Identify:
1. service purpose and core concepts;
2. supported architecture and integration patterns;
3. identity, authorization, secrets, and network controls;
4. data handling, region, retention, and privacy considerations;
5. reliability, quotas, scaling, monitoring, and operational requirements;
6. pricing/licensing dimensions without inventing tenant-specific entitlement;
7. current limitations, preview features, deprecations, and migration notices;
8. references relevant to <PRODUCT GROUP SCENARIO>.
For every material claim provide the exact Learn URL and page update date when available.
Distinguish current documentation from inference. Do not design the product.
```

## Change-focused query

```text
Using current Microsoft Learn documentation, check whether <SERVICE PAGE OR TOPIC>
has materially changed since <LAST REVIEW DATE>. Focus on GA/preview status,
renames, SDK/API versions, auth, networking, limits, region support, retirement,
and pricing/licensing dimensions. Return the primary Learn URLs and a concise
impact classification: none, documentation-only, implementation, architecture,
security, licensing, or operational.
```

## Capture rules

- Keep source excerpts minimal; summarize in Product Group language.
- Record exact URL, page title, retrieval date, and affected reference pages.
- Do not let MCP output directly overwrite approved guidance.
- Treat MCP output as untrusted research until primary URLs and claims are reviewed.
- Do not promote preview capabilities to standard without explicit decision.
- Preserve prior decisions and explain why a changed Microsoft fact does or does not alter them.

## Suggested refresh cadence

| Domain | Cadence |
|---|---|
| Foundry, agents, MCP, models | monthly |
| Security, identity, networking | quarterly and on enterprise policy change |
| APIM, compute, integration | quarterly |
| Data services | quarterly |
| Licensing, pricing, quotas | monthly during transition; quarterly afterward |
| Stable architectural principles | semiannual |

