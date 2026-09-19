---
title: Source Record — Models, Evaluation, and Safety
status: current
owner: Product Group Documentation
retrieved: 2026-09-19
---

# Source Record — Models, Evaluation, and Safety

## Research question

What current Microsoft Learn facts materially qualify the Product Group's candidate guidance for Foundry model selection and lifecycle, evaluation, tracing, safety controls, red teaming, and the Azure Machine Learning boundary?

## Primary Microsoft Learn sources

| Page title | URL | Page date | Retrieved |
|---|---|---|---|
| Overview of Microsoft Foundry Models | https://learn.microsoft.com/en-us/azure/foundry/concepts/foundry-models-overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Foundry Models sold by Azure | https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Foundry Models from partners and community | https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-from-partners | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Microsoft Foundry Models lifecycle and support policy | https://learn.microsoft.com/azure/foundry/openai/concepts/model-retirements | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Model retirement schedule | https://learn.microsoft.com/azure/foundry/openai/concepts/model-retirement-schedule | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Run evaluations from the Microsoft Foundry portal | https://learn.microsoft.com/azure/foundry/how-to/evaluate-generative-ai-app | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Agent evaluators | https://learn.microsoft.com/azure/foundry/concepts/evaluation-evaluators/agent-evaluators | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Risk and safety evaluators | https://learn.microsoft.com/azure/foundry/concepts/evaluation-evaluators/risk-safety-evaluators | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Microsoft Foundry risk and safety evaluations Transparency Note | https://learn.microsoft.com/azure/foundry/concepts/safety-evaluations-transparency-note | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Tracing and data handling | https://learn.microsoft.com/azure/foundry/observability/concepts/trace-data | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Run AI Red Teaming Agent locally | https://learn.microsoft.com/azure/foundry/how-to/develop/run-scans-ai-red-teaming-agent | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Azure AI Content Safety? | https://learn.microsoft.com/azure/ai-services/content-safety/overview | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Prompt Shields | https://learn.microsoft.com/azure/ai-services/content-safety/concepts/jailbreak-detection | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Content Safety region availability and service limits | https://learn.microsoft.com/azure/ai-services/content-safety/language-support | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Transparency note: Azure AI Content Safety | https://learn.microsoft.com/azure/foundry/responsible-ai/content-safety/transparency-note | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Azure Machine Learning? | https://learn.microsoft.com/azure/machine-learning/overview-what-is-azure-machine-learning?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| MLOps model management with Azure Machine Learning | https://learn.microsoft.com/azure/machine-learning/concept-model-management-and-deployment?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Machine Learning registries for MLOps | https://learn.microsoft.com/azure/machine-learning/concept-machine-learning-registries-mlops?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Online endpoint deployment for real-time inferencing | https://learn.microsoft.com/azure/machine-learning/concept-endpoints-online?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Azure Machine Learning model monitoring | https://learn.microsoft.com/azure/machine-learning/concept-model-monitoring?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| Data collection from models in production | https://learn.microsoft.com/azure/machine-learning/concept-data-collection?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |
| What is Responsible AI? | https://learn.microsoft.com/azure/machine-learning/concept-responsible-ai?view=azureml-api-2 | Not exposed by Learn MCP retrieval | 2026-09-19 |

## Material Microsoft facts

