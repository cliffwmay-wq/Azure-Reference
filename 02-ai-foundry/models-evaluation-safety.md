---
title: Models, Evaluation, and Safety
status: candidate
owner: Product Group AI Platform
review_cycle: monthly
source_posture: Microsoft-Learn-grounded
last_reviewed: 2026-09-19
---

# Models, Evaluation, and Safety

## Model selection

Select a model against the task, not the general reputation of the model. Record:

- modalities and structured-output needs;
- quality on representative cases;
- latency and throughput;
- regional availability and capacity;
- context and output constraints;
- pricing driver;
- data/privacy posture;
- model/version lifecycle;
- fallback and migration plan.

Catalog availability is not enterprise approval. IA, data, licensing, and operational ownership remain required.

Microsoft's catalog distinguishes models sold by Azure from partner and community models. Models from other providers can be Non-Microsoft Products subject to provider-specific terms, support, data-processing, regional, deployment, and safety characteristics. The Product Group must review those dimensions for the exact model and deployment type rather than approve a provider or catalog category wholesale.

Every production record must include the model name and version, provider, lifecycle state, deployment type, processing geography, region, quota/capacity, content-filter configuration, terms owner, retirement date when published, and tested replacement. Model aliases without a resolved version are insufficient release evidence.

## Evaluation dimensions

| Dimension | Examples |
|---|---|
| Task quality | correctness, completeness, classification accuracy, extraction quality |
| Grounding | faithfulness to retrieved evidence, citation precision |
| Tool behavior | correct tool choice, valid arguments, unnecessary calls, safe refusal |
| Safety | prompt injection, harmful content, secret leakage, privilege boundary |
| Operations | latency, error rate, token use, cost, rate-limit behavior |
| Human outcome | override rate, acceptance, correction categories, time saved |

## Evaluation assets

Maintain versioned:

- representative and adversarial cases;
- expected structured results or grading rubric;
- known edge cases;
- tool-call expectations;
- evaluator definitions;
- thresholds for release;
- results tied to model, prompt, agent, tool, and data versions.

Separate automated metrics from human judgment. Neither alone is sufficient for consequential operational decisions.

## Evaluation qualifications

Foundry can evaluate models, agents, datasets, conversations, and captured traces with built-in or custom evaluators. Evaluator release status varies: some agent, conversation, multimodal, safety, and RAG evaluators remain preview even when the broader evaluation capability is GA.

AI-assisted evaluators depend on a judge model and can consume model quota and incur cost. Their output is model-assisted evidence, not an objective determination of correctness, safety, or policy compliance. Calibrate evaluators against representative human review, record the judge model/version and rubric, and retain enough evidence to reproduce the release decision.

Microsoft's safety-evaluation transparency material identifies limits including primarily English evaluation and single-turn evidence. Product Group testing must add domain language, multi-turn behavior, tool use, and human-impact cases where relevant.

## Safety layers

- input validation and file/type constraints;
- content classification where applicable;
- Prompt Shields or equivalent attack detection where applicable;
- treat retrieved content and remote tool output as untrusted;
- system/tool instructions isolated from user-supplied content;
- least-privilege tool access;
- required approval for consequential writes;
- output schema validation and policy checks;
- audit and incident response.

Azure AI Content Safety provides text and image harm detection and additional guardrail capabilities, but the Product Group must test effectiveness for its own domain and language. See [Azure AI Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview).

Prompt Shields can detect direct user-prompt attacks and indirect attacks embedded in documents or tool-returned content. It is one probabilistic control, not an authorization boundary or guarantee that hostile instructions will be blocked. Deterministic authorization, least privilege, data validation, output validation, and human approval remain necessary.

Content Safety performance varies by use case and can produce false positives and false negatives. Microsoft documents broader training/testing for content-harm detection than for several other features: Prompt Shields and multiple additional safety features have been tested primarily in English. Region and processing-route support also varies by feature.

## Tracing and red teaming

Foundry tracing can capture prompts, model outputs, tool calls, intermediate steps, errors, latency, and token use in Application Insights/Log Analytics. Treat trace content as production customer data: minimize or redact sensitive values before collection, restrict readers, define retention, and never assume operational telemetry is safe to collect merely because tracing supports it.

