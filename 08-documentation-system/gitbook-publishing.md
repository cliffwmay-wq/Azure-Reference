---
title: GitBook Publishing Model
status: candidate
owner: Product Group Documentation
review_cycle: quarterly
source_posture: implementation-guidance
---

# GitBook Publishing Model

GitBook is the publication and navigation layer for approved Knowledge Base and Technical Documentation. Markdown in version control remains the preferred source for reviewable technical content.

## Repository model

Recommended separation:

```text
azure-reference/        # internal platform reference
product-name/
  knowledge-base/       # publishable audience guidance
  technical-docs/       # controlled technical documentation
```

Whether these become separate repositories or bounded folders is an enterprise transition decision. Permissions, publication audience, and lifecycle should drive the choice.

## Publication controls

- Map `SUMMARY.md` to the desired navigation.
- Publish only approved folders/spaces.
- Keep secrets, internal endpoints, raw prompts, sensitive diagrams, and security evidence outside public/broad spaces.
- Link rather than copy shared Azure guidance.
- Use stable relative links within a repository and controlled cross-space links.
- Preview Mermaid, tables, code blocks, and admonitions after import.
- Define branch/review requirements and who can publish.

## Product fork package

Each new product starts with:

- Product Knowledge Base home and audience map;
- Product Technical Document from the template;
- system context and data-flow diagrams;
- inherited Azure reference links;
- ADR directory;
- operational runbooks;
- release/change log;
- publication classification.

## Avoiding drift

Do not manually maintain materially different copies in Git and GitBook. Select the supported synchronization/import workflow during transition, document its directionality, and designate one source of truth.

