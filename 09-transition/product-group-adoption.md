---
title: Product Group Adoption
status: candidate
owner: Product Group Leadership
review_cycle: monthly-during-adoption
source_posture: operating-model
---

# Product Group Adoption

## Roles

| Role | Responsibility |
|---|---|
| Reference owner | coherence, boundaries, lifecycle, final Product Group approval |
| Domain steward | accuracy for AI, API, data, security, application, or operations domain |
| Product owner | ensures product intent and downstream documentation exist |
| Engineering owner | implementation truth, contracts, deployment, support evidence |
| Enterprise reviewer | validates Infrastructure, IA, Data, Applications, or Architecture alignment |
| Documentation publisher | GitBook structure, access, and publication quality |

## Working rhythm

- Update the reference when platform learning is reusable across products.
- Update product Technical Documentation when implementation changes.
- Update Knowledge Base when user/operator behavior changes.
- Open an ADR when a platform or product architectural choice changes.
- Review Foundry/MCP/model content monthly while the platform is moving quickly.
- Run a quarterly cross-domain reference review.

## First implementation method

Use one greenfield product as a robust test of the intent-to-spec-to-development method. The goal is not to prove that agents can generate code. The goal is to test whether the Product Group can repeatedly turn governed intent into a supported, observable, secure product and feed learning back into a reusable platform.

## Adoption measures

- percentage of platform pages with named owners and current review;
- number of product decisions linked to reference pages/ADRs;
- documentation created before production release;
- reusable capabilities produced by product work;
- time to establish a new product environment and documentation set;
- unresolved enterprise facts and age;
- stale/broken source links;
- production incidents caused by undocumented configuration or ownership.

## Anti-patterns

- treating this as one person's notebook;
- copying Microsoft Learn without interpretation;
- publishing prototypes as standards;
- placing all Azure services in scope “just in case”;
- allowing GitBook to become an unreviewed second source of truth;
- hiding uncertainty to make the architecture appear finished.

