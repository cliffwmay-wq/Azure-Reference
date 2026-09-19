---
title: Documentation Governance
status: approved-baseline
owner: Product Group
review_cycle: quarterly
source_posture: internal-governing
---

# Documentation Governance

## Content classes

Every statement should be recognizable as one of four classes:

| Class | Meaning | Example |
|---|---|---|
| Microsoft fact | Verifiable current product behavior | APIM can expose selected REST operations as MCP tools. |
| Enterprise fact | Confirmed tenant, licensing, network, or policy condition | Private endpoints are required for production data services. |
| Product Group decision | Approved local interpretation or standard | APIM is the shared capability gateway. |
| Hypothesis | Candidate direction requiring validation | A Foundry Toolbox should be the default tool boundary for a product family. |

Never allow a hypothesis to become an apparent enterprise requirement through confident wording.

## Page lifecycle

- **draft:** useful but incomplete; not approved for inheritance.
- **candidate:** researched and ready for review.
- **approved-baseline:** accepted for Product Group use.
- **adopted:** validated in at least one supported production implementation.
- **deprecated:** retained to explain migration or historical decisions.
- **superseded:** replaced by a linked page or decision.

## Required metadata

Every reference page must state:

- title;
- status;
- owner;
- review cycle or next review date;
- source posture;
- applicable environments when relevant;
- linked architecture decisions when a choice has been made.

## Change rules

1. Update Microsoft facts when current Learn documentation changes.
2. Change Product Group decisions only with an ADR or equivalent decision record.
3. Do not overwrite uncertainty; record the open question and responsible owner.
4. Product documents link to this reference rather than copying long platform explanations.
5. Breaking guidance changes require a downstream-impact review.
6. Published GitBook content is regenerated or synchronized from governed Markdown.

## Review questions

Every meaningful update should answer:

- What changed in the source platform?
- Does it change our selected pattern or only implementation options?
- Which products inherit the guidance?
- Does it affect security, licensing, cost, support, or data handling?
- What must be retested?
- What prior statement is now obsolete?

## Feedback path

Questions and corrections enter as a documentation issue containing:

- page and exact statement;
- evidence or Microsoft Learn link;
- proposed classification: fact, decision, hypothesis, or implementation detail;
- affected products;
- urgency and operational consequence.

The page owner resolves the issue directly or routes it to Architecture, Infrastructure, Information Assurance, Data, or Product ownership.