The Foundry AI Red Teaming Agent can automate adversarial probing, but the current documented workflow is preview and has scenario and regional limitations. Automated red teaming supplements—not replaces—threat modeling, manual adversarial review, domain safety testing, and incident-response planning.

## Model lifecycle

Foundry models move through lifecycle states including preview, GA, legacy where used, deprecated, and retired. Availability and upgrade behavior vary by provider, deployment type, region, and cloud. Microsoft documents automatic retirement upgrades for certain Standard deployment types, while provisioned deployments require manual migration. Product teams must monitor the retirement schedule and evaluate replacement behavior before production change.

## Release gate

No production release proceeds without named quality and safety thresholds, reviewed failures, operational capacity, rollback ability, and an owner authorized to accept residual risk.

This is a candidate Product Group release gate. Enterprise reviewers must approve its thresholds, evidence retention, exception path, and residual-risk authority before it becomes an approved baseline.

## Microsoft Learn sources

| Page | Retrieved | Material facts supported |
|---|---|---|
| [Overview of Microsoft Foundry Models](https://learn.microsoft.com/en-us/azure/foundry/concepts/foundry-models-overview) | 2026-09-19 | Model categories, third-party terms, deployment options, catalog lifecycle metadata |
| [Foundry Models sold by Azure](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure) | 2026-09-19 | Azure-hosted and Azure-operated model category, billing, support, deployment, and regional qualifications |
| [Foundry Models from partners and community](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-from-partners) | 2026-09-19 | Non-Microsoft Product classification, provider responsibility, deployment types, and regional availability |
| [Foundry Models lifecycle and support policy](https://learn.microsoft.com/azure/foundry/openai/concepts/model-retirements) | 2026-09-19 | Lifecycle states, regional variation, retirement and upgrade behavior |
| [Model retirement schedule](https://learn.microsoft.com/azure/foundry/openai/concepts/model-retirement-schedule) | 2026-09-19 | Time-sensitive retirement dates and suggested replacements |
| [Run evaluations from the Foundry portal](https://learn.microsoft.com/azure/foundry/how-to/evaluate-generative-ai-app) | 2026-09-19 | Evaluation targets, data sources, built-in/custom evaluators, preview labels |
| [Agent evaluators](https://learn.microsoft.com/azure/foundry/concepts/evaluation-evaluators/agent-evaluators) | 2026-09-19 | System/process evaluators, tool behavior, and evaluator-specific status |
| [Risk and safety evaluators](https://learn.microsoft.com/azure/foundry/concepts/evaluation-evaluators/risk-safety-evaluators) | 2026-09-19 | Content, jailbreak, protected-material, code, and agent-safety evaluation |
| [Risk and safety evaluations transparency note](https://learn.microsoft.com/azure/foundry/concepts/safety-evaluations-transparency-note) | 2026-09-19 | Intended use and language, scope, annotation, and generalization limits |
| [Tracing and data handling](https://learn.microsoft.com/azure/foundry/observability/concepts/trace-data) | 2026-09-19 | Captured customer data, storage, access, privacy, and retention considerations |
| [Run AI Red Teaming Agent locally](https://learn.microsoft.com/azure/foundry/how-to/develop/run-scans-ai-red-teaming-agent) | 2026-09-19 | Preview status, adversarial scans, risk categories, and current limitations |
| [Azure AI Content Safety overview](https://learn.microsoft.com/azure/ai-services/content-safety/overview) | 2026-09-19 | Harm detection, prompt protection, feature and input limits |
| [Prompt Shields](https://learn.microsoft.com/azure/ai-services/content-safety/concepts/jailbreak-detection) | 2026-09-19 | Direct and indirect attack detection |
| [Content Safety region, limit, and language support](https://learn.microsoft.com/azure/ai-services/content-safety/language-support) | 2026-09-19 | Regional processing, feature availability, input limits, tested languages |
| [Content Safety transparency note](https://learn.microsoft.com/azure/foundry/responsible-ai/content-safety/transparency-note) | 2026-09-19 | Accuracy, language, evolving-content, false-positive, and false-negative limits |

Research detail and unresolved enterprise facts are recorded in [Source Record — Models, Evaluation, and Safety](../sources/2026-09-19-models-evaluation-safety.md).
