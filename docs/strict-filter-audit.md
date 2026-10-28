# Uniform MAS and Database-Venue Filter

Updated 2026-10-27. [Current admitted papers](strict-db-mas-papers.md) · [Planning decision](planning-literature-review.md) · [Full decisions and source snapshots](../data/strict_mas_review.json)

## Admission rules

1. **Venue and date:** publication years 2024–2026 in ICDE, SIGMOD/PACMMOD or PVLDB, plus a separately labeled CIDR extension. Workshops, journals and other conferences do not enter the current main list. Conference cycles are recorded separately: NOMA is a 2026 publication in the VLDB 2027 cycle.
2. **MAS:** the primary source must establish cooperating LLM agents, their roles and information/result exchange. Multiple calls, tools, models, pipeline candidates or independent agent comparisons are insufficient.
3. **Direction:** identify the data-system mechanism improving the collaboration itself. Using agents for SQL generation, data preparation, analysis or visualization does not automatically pass. An application qualifies only for a specifically identified MAS support component and evidence about that component.
4. **Evidence and placement:** distinguish systems, visions and application-embedded components. Retained entries need inspected primary-source sections and one primary layer/topic. Missing evidence means not admitted, not proven irrelevant.

## Sources and coverage

The same admission predicate was applied to **691 existing records** and the **60-record seed inventory**. Repository scanning extracted **452 linked candidate entries** (160 from HKUSTDial and 292 from kyegomez), including duplicate work versions, products and blogs. These are not 452 unique papers.

Matching used normalized titles, manually checked title aliases, the existing library, 5,790 cached conference metadata records and 2,092 cached official PVLDB entries. Likely and boundary cases were checked against author papers, official conference pages or publisher records. This is not a completed full-paper review of 691 entries or an exhaustive venue search for every unmatched preprint.