| Fact | Source | Confidence/qualification |
|---|---|---|
| Foundry's catalog includes models sold by Azure and partner/community models; models from other providers can be Non-Microsoft Products subject to separate terms. | Foundry Models overview; sold-by-Azure and partner/community model pages | High; exact terms and support vary by model/provider. |
| Model availability depends on model/version, region, cloud, deployment type, quota, and security requirements. | Models overview; lifecycle policy | High; time-sensitive. |
| Foundry models move through documented lifecycle states and ultimately retire; automatic-upgrade behavior differs by deployment type, and provisioned deployments require manual migration. | Model lifecycle policy | High; retirement schedule must be checked continuously. |
| Foundry evaluations can target models, agents, datasets, conversations, and traces with built-in or custom evaluators. | Run evaluations | High; individual evaluator and scope status varies. |
| Several agent, conversation, multimodal, safety, and RAG evaluation capabilities are explicitly preview. | Run evaluations; evaluator pages | High; status is evaluator-specific. |
| AI-assisted evaluation consumes judge-model quota and produces model-assisted evidence that must be calibrated for the use case. | Run evaluations; safety transparency note | High; judge behavior and data affect results. |
| Microsoft's documented validation for risk and safety evaluations is primarily English and includes single-turn limitations. | Safety-evaluation transparency note | High; domain and multi-turn generalization are not established. |
| Foundry traces can capture prompts, responses, tool calls, intermediate steps, and execution metadata in connected Application Insights/Log Analytics. | Tracing and data handling | High; trace content can include personal and customer data. |
| The AI Red Teaming Agent automates adversarial probing but its documented local workflow is preview and has region and scenario limits. | Run AI Red Teaming Agent | High; not a substitute for comprehensive assurance. |
| Prompt Shields examines direct user prompts and indirect instructions in documents or tool responses. | Prompt Shields | High; probabilistic detection is not an authorization control. |
| Content Safety performance can include false positives and false negatives; tested languages and processing routes vary by feature. | Content Safety transparency and availability | High; application-specific testing is required. |
| Azure Machine Learning supports training, experiment tracking, registration, deployment, MLOps, registries, managed endpoints, and model monitoring. | Azure Machine Learning overview and MLOps sources | High; enterprise availability remains unverified. |
| Azure Machine Learning production data collection can store model inputs and outputs in Blob Storage for monitoring, debugging, and audit. | Production model data collection | High; data governance is required before enablement. |
| Built-in model-monitoring signals emphasize supported tabular scenarios, and some signals remain preview. | Model monitoring | High; monitoring coverage is task- and format-specific. |

## Limitations, previews, and deprecations

- Catalog presence and Microsoft Responsible AI review do not guarantee that a model is safe or suitable for the Product Group's use case.
- Model and version availability, lifecycle, region, processing geography, quota, deployment type, terms, and automatic upgrade behavior are time-sensitive.
- Evaluator and evaluation-scope status varies; preview features must not silently become production release dependencies.
- Model-assisted judges inherit model limits and can disagree with human reviewers.
- Safety-evaluation evidence documented by Microsoft does not establish broad non-English or multi-turn generalization.
- Tracing and production model data collection can persist sensitive inputs, outputs, tool arguments, and inference payloads.
- AI Red Teaming Agent is preview in the retrieved implementation guide.
- Content Safety and Prompt Shields are probabilistic and require representative application testing.
- Azure Machine Learning monitoring signals and data collectors do not cover every endpoint, task, modality, or data shape.
- Learn MCP retrieval did not expose page-update dates; retrieval dates are recorded instead.

## Enterprise facts still required

| Enterprise fact | Owner |
|---|---|
| Approved providers, models, versions, deployment types, regions, processing geographies, terms, and retirement ownership | AI Platform / Information Assurance / Procurement |
| Approved production use of preview models, evaluators, red-teaming capabilities, and safety features | Architecture / Information Assurance |
| Required evaluation datasets, human-review rubrics, judge models, thresholds, release exceptions, evidence retention, and residual-risk authority | AI Platform / Product / Information Assurance |
| Trace capture, redaction, access, destination, retention, and incident-use policy | Information Assurance / Observability |
| Required Content Safety/Prompt Shields configuration, supported languages, false-positive/negative tolerance, appeal path, and monitoring | Information Assurance / Product |
| Whether Azure Machine Learning is the supported custom ML platform and its approved workspaces, registries, compute, endpoints, network, and identities | ML Platform / Architecture / Infrastructure |
| Whether production inference data collection is allowed and its classification, storage, sampling, access, retention, and deletion controls | Data / Information Assurance / ML Platform |

## Product Group decision impact

**security**

The existing candidate boundary remains reasonable: Foundry for hosted models and agent/application evaluation, Azure Machine Learning as the primary custom-ML candidate, and deterministic/human controls for consequential authority. Implementation must add exact model lifecycle ownership, evaluator calibration, trace governance, language-specific safety testing, and production-data controls. No page was promoted and no enterprise approval was inferred.

## Reference pages affected

- `02-ai-foundry/models-evaluation-safety.md`
- `02-ai-foundry/azure-machine-learning.md`
- `sources/microsoft-learn-catalog.md`
- `sources/research-backlog.md`

## Downstream impact note

Review product documentation that identifies only a model family without a version, treats catalog availability as approval, assumes evaluation results are objective, relies on preview evaluators for a production gate, logs prompts or inference payloads without data controls, treats Prompt Shields as a security boundary, or assumes Azure Machine Learning monitoring covers every model type. No downstream product repositories were identified in this workspace.

## Reviewer and review date

Reviewer: AI Platform / ML Platform / Information Assurance / Product (pending)

Review date: pending
