---
title: Delivery, IaC, and Change
status: candidate
owner: Product Group Engineering
review_cycle: quarterly
source_posture: internal-governing
last_reviewed: 2026-09-19
---

# Delivery, IaC, and Change

## Source and deployment

Git is the source of truth for application code, infrastructure definitions, agent definitions, prompts, tool contracts, evaluations, and documentation. Azure portal changes are useful for exploration but must be reconciled into source before production reliance.

## Infrastructure as Code

Use enterprise-approved Bicep or Terraform patterns. Record module ownership, versioning, state/backends, provider versions, policy compliance, environment values, secret references, and deployment identity.

The enterprise has not yet selected the approved repository, pipeline platform, module registry, runner model, or deployment identity pattern. This page defines candidate controls, not an Azure DevOps or GitHub entitlement.

## Current Microsoft qualifications

- Bicep is declarative and idempotent for Azure Resource Manager deployments and supports Azure resource types and API versions, including preview versions. IaC use doesn't make a preview resource API suitable for production; version/status review remains required.
- ARM/Bicep what-if predicts create, update, and delete effects without applying them. It has evaluation and expansion limits and requires deployment-level permissions. A what-if result is review evidence, not proof that deployment will succeed or that the change is safe.
- Azure DevOps approvals and checks can be owned outside pipeline YAML by protected-resource administrators. Branch control, required templates, approvals, external checks, Azure Monitor checks, and exclusive locks can prevent a stage from starting.
- GitHub Actions can authenticate to Azure using OpenID Connect with a federated identity. Microsoft marks a service-principal client secret as not recommended. Workload identity scope, subject claims, environment protection, and Azure permissions still require least privilege.
- Microsoft's GitHub IaC pattern separates pull-request validation and preview from reviewed deployment through protected environments. The Product Group must preserve equivalent separation on whichever enterprise pipeline is approved.

## Pipeline controls

- build, lint, unit, contract, security, and dependency checks;
- infrastructure validation/plan;
- agent/model evaluation gates;
- artifact versioning and provenance;
- environment approvals;
- deployment health verification;
- rollback and forward-fix paths;
- release notes and downstream documentation impact.

For production, retain the reviewed commit, artifact digest, dependency/SBOM evidence where required, evaluation results, infrastructure preview, approver identity, deployment identity, policy results, deployment output, smoke/health results, rollback decision, and linked incident or exception.

## AI change units

Treat each as a versioned change that may require evaluation:

- model/version/deployment;
- system instructions or prompt;
- tool description/schema/permission;
- Toolbox membership;
- retrieval source/index/chunking/embedding;
- policy/safety threshold;
- structured output contract;
- evaluation rubric or dataset.

## Environment promotion

Promote reviewed immutable artifacts and declarative definitions. Never assume a visually similar portal configuration is equivalent. Capture configuration drift and emergency changes, then reconcile them back to source.

Sources: [Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/), [Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/), and [GitHub Actions for Azure](https://learn.microsoft.com/en-us/azure/developer/github/github-actions).

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [What is Bicep?](https://learn.microsoft.com/azure/azure-resource-manager/bicep/overview) | 2026-09-19 | Declarative syntax, idempotency, API-version support, consistency, and what-if integration |
| [Bicep what-if](https://learn.microsoft.com/azure/azure-resource-manager/bicep/deploy-what-if) | 2026-09-19 | Non-mutating predicted changes, permissions, validation levels, and expansion limitations |
| [Azure Pipelines approvals and checks](https://learn.microsoft.com/azure/devops/pipelines/process/approvals?view=azure-devops) | 2026-09-19 | Resource-owner checks, approvals, branch control, protected resources, timeouts, and locks |
| [Use GitHub Actions to connect to Azure](https://learn.microsoft.com/azure/developer/github/connect-from-azure) | 2026-09-19 | OIDC, managed identity, service-principal secret options, and recommendation status |
| [Deploy infrastructure with GitHub Actions](https://learn.microsoft.com/devops/deliver/iac-github-actions) | 2026-09-19 | Branch/PR workflow, IaC validation, preview, protected production environment, and federation |

Research detail and unresolved enterprise facts are recorded in [Source Record — Operations and Delivery](../sources/2026-09-19-operations-delivery.md).