| Repository | README commit | Snapshot date |
|---|---|---|
| [HKUSTDial/awesome-data-agents](https://github.com/HKUSTDial/awesome-data-agents) | [31a225514eed](https://github.com/HKUSTDial/awesome-data-agents/blob/31a225514eed2e60f2a5a425cadf4f715ea5f6e0/README.md) | 2026-08-05T05:37:55Z |
| [kyegomez/awesome-multi-agent-papers](https://github.com/kyegomez/awesome-multi-agent-papers) | [ee79d662180c](https://github.com/kyegomez/awesome-multi-agent-papers/blob/ee79d662180c7a699cfe790c3092d266e50403cf/README.md) | 2026-10-23T22:53:45Z |

**Result: 15 admitted records; no new bibliographic record was added to the existing library.** The initial five-record display was incomplete. The follow-up [Planning / Execution review](planning-execution-review.md) restores documented components from previously withheld application papers. Remaining unreviewed M-labeled records are pending mechanism review, not negative findings. Related demos are linked without counting a second independent mechanism.

| Existing-library decision | Records |
|---|---:|
| `excluded_agent_scope` | 3 |
| `excluded_overview` | 33 |
| `excluded_venue` | 1 |
| `excluded_workshop` | 1 |
| `hold_primary_content` | 2 |
| `include_component` | 10 |
| `include_system` | 3 |
| `include_vision` | 2 |
| `not_admitted_direction` | 5 |
| `not_admitted_evidence` | 597 |
| `not_admitted_mas` | 12 |
| `pending_mechanism_review` | 20 |
| `related_demo_not_independent_method` | 2 |

## Decisions that matter for Planning

| Paper / source | Decision | Evidence and boundary |
|---|---|---|
| [DataLab](https://arxiv.org/html/2412.02205v3), ICDE 2025; kyegomez list | Admit only the communication component; **Execution** | §V defines structured information units and shared-buffer exchange between proxy/specialist agents; §VII-D evaluates that mechanism. The notebook DAG (§VI) is for context retrieval, not Planning-task extraction. |
| [AllHands](https://www.microsoft.com/en-us/research/publication/allhands-ask-me-anything-on-large-scale-verbatim-feedback-via-large-language-models/), ICDE 2025; kyegomez list | Not admitted | Author abstract and §3.4 describe one QA-agent framework with internal planner/code-generation/execution components. The inspected material does not establish the required cooperating MAS. |
| [DocETL](https://www.vldb.org/pvldb/vol18/p3035-shankar.pdf) | Not admitted to DB for MAS | Multiple generation/validation agents are real, but they optimize document-processing queries. A multi-agent optimizer is not the same as an optimizer for a MAS. |
| [AOP](https://www.vldb.org/cidrdb/papers/2025/p32-wang.pdf), SIC, Palimpzest, LOTUS, Abacus | Not admitted as analogous methods | Logical or physical data pipelines alone do not establish a collaborating MAS as the object being improved. |
| [From RAG to Agentic AI](https://www.vldb.org/2025/Workshops/VLDB-Workshops-2025/LLM%2BGraph/LLMGraph-8.pdf) | Excluded from main conference list | Explicit MAS vision, but LLM+Graph@VLDB workshop. |
| [AFlow](https://proceedings.iclr.cc/paper_files/paper/2025/hash/5492ecbce4439401798dcd2c90be94cd-Abstract-Conference.html) | Excluded venue | ICLR 2025, not a target DB venue. |
| [Planning with Multi-Constraints via Collaborative Language Agents](https://aclanthology.org/2025.coling-main.672/) | Excluded venue | COLING 2025, not a target DB venue. |
| [stratum](https://www.vldb.org/pvldb/vol19/p3799-phani.pdf) | MAS evidence not established | §§2–5 study execution of candidate ML pipelines generated by AIDE. Multiple pipelines do not establish collaborating agents; MAS papers in its references do not change that. |
| [Efficient Neural-Symbolic Data System via Multi-Agent Collaboration](https://icde2026.github.io/deft-papers.html) | Hold for primary content | ICDE 2026 DEFT metadata is confirmed; content-level direction and mechanism remain insufficiently verified. No title-based Planning assignment. |

## Repository leads linked to existing DB publication records

This table records identity matching, not admission. Older broad agent labels remain archival. An exclusion based on insufficient mechanism evidence can change after further primary-source reading.

| Repository | Matched publication | Current decision |
|---|---|---|
| awesome-data-agents | [GPTuner: A Manual-Reading Database Tuning System via GPT-Guided Bayesian Optimization](https://doi.org/10.14778/3659437.3659449) | `not_admitted_evidence` |
| awesome-data-agents | [λ-Tune: Harnessing Large Language Models for Automated Database System Tuning](https://doi.org/10.1145/3709652) | `not_admitted_evidence` |
| awesome-data-agents | [E2ETune: End-to-End Knob Tuning via Fine-tuned Generative Language Model](https://doi.org/10.14778/3773731.3773732) | `not_admitted_evidence` |
| awesome-data-agents | [LLM-R2: A Large Language Model Enhanced Rule-based Rewrite System for Boosting Query Efficiency](https://doi.org/10.14778/3696435.3696440) | `not_admitted_evidence` |
| awesome-data-agents | [GenRewrite: Query Rewriting via Large Language Models](https://doi.org/10.1145/3786684) | `not_admitted_evidence` |
| awesome-data-agents | [Can Large Language Models Be Query Optimizer for Relational Databases?](https://doi.org/10.1145/3769771) | `not_admitted_evidence` |
| awesome-data-agents | [DBG-PT: A Large Language Model Assisted Query Performance Regression Debugger](https://doi.org/10.14778/3685800.3685869) | `not_admitted_evidence` |
| awesome-data-agents | [Automatic Database Configuration Debugging using Retrieval-Augmented Language Models](https://doi.org/10.1145/3709663) | `not_admitted_evidence` |
| awesome-data-agents | [RetClean: Retrieval-Based Tabular Data Cleaning Using LLMs and Data Lakes](https://doi.org/10.14778/3685800.3685890) | `not_admitted_evidence` |
| awesome-data-agents | [Data Imputation with Limited Data Redundancy Using Data Lakes](https://doi.org/10.14778/3748191.3748200) | `not_admitted_evidence` |
| awesome-data-agents | [Table-GPT: Table Fine-tuned GPT for Diverse Table Tasks](https://doi.org/10.1145/3654979) | `not_admitted_evidence` |
| awesome-data-agents | [Cost-Effective In-Context Learning for Entity Resolution: A Design Space Exploration](https://doi.org/10.1109/icde60146.2024.00284) | `not_admitted_evidence` |
| awesome-data-agents | [ArcheType: A Novel Framework for Open-Source Column Type Annotation using Large Language Models](https://doi.org/10.14778/3665844.3665857) | `not_admitted_evidence` |
| awesome-data-agents | [AutoDDG: Automated Dataset Description Generation using Large Language Models](https://doi.org/10.1145/3786626) | `not_admitted_evidence` |
| awesome-data-agents | [Pneuma : Leveraging LLMs for Tabular Data Representation and Retrieval in an End-to-End System](https://doi.org/10.1145/3725337) | `not_admitted_evidence` |
| awesome-data-agents | [Text-to-SQL Empowered by Large Language Models: A Benchmark Evaluation](https://doi.org/10.14778/3641204.3641221) | `not_admitted_evidence` |
| awesome-data-agents | [The Dawn of Natural Language to SQL: Are We Fully Ready? [Experiment, Analysis & Benchmark ]](https://doi.org/10.14778/3681954.3682003) | `not_admitted_evidence` |
| awesome-data-agents | [Rabbit: Retrieval-Augmented Generation Enables Better Automatic Database Knob Tuning](https://doi.org/10.1109/icde65448.2025.00284) | `pending_mechanism_review` |
| awesome-data-agents | [MCTuner: Spatial Decomposition-Enhanced Database Tuning via LLM-Guided Exploration](https://doi.org/10.1145/3769807) | `not_admitted_evidence` |
| awesome-data-agents | [AgentTune: An Agent-Based Large Language Model Framework for Database Knob Tuning](https://doi.org/10.1145/3769758) | `pending_mechanism_review` |
| awesome-data-agents | [R-Bot: An LLM-based Query Rewrite System](https://doi.org/10.14778/3750601.3750625) | `not_admitted_evidence` |
| awesome-data-agents | [Cracking SQL Barriers: An LLM-based Dialect Translation System](https://doi.org/10.1145/3725278) | `not_admitted_evidence` |
| awesome-data-agents | [D-Bot: Database Diagnosis System using Large Language Models](https://doi.org/10.14778/3675034.3675043) | `include_component` |
| awesome-data-agents | [DBAIOps: A Reasoning LLM-Enhanced Database Operation and Maintenance System using Knowledge Graphs](https://doi.org/10.14778/3797919.3797937) | `not_admitted_evidence` |
| awesome-data-agents | [AutoPrep: Natural Language Question-Aware Data Preparation with a Multi-Agent Framework](https://doi.org/10.14778/3748191.3748211) | `not_admitted_direction` |
| awesome-data-agents | [Weak-to-Strong Prompts with Lightweight-to-Powerful LLMs for High-Accuracy, Low-Cost, and Explainable Data Transformation](https://doi.org/10.14778/3742728.3742734) | `not_admitted_evidence` |
| awesome-data-agents | [DeepPrep: An LLM-Powered Agentic System for Autonomous Data Preparation](https://doi.org/10.14778/3836663.3836695) | `not_admitted_evidence` |
| awesome-data-agents | [Agent-OM: Leveraging LLM Agents for Ontology Matching](https://doi.org/10.14778/3712221.3712222) | `pending_mechanism_review` |
| awesome-data-agents | [CHORUS: Foundation Models for Unified Data Discovery and Exploration](https://doi.org/10.14778/3659437.3659461) | `not_admitted_evidence` |
| awesome-data-agents | [DATALORE: Can a Large Language Model Find All Lost Scrolls in a Data Repository?](https://doi.org/10.1109/icde60146.2024.00388) | `not_admitted_evidence` |
| awesome-data-agents | [ReAcTable: Enhancing ReAct for Table Question Answering](https://doi.org/10.14778/3659437.3659452) | `not_admitted_evidence` |
| awesome-data-agents | [AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models](https://doi.org/10.14778/3685800.3685816) | `include_component` |
| awesome-data-agents | [ST-Raptor: LLM-Powered Semi-Structured Table Question Answering](https://doi.org/10.1145/3769829) | `not_admitted_evidence` |
| awesome-data-agents | [OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment](https://doi.org/10.1145/3725331) | `include_component` |
| awesome-data-agents | [DeepEye-SQL: A Software-Engineering-Inspired Text-to-SQL Framework](https://doi.org/10.1145/3802035) | `not_admitted_evidence` |
| awesome-data-agents | [MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization](https://doi.org/10.1145/3786670) | `include_component` |
| awesome-data-agents | [QUEST: Query Optimization in Unstructured Document Analysis](https://doi.org/10.14778/3749646.3749713) | `not_admitted_evidence` |
| awesome-data-agents | [Doctopus: Budget-aware Structural Table Extraction from Unstructured Documents](https://doi.org/10.14778/3749646.3749647) | `not_admitted_evidence` |
| awesome-data-agents | [DeepEye: A Steerable Self-driving Data Agent System](https://doi.org/10.1145/3788853.3801612) | `include_component` |
| awesome-data-agents | [AOP: Automated and Interactive LLM Pipeline Orchestration for Answering Complex Queries](https://www.vldb.org/cidrdb/2025/aop-automated-and-interactive-llm-pipeline-orchestration-for-answering-complex-queries.html) | `not_admitted_mas` |
| awesome-data-agents | [SiriusBI: A Comprehensive LLM-powered Solution for Data Analytics in Business Intelligence](https://doi.org/10.14778/3750601.3750610) | `not_admitted_evidence` |
| awesome-data-agents | [Natural Language to SQL: State of the Art and Open Problems](https://doi.org/10.14778/3750601.3750696) | `excluded_overview` |
| awesome-data-agents | [Data+AI: LLM4Data and Data4LLM](https://doi.org/10.1145/3722212.3725641) | `excluded_overview` |
| awesome-data-agents | [LLM for Data Management](https://doi.org/10.14778/3685800.3685838) | `excluded_overview` |
| awesome-multi-agent-papers | [DataLab: A Unified Platform for LLM-Powered Business Intelligence](https://doi.org/10.1109/icde65448.2025.00326) | `include_component` |
| awesome-multi-agent-papers | [AllHands :Ask Me Anything on Large-scale Verbatim Feedback via Large Language Models](https://doi.org/10.1109/icde65448.2025.00011) | `not_admitted_mas` |

## Additional DB-related leads outside the existing library

| Lead | Treatment |
|---|---|
| [Can Foundation Models Wrangle Your Data?](https://arxiv.org/abs/2205.09911) — repository annotation: - *VLDB 2022* | `excluded_year` |
| [Prompt4Vis: Prompting Large Language Models with Example Mining for Tabular Data Visualization](https://link.springer.com/article/10.1007/s00778-025-00912-0) — repository annotation: - *VLDBJ 2025* | `excluded_journal` |
| [SERAG: Self-Evolving RAG System for Query Optimization](https://viterbi-web.usc.edu/~sabek/pdf/25_workshop_serag.pdf) — repository annotation: - *SIGMOD Workshop 2025* | `excluded_workshop` |
| [Panda: Performance Debugging for Databases using LLM Agents](https://www.vldb.org/cidrdb/papers/2024/p6-singh.pdf) — repository annotation: - *CIDR 2024* | `not_admitted_mas` |
| [CleanAgent: Automating Data Standardization with LLM-based Agents](https://www.vldb.org/2025/Workshops/VLDB-Workshops-2025/DATAI/DATAI25_8.pdf) — repository annotation: - *VLDB Workshop 2025* | `excluded_workshop` |
| [Demystifying Artificial Intelligence for Data Preparation](https://dl.acm.org/doi/pdf/10.1145/3555041.3589406) — repository annotation: - *SIGMOD Tutorial 2023* | `excluded_year` |

## Limits and integrity

- Unmatched repository entries retain their original link, annotation, line number and decision in the JSON audit. Lack of a verified target-venue match is not proof that no DB publication exists.
- Automatic screening is used to withhold unsupported records, not to manufacture positive evidence. Included entries have section-level evidence. Many withheld records have only metadata or abstract-level screening.
- Source repository titles and annotations are treated as untrusted bibliographic leads. Official publication metadata and primary text determine admission.
- AI-assisted screening was used. No paper is marked as read by the user, and experiments were not independently reproduced.
