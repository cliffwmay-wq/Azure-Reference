# Azure Reference Maintainer Instructions

## Mission

Maintain a complete but bounded Product Group Azure Reference. Preserve separation between Microsoft product facts, enterprise facts, Product Group decisions, and hypotheses.

## Non-negotiable principles

- Modernize through the work.
- Technology should serve the flow of work.
- Models perceive; systems of record provide facts; governed knowledge/rules provide standards; agents reason/orchestrate; authorized humans and deterministic controls govern consequential action.
- Intelligence recommends. Authority decides. Systems record.
- API-first underneath. MCP-ready at the edge. Governed throughout.
- Do not build one giant intelligent system.

## Research rules

1. Prefer primary Microsoft Learn sources for Microsoft capability claims.
2. Use the connected Microsoft Learn MCP for discovery and retrieval when available.
3. Record source URL, title, retrieval date, and supported material facts.
4. Summarize; do not copy large sections of Microsoft documentation.
5. Treat MCP results as research, not automatic authority. Review the cited primary page.
6. Identify preview, regional, tier, SDK/API-version, quota, licensing, and retirement qualifications.
7. Never invent enterprise licensing, approval, tenant configuration, or network facts.

## Editing rules

- Keep each service in the page matching its primary responsibility.
- Add a new page only when the inclusion rule in `00-governance/purpose-scope.md` is met.
- Link shared guidance rather than duplicating it.
- Preserve front matter and update status/review metadata.
- Use an ADR for material Product Group selection changes.
- Identify downstream product documentation affected by breaking guidance.
- Keep product-specific schemas, prompts, endpoints, and runbooks out of this reference.

## Required output from a research update

- source record;
- concise reference-page change;
- classification of impact;
- unresolved enterprise facts with owner placeholders;
- downstream impact note;
- no silent conversion of hypothesis into standard.

