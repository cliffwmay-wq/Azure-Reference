---
title: Reference-to-Publication Model
status: approved-baseline
owner: Product Group
review_cycle: quarterly
source_posture: internal-governing
---

# Reference-to-Publication Model

The documentation system deliberately separates platform reference, product knowledge, and product implementation.

## Three units

### Azure Reference

Holds Microsoft-grounded service understanding, Product Group architectural interpretation, approved patterns, selection guidance, cross-cutting controls, and transition facts.

### Product Knowledge Base

Holds concepts, user/operator guidance, FAQs, learning material, terminology, workflows, and troubleshooting appropriate to its audience. It may explain the product without exposing sensitive implementation.

### Product Technical Documentation

Holds system context, architecture, APIs/contracts, data models, security, deployment, configuration, evaluations, operations, support, and change history for one product or capability.

## Forking rule

A product does not copy the Azure Reference wholesale. It links to inherited platform guidance and records only:

- the selected option;
- product-specific configuration;
- justified deviations;
- implementation evidence;
- operating procedures;
- audience-appropriate explanation.

## Provenance

Each downstream page should identify:

- parent reference page or ADR;
- product/version/environment;
- owner;
- status and review date;
- source code/configuration location where applicable;
- sensitivity/publication classification.

## Content promotion

```text
Raw source → source record → normalized reference → reviewed decision
→ product KB/technical page → GitBook publication
```

Microsoft Learn text is summarized and linked, not copied at scale. Internal decisions are clearly distinguished from Microsoft facts.

## Quality gate

Before publication verify accuracy, current links, audience, secret/sensitive-data removal, navigation, ownership, review status, product/version applicability, and downstream impact.

