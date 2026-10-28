# Database References from the Three Seed Papers

> **Archive:** this is a discovery inventory, not the current inclusion list. Use the [strict DB for MAS list](strict-db-mas-papers.md) and [uniform filter audit](strict-filter-audit.md).

Updated 2026-10-27. Start with the [Planning review](planning-literature-review.md). The [audit snapshot](../data/citation_review.json) contains citation numbers, abstracts or clearly labeled paraphrases, scope decisions, and version notes.

The current conference window is publication years **2024–2026**. This audit found **26 cited records in that window**, plus **NOMA and SagaLLM as seed anchors**: 28 records in total. Of these, 15 matched the previous local library and 13 were added. CIDR and VLDB workshops are explicit extensions to the original three-venue search.

The entire inventory has **58 distinct cited works plus two seed anchors**. The older and journal annexes below do not count toward the recent conference collection. This is a bounded reference audit, not an exhaustive search of database venues.

**Seeds:** ACDS, the supplied architecture manuscript (149 references); [NOMA](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf) (35 references); [SagaLLM](https://www.vldb.org/pvldb/vol18/p4874-chang.pdf) (52 references). Source references such as `ACDS [113]` use those exact versions.

## Interpretation

- Confirmed MAS systems and MAS visions have separate labels. A vision is not an evaluated implementation.
- A transferable database method is not automatically a DB-for-MAS paper.
- Primary layers are our organizational assignments. No paper receives multiple primary entries.
- Older records labeled as seed-only metadata still need independent verification. No work is marked as read by the user.

## Recent ICDE, SIGMOD/PACMMOD, and VLDB/PVLDB

| Paper | Venue · Publication year | Cited by | Scope | Primary layer |
|---|---|---|---|---|
| [Abacus: A Cost-Based Optimizer for Semantic Operator Systems](https://doi.org/10.14778/3796195.3796215) | VLDB · 2026 | ACDS [96] | Transferable method; not MAS evidence | Execution |
| [Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective](https://doi.org/10.1145/3802046) | SIGMOD · 2026 | ACDS [113]; NOMA [32] | DB for MAS: system / seed proposal | Execution |
| [Rethinking Query Optimization for Multi-Agent Systems](https://doi.org/10.14778/3845598.3845602) | VLDB · 2026 | User-supplied seed | DB for MAS: system / seed proposal | Execution |
| [SEMA: A High-performance System for LLM-based Semantic Query Processing](https://doi.org/10.14778/3836663.3836685) | VLDB · 2026 | ACDS [87] | Transferable method; not MAS evidence | Execution |
| [Task Cascades for Efficient Unstructured Data Processing](https://doi.org/10.1145/3786702) | SIGMOD · 2026 | ACDS [105] | Transferable method; not MAS evidence | Execution |
| [Beyond Quacking: Deep Integration of Language Models and RAG into DuckDB](https://doi.org/10.14778/3750601.3750685) | VLDB · 2025 | NOMA [11] | Background only | — |
| [Conformal Prediction for Verifiable Learned Query Optimization](https://www.vldb.org/pvldb/vol18/p2653-liu.pdf) | VLDB · 2025 | NOMA [21] | Transferable method; not MAS evidence | Execution |
| [ContextCache: Context-Aware Semantic Cache for Multi-Turn Queries in Large Language Models](https://doi.org/10.14778/3750601.3750679) | VLDB · 2025 | NOMA [33] | Agent support; MAS not established | Memory |
| [DocETL: Agentic Query Rewriting and Evaluation for Complex Document Processing](https://doi.org/10.14778/3746405.3746426) | VLDB · 2025 | ACDS [104]; NOMA [27] | Transferable method; not MAS evidence | Planning |
| [GenJoin: Conditional Generative Plan-to-Plan Query Optimizer that Learns from Subplan Hints](https://doi.org/10.1145/3749165) | SIGMOD · 2025 | NOMA [29] | Transferable method; not MAS evidence | Execution |
| [How Good are Learned Cost Models, Really? Insights from Query Optimization Tasks](https://doi.org/10.1145/3725309) | SIGMOD · 2025 | NOMA [15] | Transferable method; not MAS evidence | Execution |
| [LIMAO: A Framework for Lifelong Modular Learned Query Optimization](https://www.vldb.org/pvldb/vol18/p4546-zhang.pdf) | VLDB · 2025 | NOMA [34] | Transferable method; not MAS evidence | Execution |
| [Learned Cost Models for Query Optimization: From Batch to Streaming Systems](https://www.vldb.org/pvldb/vol18/p5482-li.pdf) | VLDB · 2025 | NOMA [14] | Transferable method; not MAS evidence | Execution |
| [Learned Offline Query Planning via Bayesian Optimization](https://doi.org/10.1145/3725316) | SIGMOD · 2025 | NOMA [31] | Transferable method; not MAS evidence | Execution |
| [Logical and Physical Optimizations for SQL Query Execution over Large Language Models](https://doi.org/10.1145/3725411) | SIGMOD · 2025 | ACDS [101] | Transferable method; not MAS evidence | Planning |
| [SQLStorm: Taking Database Benchmarking into the LLM Era](https://doi.org/10.14778/3749646.3749683) | VLDB · 2025 | NOMA [26] | Background only | — |
| [SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning](https://doi.org/10.14778/3750601.3750611) | VLDB · 2025 | User-supplied seed | DB for MAS: system / seed proposal | Action |
| [Semantic Integrity Constraints: Declarative Guardrails for AI-Augmented Data Processing Systems](https://doi.org/10.14778/3749646.3749677) | VLDB · 2025 | ACDS [53] | Transferable method; not MAS evidence | Planning |
| [Semantic Operators and Their Optimization: Towards AI-Based Data Analytics with Accuracy Guarantees](https://doi.org/10.14778/3749646.3749685) | VLDB · 2025 | ACDS [84]; NOMA [24] | Transferable method; not MAS evidence | Execution |
| [Unify: An Unstructured Data Analytics System](https://doi.org/10.1109/icde65448.2025.00374) | ICDE · 2025 | ACDS [114] | Transferable method; not MAS evidence | Planning |
| [ThalamusDB: Approximate Query Processing on Multi-Modal Data](https://doi.org/10.1145/3654989) | SIGMOD · 2024 | NOMA [16] | Transferable method; not MAS evidence | Execution |

## Recent CIDR extension

| Paper | Venue · Publication year | Cited by | Scope | Primary layer |
|---|---|---|---|---|
| [BridgeScope: A Universal Toolkit for Bridging Large Language Models and Databases](https://www.vldb.org/cidrdb/2026/bridgescope-a-universal-toolkit-for-bridging-large-language-models-and-databases.html) | CIDR · 2026 | ACDS [121] | Agent support; MAS not established | Data Interface |
| [Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First](https://www.vldb.org/cidrdb/2026/supporting-our-ai-overlords-redesigning-data-systems-to-be-agent-first.html) | CIDR · 2026 | ACDS [59] | DB for MAS: vision | Planning |
| [AOP: Automated and Interactive LLM Pipeline Orchestration for Answering Complex Queries](https://www.vldb.org/cidrdb/2025/aop-automated-and-interactive-llm-pipeline-orchestration-for-answering-complex-queries.html) | CIDR · 2025 | ACDS [115] | Transferable method; not MAS evidence | Planning |
| [Palimpzest: Optimizing AI-Powered Analytics with Declarative Query Processing](https://www.vldb.org/cidrdb/2025/palimpzest-optimizing-ai-powered-analytics-with-declarative-query-processing.html) | CIDR · 2025 | ACDS [58]; NOMA [20] | Transferable method; not MAS evidence | Execution |
| [Text2SQL is Not Enough: Unifying AI and Databases with TAG](https://www.vldb.org/cidrdb/2025/text2sql-is-not-enough-unifying-ai-and-databases-with-tag.html) | CIDR · 2025 | ACDS [5] | Background only | — |

## Recent VLDB workshops — not the main conference

| Paper | Venue · Publication year | Cited by | Scope | Primary layer |
|---|---|---|---|---|
| [A Learned Cost Model-based Cross-engine Optimizer for SQL Workloads](https://www.vldb.org/2025/Workshops/VLDB-Workshops-2025/CDMS/CDMS25_06.pdf) | VLDB Workshop · 2025 | NOMA [28] | Transferable method; not MAS evidence | Execution |
| [Towards the Next Generation of Agent Systems: From RAG to Agentic AI](https://www.vldb.org/2025/Workshops/VLDB-Workshops-2025/LLM%2BGraph/LLMGraph-8.pdf) | VLDB Workshop · 2025 | NOMA [35] | DB for MAS: vision | Planning |

## Historical conference background — outside 2024–2026

| Paper | Venue · Publication year | Cited by | Scope | Primary layer |
|---|---|---|---|---|
| SANTOS: Relationship-based Semantic Table Union Search | SIGMOD · 2023 | ACDS [45] | Bibliographic background; seed-only metadata | — |
| [Semantics-aware Dataset Discovery from Data Lakes with Contextualized Column-based Representation Learning](https://doi.org/10.14778/3587136.3587146) | VLDB · 2023 | ACDS [20] | Bibliographic background | — |
| [Bao: Making Learned Query Optimization Practical](https://doi.org/10.1145/3448016.3452838) | SIGMOD · 2021 | ACDS [64] | Bibliographic background | — |
| Milvus: A Purpose-Built Vector Data Management System | SIGMOD · 2021 | ACDS [117] | Bibliographic background; seed-only metadata | — |
| Delta Lake: High-Performance ACID Table Storage over Cloud Object Stores | VLDB · 2020 | ACDS [3] | Bibliographic background; seed-only metadata | — |
| Data Lake Management: Challenges and Opportunities | VLDB · 2019 | ACDS [74] | Bibliographic background; seed-only metadata | — |
| DuckDB: An Embeddable Analytical Database | SIGMOD · 2019 | ACDS [92] | Bibliographic background; seed-only metadata | — |
| RHEEM: Enabling Cross-Platform Data Processing - May The Big Data Be With You! | VLDB · 2018 | NOMA [1] | Bibliographic background; seed-only metadata | — |
| [Data Management in Machine Learning: Challenges, Techniques, and Systems](https://doi.org/10.1145/3035918.3054775) | SIGMOD · 2017 | NOMA [18] | Bibliographic background | — |
| [Mix 'n' Match Multi-Engine Analytics](https://doi.org/10.1109/bigdata.2016.7840605) | IEEE BigData · 2016 | NOMA [10] | Bibliographic background | — |
| Druid: A Real-time Analytical Data Store | SIGMOD · 2014 | ACDS [128] | Bibliographic background; seed-only metadata | — |
| F1: A Distributed SQL Database That Scales | VLDB · 2013 | ACDS [108] | Bibliographic background; seed-only metadata | — |
| The W3C PROV Family of Specifications for Modelling Provenance Metadata | EDBT · 2013 | ACDS [69] | Bibliographic background; seed-only metadata | — |
| [SharedDB: Killing One Thousand Queries with One Stone](https://www.vldb.org/pvldb/vol5/p526_georgiosgiannikis_vldb2012.pdf) | VLDB · 2012 | ACDS [30] | Historical foundation | Planning |
| gStore: Answering SPARQL Queries via Subgraph Matching | VLDB · 2011 | ACDS [149] | Bibliographic background; seed-only metadata | — |
| RDF-3X: A RISC-style Engine for RDF | VLDB · 2008 | ACDS [75] | Bibliographic background; seed-only metadata | — |
| Principles of Dataspace Systems | PODS · 2006 | ACDS [37] | Bibliographic background; seed-only metadata | — |
| [Robust Query Processing through Progressive Optimization](https://doi.org/10.1145/1007568.1007642) | SIGMOD · 2004 | NOMA [22] | Historical foundation | Execution |
| Why and Where: A Characterization of Data Provenance | ICDT · 2001 | ACDS [6] | Bibliographic background; seed-only metadata | — |
| [Eddies: Continuously Adaptive Query Processing](https://db.cs.berkeley.edu/papers/sigmod00-eddy.pdf) | SIGMOD · 2000 | ACDS [4] | Historical foundation | Execution |
| [NiagaraCQ: A Scalable Continuous Query System for Internet Databases](https://research.cs.wisc.edu/niagara/papers/NiagaraCQ.pdf) | SIGMOD · 2000 | ACDS [8] | Historical foundation | Planning |
| [Semantic Data Caching and Replacement](https://www.vldb.org/conf/1996/P330.PDF) | VLDB · 1996 | NOMA [8] | Bibliographic background | — |
| [Maintaining Views Incrementally](https://sigmodrecord.org/1993/06/03/maintaining-views-incrementally/) | SIGMOD · 1993 | ACDS [35] | Bibliographic background; seed-only metadata | — |
| [Sagas](https://doi.org/10.1145/38713.38742) | SIGMOD · 1987 | ACDS [27]; SagaLLM [18] | Bibliographic background | — |
| The Transaction Concept: Virtues and Limitations | VLDB · 1981 | SagaLLM [22] | Bibliographic background; seed-only metadata | — |

## Journal background — not conference papers

| Paper | Venue · Publication year | Cited by | Scope | Primary layer |
|---|---|---|---|---|
| [Assisted Design of Data Science Pipelines](https://doi.org/10.1007/s00778-024-00835-2) | VLDB Journal · 2024 | NOMA [25] | Bibliographic background | — |
| Survey of Vector Database Management Systems | VLDB Journal · 2024 | ACDS [81] | Bibliographic background; seed-only metadata | — |
| Apache Wayang: A Unified Data Analytics Framework | SIGMOD Record · 2023 | NOMA [4] | Bibliographic background; seed-only metadata | — |
| [RHEEMix in the Data Jungle: A Cost-based Optimizer for Cross-platform Systems](https://doi.org/10.1007/s00778-020-00612-x) | VLDB Journal · 2020 | NOMA [17] | Bibliographic background | — |
| Adaptive Query Processing | Foundations and Trends in Databases · 2007 | NOMA [9] | Bibliographic background; seed-only metadata | — |
| From Databases to Dataspaces: A New Abstraction for Information Management | SIGMOD Record · 2005 | ACDS [24] | Bibliographic background; seed-only metadata | — |
| ARIES: A Transaction Recovery Method Supporting Fine-Granularity Locking and Partial Rollbacks Using Write-Ahead Logging | TODS · 1992 | ACDS [71] | Bibliographic background; seed-only metadata | — |

## Corrections to the earlier local screening

- **Helium:** explicit MAS workloads were confirmed in the extended paper, including debate and reflection. The earlier abstract-only “MAS unconfirmed” label is superseded.
- **DocETL:** generation and validation agents are explicit, but their target is document-processing optimization. It remains a transferable method for our DB-for-MAS scope.
- **Abacus:** research paper, not a demo. **Semantic Integrity Constraints:** vision, not a completed MAS validation system.
- **NOMA:** publication year 2026, PVLDB volume 20 / VLDB 2027 cycle. **GenJoin:** publication year 2025, SIGMOD 2026 cycle.
- **LOTUS:** the seed/PDF title and Crossref title differ; the common DOI is used to avoid duplicate records.
- **Helium, Task Cascades, SEMA:** ACDS cites preprints; these were linked to published records.
- **The VLDB Journal** and **SIGMOD Record** are not classified as main-conference papers. The two workshop papers are explicitly marked.

## Venue and version exclusions

| Seed reference | Work | Boundary |
|---|---|---|
| ACDS [12] | UQE: A Query Engine for Unstructured Databases | NeurIPS 2024 |
| ACDS [47] | An LLM Compiler for Parallel Function Calling | ICML 2024 |
| ACDS [106] | HuggingGPT | NeurIPS 2023 |
| ACDS [141] | AFlow: Automating Agentic Workflow Generation | ICLR 2025 |
| ACDS [145] | Language Agent Tree Search | ICML 2024 |
| ACDS [60] | Reason for Future, Act for Now (RAFA) | ICML 2024 |
| ACDS [110] | LakeBench: Benchmarks for Data Discovery over Data Lakes | Preprint in seed; DB-conference publication not verified |
| ACDS [127] | DB-GPT: Empowering Database Interactions with Private Large Language Models | Preprint in seed; DB-conference publication not verified |
| ACDS [147] | A Survey of Data Agents: Emerging Paradigm or Overstated Hype? | Preprint in seed; DB-conference publication not verified |
| NOMA [19] | GenDB: The Next Generation of Query Processing — Synthesized, Not Engineered | Preprint in seed; DB-conference publication not verified |
