---
title: Azure Machine Learning
status: candidate
owner: Product Group ML Platform
review_cycle: quarterly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Azure Machine Learning

Azure Machine Learning is the primary candidate for controlled custom ML and computer-vision lifecycle when the Product Group must train, evaluate, register, deploy, and monitor its own models.

## Use Azure ML for

- managed training jobs and compute;
- experiments and reproducibility;
- data/model assets and lineage;
- pipelines;
- model registry and controlled promotion;
- managed online or batch endpoints;
- environment/version management;
- ML-oriented monitoring and MLOps.

## Foundry and Azure ML split

| Responsibility | Microsoft Foundry | Azure Machine Learning |
|---|---|---|
| Hosted model discovery/deployment | primary | supporting/integrated where applicable |
| Agent application and tools | primary | not primary |
| Prompt and agent evaluation | primary | can support ML evaluation workflows |
| Custom CV/ML training | conditional | primary candidate |
| Experiment tracking and pipelines | supporting | primary |
| Custom model registry/endpoints | conditional | primary |

This is a responsibility split, not an organizational wall. A custom Azure ML endpoint may be exposed as a domain capability/tool used by a Foundry agent.

This split is a candidate Product Group interpretation. It does not assert that Azure Machine Learning is licensed, deployed, network-approved, or supported by the enterprise.

## Lab-to-production path

```text
Governed image/data storage → curated dataset → baseline experiment
→ approved training environment → evaluation → registry/version
→ controlled endpoint → API/tool → human outcomes → next dataset/version
```

Begin narrow: one decision-support use case, controlled data, simple baselines, shadow-mode validation, and manual review. Defer AKS, feature stores, autonomous retraining, broad multimodal scope, and automatic feedback ingestion until evidence justifies them.

## Required records

- dataset version, provenance, labeling guidance, and access;
- training code, environment, parameters, and compute;
- experiment and evaluation results;
- model card, intended use, exclusions, and limitations;
- registry version and promotion approval;
- endpoint configuration and capacity;
- monitoring, drift/quality review, rollback, and retirement;
- human feedback acceptance and curation process.

## Current Microsoft qualifications

- Azure Machine Learning manages the custom ML lifecycle across training, experiment tracking, model registration, deployment, and MLOps.
- Managed online endpoints provide managed real-time inferencing; batch endpoints address asynchronous batch scoring. Endpoint choice, compute, autoscaling, network, authentication, quota, and cost still require explicit design.
- Machine Learning registries can share versioned models, environments, components, and data assets across workspaces and support promotion across development, test, and production boundaries.
- Model monitoring compares production inference data with reference data and can track signals such as data drift, prediction drift, data quality, feature-attribution drift, and model performance. Signal applicability varies by task and data format, and some signals remain preview.
- Enabling production data collection can log request and response payloads or custom inference data to Azure Blob Storage. Data classification, minimization, access, retention, regional placement, and consent must be approved before collection.
- Monitoring or a Responsible AI dashboard supplies evidence; neither automatically authorizes retraining, promotion, or consequential use.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [What is Azure Machine Learning?](https://learn.microsoft.com/azure/machine-learning/overview-what-is-azure-machine-learning?view=azureml-api-2) | 2026-09-19 | Managed ML lifecycle, training, deployment, and MLOps |
| [MLOps model management](https://learn.microsoft.com/azure/machine-learning/concept-model-management-and-deployment?view=azureml-api-2) | 2026-09-19 | Experiment lineage, registration, packaging, deployment, and automation |
| [Machine Learning registries for MLOps](https://learn.microsoft.com/azure/machine-learning/concept-machine-learning-registries-mlops?view=azureml-api-2) | 2026-09-19 | Cross-workspace assets and environment promotion |
| [Online endpoint deployment](https://learn.microsoft.com/azure/machine-learning/concept-endpoints-online?view=azureml-api-2) | 2026-09-19 | Managed real-time endpoint responsibility and capabilities |
| [Azure Machine Learning model monitoring](https://learn.microsoft.com/azure/machine-learning/concept-model-monitoring?view=azureml-api-2) | 2026-09-19 | Monitoring signals, reference data, thresholds, alerts, and limitations |
| [Production model data collection](https://learn.microsoft.com/azure/machine-learning/concept-data-collection?view=azureml-api-2) | 2026-09-19 | Input/output logging, Blob Storage, sampling, and supported endpoints |
| [Responsible AI in Azure Machine Learning](https://learn.microsoft.com/azure/machine-learning/concept-responsible-ai?view=azureml-api-2) | 2026-09-19 | Responsible AI lifecycle and accountability tooling |

Research detail and unresolved enterprise facts are recorded in [Source Record — Models, Evaluation, and Safety](../sources/2026-09-19-models-evaluation-safety.md).
