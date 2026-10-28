# Strict DB for Multi-Agent Systems Reading List

Updated 2026-10-27. **15 admitted publication records.** This supersedes the historical broad agent labels and the earlier 28-record seed-reference collection as an inclusion list.

Admission requires a verified 2024–2026 publication in ICDE, SIGMOD/PACMMOD, PVLDB, or the separately identified CIDR extension; explicit collaborating LLM agents; and an identifiable data-system mechanism or dedicated vision for improving that collaboration. Workshops, journals, single-agent systems, unverified cases, and merely analogous data-processing optimizers do not enter this list.

An application paper may qualify for a specifically documented MAS support component; the application itself does not qualify automatically. Research evaluation, demo descriptions and visions are distinguished in the evidence notes. A demo design is not a general performance claim. Publication year and conference cycle remain separate; NOMA was published in 2026 in the VLDB 2027 cycle.

[Planning and Execution review](planning-execution-review.md) · [Planning topics](planning-literature-review.md) · [Uniform filter audit](strict-filter-audit.md) · [Machine-readable decisions](../data/strict_mas_review.json)

| Paper | Venue / publication year | Evidence | One primary layer / topic |
|---|---|---|---|
| [AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models](https://doi.org/10.14778/3685800.3685816) | VLDB 2024 | Documented MAS support component within an application | Execution / Agent Scheduling |
| [D-Bot: Database Diagnosis System using Large Language Models](https://doi.org/10.14778/3675034.3675043) | VLDB 2024 | Documented MAS support component within an application | Execution / Communication Optimization |
| [Demonstration of DB-GPT: Next Generation Data Interaction System Empowered by Large Language Models](https://doi.org/10.14778/3685800.3685876) | VLDB 2024 | Documented MAS support component within an application | Execution / Workflow Management |
| [DataLab: A Unified Platform for LLM-Powered Business Intelligence](https://doi.org/10.1109/icde65448.2025.00326) | ICDE 2025 | Documented MAS support component within an application | Execution / Communication Optimization |
| [OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment](https://doi.org/10.1145/3725331) | SIGMOD 2025 | Documented MAS support component within an application | Execution / Execution Validation |
| [A Demonstration of QueryArtisan:  Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code](https://doi.org/10.14778/3750601.3750647) | VLDB 2025 | Documented MAS support component within an application | Planning / Task and Dependency Extraction |
| [SQL-Factory: A Multi-Agent Framework for High-Quality and Large-Scale SQL Generation](https://doi.org/10.14778/3778092.3778093) | VLDB 2025 (conference cycle 2026) | Documented MAS support component within an application | Execution / Agent Scheduling |
| [SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning](https://doi.org/10.14778/3750601.3750611) | VLDB 2025 | Implemented MAS system | Action / Compensation and Recovery |
| [Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First](https://www.vldb.org/cidrdb/2026/supporting-our-ai-overlords-redesigning-data-systems-to-be-agent-first.html) | CIDR 2026 | Dedicated MAS vision | Planning / Task Decomposition and Merge |
| [HEXGEN-FLOW: Optimizing LLM Inference Request Scheduling for Agentic Text-to-SQL](https://doi.org/10.1109/icde65706.2026.00134) | ICDE 2026 | Implemented MAS system | Inference Infrastructure / Inference Scheduling |
| [DeepEye: A Steerable Self-driving Data Agent System](https://doi.org/10.1145/3788853.3801612) | SIGMOD 2026 | Documented MAS support component within an application | Execution / Workflow Optimization |
| [Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective](https://doi.org/10.1145/3802046) | SIGMOD 2026 | Implemented MAS system | Execution / Workflow Optimization |
| [MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization](https://doi.org/10.1145/3786670) | SIGMOD 2026 | Documented MAS support component within an application | Execution / Execution Validation |
| [Rethinking Query Optimization for Multi-Agent Systems](https://doi.org/10.14778/3845598.3845602) | VLDB 2026 (conference cycle 2027) | Dedicated MAS vision | Execution / Workflow Optimization |
| [SpatialSQL: A Multi-Agent System for Interactive and Observable Spatial Text-to-SQL](https://doi.org/10.14778/3827998.3828055) | VLDB 2026 | Documented MAS support component within an application | Execution / Execution Analysis |

## AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models

User, Planner, Engineer, Executor and Critic exchange outputs and feedback under a common scheduler. Use workflow state to choose the next agent and control retries and termination.

**Boundary:** Only its scheduling mechanism is retained. Its tabular-QA accuracy is application-specific; it is not a general resource scheduler.

**Inspected:** §4.3, Algorithms 1–3; §5.4 and Table 5, pp3926–3930. [Primary source](https://www.vldb.org/pvldb/vol17/p3920-zhu.pdf).

**Abstract**

With the growing significance of data analysis, several studies aim to provide precise answers to users' natural language questions from tables, a task referred to as tabular question answering (TQA). The state-of-the-art TQA approaches are limited to handling only single-table questions. However, real-world TQA problems are inherently complex and frequently involve multiple tables, which poses challenges in directly extending single-table TQA designs to handle multiple tables, primarily due to the limited extensibility of the majority of single-table TQA methods. This paper proposes AutoTQA, a novel Auto nomous T abular Q uestion A nswering framework that employs multi-agent large language models (LLMs) across multiple tables from various systems (e.g., TiDB, BigQuery). AutoTQA comprises five agents: the User , responsible for receiving the user's natural language inquiry; the Planner , tasked with creating an execution plan for the user's inquiry; the Engineer , responsible for executing the plan step-by-step; the Executor , provides various execution environments (e.g., text-to-SQL) to fulfill specific tasks assigned by the Engineer ; and the Critic , responsible for judging whether to complete the user's natural language inquiry and identifying gaps between the current results and initial tasks. To facilitate the interaction between different agents, we have also devised agent scheduling algorithms. Furthermore, we have developed LinguFlow, an open-source, low-code visual programming tool, to quickly build and debug LLM-based applications, and to accelerate the creation of various external tools and execution environments. We also implemented a series of data connectors, which allows AutoTQA to access various tables from multiple systems. Extensive experiments show that AutoTQA delivers outstanding performance on four representative datasets.

[Abstract source](https://api.openalex.org/works/W4404181300) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## D-Bot: Database Diagnosis System using Large Language Models

Several selected LLM experts analyze the same anomaly, exchange summarized procedures/results and revise their findings through cross-review. Summarize agents' execution records and exchange concise evidence for cross-review.

**Boundary:** Retain the coordination and message-preparation mechanism. Database diagnosis itself is MAS for DB, and generic MAS-wide gains are not established.

**Inspected:** §7, pp2521–2522. [Primary source](https://www.vldb.org/pvldb/vol17/p2514-li.pdf).

**Abstract**

Database administrators (DBAs) play an important role in managing database systems. However, it is hard and tedious for DBAs to manage vast database instances and give timely response (waiting for hours is intolerable in many online cases). In addition, existing empirical methods only support limited diagnosis scenarios, which are also labor-intensive to update the diagnosis rules for database version updates. Recently large language models (LLMs) have shown great potential in various fields. Thus, we propose D-Bot , an LLM-based database diagnosis system that can automatically acquire knowledge from diagnosis documents, and generate reasonable and well-founded diagnosis report (i.e., identifying the root causes and solutions) within acceptable time (e.g., under 10 minutes compared to hours by a DBA). The techniques in D-Bot include ( i ) offline knowledge extraction from documents, ( ii ) automatic prompt generation (e.g., knowledge matching, tool retrieval), ( iii ) root cause analysis using tree search algorithm, and ( iv ) collaborative mechanism for complex anomalies with multiple root causes. We verify D-Bot on real benchmarks (including 539 anomalies of six typical applications), and the results show D-Bot can effectively identify root causes of unseen anomalies and significantly outperforms traditional methods and vanilla models like GPT-4.

[Abstract source](https://api.openalex.org/works/W4401352024) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## Demonstration of DB-GPT: Next Generation Data Interaction System Empowered by Large Language Models

The demonstration has a planner, three analysis agents and an aggregation agent; AWEL explicitly expresses multi-agent execution plans. Represent and orchestrate multi-agent execution using a declarative workflow DAG.

**Boundary:** Retain the AWEL and multi-agent orchestration design. The demo does not establish a cost-based MAS optimizer or performance guarantees.

**Inspected:** §§2.3–2.4 and §3, pp4367–4368. [Primary source](https://www.vldb.org/pvldb/vol17/p4365-chen.pdf).

**Abstract**

The recent breakthroughs in large language models (LLMs) are positioned to transition many areas of software. In this paper, we present DB-GPT, a revolutionary and product-ready Python library that integrates LLMs into traditional data interaction tasks to enhance user experience and accessibility. DB-GPT is designed to understand data interaction tasks described by natural language and provide context-aware responses powered by LLMs, making it an indispensable tool for users ranging from novice to expert. Its system design supports deployment across local, distributed, and cloud environments. Beyond handling basic data interaction tasks like Text-to-SQL with LLMs, it can handle complex tasks like generative data analysis through a Multi-Agents framework and the Agentic Workflow Expression Language (AWEL). The Service-oriented Multi-model Management Framework (SMMF) ensures data privacy and security, enabling users to employ DB-GPT with private LLMs. Additionally, DB-GPT offers a series of product-ready features designed to enable users to integrate DB-GPT within their product environments easily. The code of DB-GPT is available at Github.

[Abstract source](https://api.openalex.org/works/W4404181113) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## DataLab: A Unified Platform for LLM-Powered Business Intelligence

DataLab has a proxy and specialized collaborating BI agents. Section V structures exchanged information, maintains a shared buffer, separates producers from consumers, and routes relevant data through an FSM. Section VII-D evaluates this communication module on tasks requiring several agents.

**Boundary:** Retained only for its explicitly evaluated inter-agent data-management component, not because BI is a database task. Notebook-cell dependency extraction in §VI supports context retrieval; it is not extraction of a future collaboration plan. Primary layer: Execution, not Planning.

**Inspected:** Author version arXiv:2412.02205v3, §III, §V, §VI and §VII-D/E; pp3–4,7–8,11. [Primary source](https://arxiv.org/html/2412.02205v3).

**Abstract** — author preprint version

Business intelligence (BI) transforms large volumes of data within modern organizations into actionable insights for informed decision-making. Recently, large language model (LLM)-based agents have streamlined the BI workflow by automatically performing task planning, reasoning, and actions in executable environments based on natural language (NL) queries. However, existing approaches primarily focus on individual BI tasks such as NL2SQL and NL2VIS. The fragmentation of tasks across different data roles and tools lead to inefficiencies and potential errors due to the iterative and collaborative nature of BI. In this paper, we introduce DataLab, a unified BI platform that integrates a one-stop LLM-based agent framework with an augmented computational notebook interface. DataLab supports various BI tasks for different data roles in data preparation, analysis, and visualization by seamlessly combining LLM assistance with user customization within a single environment. To achieve this unification, we design a domain knowledge incorporation module tailored for enterprise-specific BI tasks, an inter-agent communication mechanism to facilitate information sharing across the BI workflow, and a cell-based context management strategy to enhance context utilization efficiency in BI notebooks. Extensive experiments demonstrate that DataLab achieves state-of-the-art performance on various BI tasks across popular research benchmarks. Moreover, DataLab maintains high effectiveness and efficiency on real-world datasets from Tencent, achieving up to a 58.58% increase in accuracy and a 61.65% reduction in token cost on enterprise-specific BI tasks.

[Abstract source](https://arxiv.org/abs/2412.02205) · [License](http://creativecommons.org/licenses/by/4.0/)

## OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment

Extraction, Generation, Refinement and Alignment agents exchange intermediate results; §3.1 explicitly addresses error accumulation across collaborating agents. Validate each agent output against its input and upstream results before passing it to downstream agents.

**Boundary:** Retain only inter-agent consistency checking and correction. The rules and evaluation are Text-to-SQL-specific; this is not a general MAS correctness guarantee. Section references use the author preprint, whose layout differs from the published article.

**Inspected:** Author version §3.1, §§3.4–3.5 and §4.3, Table 4. [Primary source](https://arxiv.org/pdf/2502.14913).

## A Demonstration of QueryArtisan:  Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code

A Task Interpreter Agent prepares work for an Analysis Executor Agent; a Process Supervisor Agent checks the process and returns errors. Prepare subtask requirements, prerequisite queries and constraints before handing work to execution agents.

**Boundary:** Retain only the task/prerequisite preparation mechanism. Its cost-based optimization of data operators is not evidence of optimizing agent topology. The demo does not independently evaluate a general dependency extractor.

**Inspected:** §2 and §3, pp5264–5265. [Primary source](https://www.vldb.org/pvldb/vol18/p5263-tang.pdf).

**Abstract**

Querying and analyzing data in data lakes requires substantial manual intervention, including numerous data preprocessing steps, and often demands complex domain expertise. However, the advent of Large Language Models (LLMs) has introduced a promising solution to these challenges by providing a unified framework for interpreting the heterogeneous datasets within data lakes. In this paper, we demonstrate QueryArtisan, a novel LLM-powered analytical system tailored for data lakes. It enables users to issue complex queries in natural language without the need for domain-specific expertise. The system automatically executes user-submitted queries and performs data processing and analysis based on the query results. QueryArtisan extends beyond traditional ETL (Extract, Transform, Load) processes by generating just-in-time code customized for dataset-specific tasks. A suite of heterogeneous operators is developed to process data across various modalities. In addition, a cost-based query optimization mechanism is integrated to improve the efficiency of the generated code. Furthermore, QueryArtisan can dynamically instantiate multiple agents in response to user-defined analytical requirements to perform further in-depth analysis of the retrieved data.

[Abstract source](https://api.openalex.org/works/W4414243402) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## SQL-Factory: A Multi-Agent Framework for High-Quality and Large-Scale SQL Generation

Generation, Expansion and Management teams coordinate; a Management Agent consumes a Critical Agent's evaluation and changes the active team. Use a shared result pool and quality statistics to choose which agent team runs next.

**Boundary:** Retain its data-driven team scheduling and shared result-pool mechanism. SQL diversity, executability and coverage remain application-specific criteria.

**Inspected:** §3, §4.1 and §5, pp294–303. [Primary source](https://www.vldb.org/pvldb/vol19/p292-gao.pdf).

**Abstract**

High quality SQL corpus is essential for intelligent databases. For example, Text-to-SQL requires SQL queries and corresponding natural language questions as training samples. However, collecting such a query corpus remains challenging in practice due to the high cost of manual annotation, which highlights the importance of automatic SQL generation. Despite recent advances, existing generation methods still face limitations in achieving both diversity and cost-effectiveness. Besides, many methods also treat all tables equally, which overlooks schema complexity and leads to under-utilization of structurally rich tables. To address these issues, this paper proposes a multi-agent framework for high-quality and large-scale SQL generation, dubbed SQL-Factory. It decomposes the generation process into three collaborative teams: the Generation Team explores diverse query structures using a powerful language model, the Expansion Team scales promising patterns via a lightweight language model, and the Management Team adaptively schedules the workflow and evaluates the quality of synthesized queries. This modular framework ensures a balanced trade-off between diversity, scalability, and generation cost. We apply SQL-Factory to four widely used benchmarks and generate over 300,000 SQL queries with less than $200 API cost. Our generated queries achieve higher diversity compared to other methods, and extensive experiments demonstrate that the generated queries significantly improve model performance in various downstream tasks.

[Abstract source](https://api.openalex.org/works/W7139098105) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning

SagaLLM coordinates task agents with a validation agent and Saga coordinator. Persistent state, dependency records, validation and compensating operations support workflow recovery. Algorithm 1 constructs task roles and dependencies.

**Boundary:** The primary contribution is recovery and validation. Algorithm 1 is a relevant construction mechanism, not an independently evaluated general-purpose role/dependency extractor; no universal ACID guarantee for arbitrary external APIs.

**Inspected:** PVLDB 18(12), §§3–4.5; Algorithm 1 p4879. [Primary source](https://www.vldb.org/pvldb/vol18/p4874-chang.pdf).

**Abstract**

This paper introduces SagaLLM, a structured multi-agent architecture designed to address four foundational limitations of current LLM-based planning systems: unreliable self-validation, context loss, lack of transactional safeguards, and insufficient inter-agent coordination. While recent frameworks leverage LLMs for task decomposition and multi-agent communication, they often fail to ensure consistency, rollback, or constraint satisfaction across distributed workflows. SagaLLM bridges this gap by integrating the Saga transactional pattern with persistent memory, automated compensation, and independent validation agents. It leverages LLMs' generative reasoning to automate key tasks traditionally requiring hand-coded coordination logic, including state tracking, dependency analysis, log schema generation, and recovery orchestration. Although SagaLLM relaxes strict ACID guarantees, it ensures workflow-wide consistency and recovery through modular checkpointing and compensable execution. Empirical evaluations across planning domains demonstrate that standalone LLMs frequently violate interdependent constraints or fail to recover from disruptions. In contrast, SagaLLM achieves significant improvements in consistency, validation accuracy, and adaptive coordination under uncertainty—establishing a robust foundation for real-world, scalable LLM-based multi-agent systems.

[Abstract source](https://api.openalex.org/works/W4414266729) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First

The paper considers an agent in charge and field agents, and proposes pruning redundant probes and sharing work across agents and turns using their goals, phase and accuracy requirements.

**Boundary:** CIDR is a separately identified DB conference extension. The paper mixes single-agent and multi-agent motivating cases; the proposed MAS-aware optimizer is a vision. Its MAS-specific work-selection discussion is the retained contribution.

**Inspected:** CIDR 2026, §2, §3, §5.2, pp2–6. [Primary source](https://www.vldb.org/cidrdb/papers/2026/p32-liu.pdf).

**Abstract**

Large Language Model (LLM) agents, acting on their users’ behalf to manipulate and analyze data, are likely to become the dominant workload for data systems in the future. When working with data, agents employ a high-throughput process of exploration and solution formulation for the given task, one we call agentic speculation. The sheer volume and inefficiencies of agentic speculation can pose challenges for present-day data systems. We argue that data systems need to adapt to more natively support agentic workloads. We take advantage of the characteristics of agentic speculation that we identify, i.e., scale, heterogeneity, redundancy, and steerability—to outline a number of new research opportunities for a new agent-first data systems architecture, ranging from new query interfaces, to new query processing techniques, to new agentic memory stores.

[Abstract source](https://www.vldb.org/cidrdb/2026/supporting-our-ai-overlords-redesigning-data-systems-to-be-agent-first.html) · [License](https://creativecommons.org/licenses/by/4.0/)

## HEXGEN-FLOW: Optimizing LLM Inference Request Scheduling for Agentic Text-to-SQL

HEXGEN-FLOW optimizes inference requests along dependent agent workflows, and its extended evaluation explicitly includes MAC-SQL. The MAC-SQL primary source establishes a decomposer collaborating with selector/refiner agents.

**Boundary:** The supporting workload is MAS, but scheduling LLM inference requests is an Inference Infrastructure contribution. Do not count its stages as a new Planning contribution or claim every evaluated workflow node is an autonomous agent.

**Inspected:** Author version arXiv:2505.05286v3, §§3–5, especially §5.1 and MAC-SQL experiment in §5.4; MAC-SQL official abstract. [Primary source](https://arxiv.org/pdf/2505.05286v3).

## DeepEye: A Steerable Self-driving Data Agent System

Autonomous AgentNodes have private contexts and standardized input/output ports; a global planner and workflow engine coordinate them with ToolNodes. Compile agent workflows, check dependencies and schemas, and run independent branches in parallel.

**Boundary:** Retain the DBMS-inspired workflow engine, not the analytics application. The demo describes the design without a standalone scheduler benchmark.

**Inspected:** §§2.1–2.3, PDF pp2–4. [Primary source](https://arxiv.org/pdf/2603.28889).

**Abstract**

Large Language Models (LLMs) have revolutionized natural language interaction with data. The ''holy grail'' of data analytics is to build autonomous Data Agents that can self-drive complex data analysis workflows. However, current implementations are still limited to linear ''ChatBI'' systems. These systems struggle with joint analysis across heterogeneous data sources (e.g., databases, documents, and data files) and often encounter ''context explosion'' in complex and iterative data analysis workflows. To address these challenges, we present DeepEye, a production-ready data agent system that adopts a workflow-centric architecture to ensure scalability and trustworthiness. DeepEye introduces a Unified Multimodal Orchestration protocol, enabling seamless integration of structured and unstructured data sources. To mitigate hallucinations, it employs Hierarchical Reasoning with context isolation, decomposing complex intents into autonomous AgentNodes and deterministic ToolNodes. Furthermore, DeepEye incorporates a database-inspired Workflow Engine (comprising a Compiler, Validator, Optimizer, and Executor) that guarantees structural correctness and accelerates execution via runtime topological optimization. In this demonstration, we showcase DeepEye's ability to orchestrate complex workflows to generate diverse multimodal outputs -- including Data Videos, Dashboards, and Analytical Reports -- highlighting its advantages in transparent execution, automated optimization, and human-in-the-loop reliability.

[Abstract source](https://api.openalex.org/works/W7147241239) · [License](https://creativecommons.org/licenses/by/)

## Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective

Helium evaluates collaborating expert/summarizer, multi-agent debate, and expert/critic reflection workflows. Section 4 applies dead-code pruning, identical-subgraph elimination, and deterministic cached-result substitution to their logical DAGs.

**Boundary:** The overall system remains in Execution. Section 4 is relevant to Planning, but assumes a supplied DAG and does not demonstrate general task or role extraction. Reuse requires compatible inputs and deterministic behavior; semantic similarity alone is insufficient.

**Inspected:** Author extended version arXiv:2603.16104v1, Figure 2, §§2–5 and §7.1, pp3–7. [Primary source](https://arxiv.org/pdf/2603.16104).

**Abstract**

Agentic workflows are composed of sequences of interdependent Large Language Model (LLM) calls, and they have become a dominant workload in modern AI systems. These workflows exhibit extensive redundancy from overlapping prompts and intermediate results due to speculative and parallel exploration. Existing LLM serving systems, such as vLLM, focus on optimizing individual inference calls and overlook cross-call dependencies, leading to significant inefficiencies. This paper rethinks LLM and agent serving from a data systems perspective and introduces Helium, a workflow-aware serving framework that models agentic workloads as query plans and treats LLM invocations as first-class operators. Helium integrates proactive caching and cache-aware scheduling to maximize reuse across prompts, KV states, and workflows. Through these techniques, Helium bridges classic query optimization principles with LLM serving, achieving up to 1.56× speedup over state-of-the-art agent serving systems on various workloads. Our results demonstrate that end-to-end optimization across workflows is essential for scalable and efficient LLM-based agents.

[Abstract source](https://api.openalex.org/works/W7161545122) · [License](https://creativecommons.org/licenses/by/)

## MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization

A Coordinator Agent orchestrates Database/Query, Visualization Implementation and Validation/Evaluation agents through feedback. Check prerequisites and execution constraints, control recovery, and bound agent interaction loops.

**Boundary:** Retain the rule-governed collaboration mechanism and its ablation. Visualization is the application, not a fourth survey dimension. Bounded termination is not a guarantee that every generated answer is correct.

**Inspected:** §§4.2–4.3 and §6.3, Tables 3–4. [Primary source](https://arxiv.org/pdf/2601.18320).

**Abstract**

Real-world visualization tasks involve complex, multi-modal requirements that extend beyond simple text-to-chart generation, requiring reference images, code examples, and iterative refinement. Current systems exhibit fundamental limitations: single-modality input, one-shot generation, and rigid workflows. While LLM-based approaches show potential for these complex requirements, they introduce reliability challenges including catastrophic failures and infinite loop susceptibility. To address this gap, we propose MultiVis-Agent, a logic rule-enhanced multi-agent framework for reliable multi-modal and multi-scenario visualization generation. Our approach introduces a four-layer logic rule framework that provides mathematical guarantees for system reliability while maintaining flexibility. Unlike traditional rule-based systems, our logic rules are mathematical constraints that guide LLM reasoning rather than replacing it. We formalize the MultiVis task spanning four scenarios from basic generation to iterative refinement, and develop MultiVis-Bench, a benchmark with over 1,000 cases for multi-modal visualization evaluation. Extensive experiments demonstrate that our approach achieves 75.63% visualization score on challenging tasks, significantly outperforming baselines (57.54-62.79%), with task completion rates of 99.58% and code execution success rates of 94.56% (vs. 74.48% and 65.10% without logic rules), successfully addressing both complexity and reliability challenges in automated visualization generation.

[Abstract source](https://api.openalex.org/works/W7151398635) · [License](https://creativecommons.org/licenses/by/)

## Rethinking Query Optimization for Multi-Agent Systems

NOMA explicitly proposes database-style optimization of multi-agent topology, model choices, and execution engines, with cost, latency and quality objectives.

**Boundary:** A dedicated MAS vision with motivating experiments, not a completed integrated optimizer. Published in 2026 but belongs to the VLDB 2027 cycle. The existing agent registry is not evidence of automatic role extraction.

**Inspected:** PVLDB 20(1), §§3–5, pp48–51. [Primary source](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf).

**Abstract**

The proliferation of large language models (LLMs) has accelerated the adoption of agent-based data pipelines. Yet current approaches remain ad hoc, relying on fixed structures, predefined LLMs, and single execution engines, without systematic optimization across heterogeneous data sources and engines. This paper presents NOMA, a query optimization framework for multi-agent data pipelines. We argue that optimizing agentic pipelines is a fundamentally different query optimization problem, with central challenges: (i) a multidimensional search and objective space, where topology, model, and engine choices must be optimized jointly across latency, cost, and accuracy; (ii) a variable pipeline topology; (iii) the co-existence of diverse data models, leaving no common operator algebra; and (iv) the significant cost of executing these pipelines. Our controlled experiment over a real-world 10-agent pipeline reveals extreme variance (153× cost, 5× latency, 25% quality) and that optimal plans are heterogeneous configurations no user would construct manually. Our analysis of real deployments confirms these inefficiencies are systematic. We present NOMA as an integrated optimization loop in which plan generation, cost estimation, runtime refinement, and semantic caching reinforce one another across executions, setting a community-wide research agenda on query optimization for multi-agent systems.

[Abstract source](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

## SpatialSQL: A Multi-Agent System for Interactive and Observable Spatial Text-to-SQL

Planner, Context Retrieval, Knowledge Retrieval, SQL Generator and SQL Validator exchange context, drafts and feedback. Record linked interaction and execution traces for monitoring, replay and failure inspection.

**Boundary:** Retain structured trace collection and inspection. The demo does not prove general causal error attribution or an evaluated automatic root-cause algorithm.

**Inspected:** §§2.2–2.3, pp4523–4524. [Primary source](https://www.vldb.org/pvldb/vol19/p4522-tong.pdf).

**Abstract**

With significant advancements in Large Language Models (LLMs) in recent years, text-to-SQL has emerged as a prominent paradigm for querying databases, aiming to transform natural language into executable database queries. Despite the outstanding performance of previous works on relational databases, few studies have addressed spatial queries, where both data and queries are related to spatial information. Compared to text-to-SQL tasks on relational databases, generating spatial SQL from natural language remains challenging due to the complexity of geometric operations and spatial reasoning. To tackle these issues, this paper presents SpatialSQL, a multi-agent system for interactive and observable spatial text-to-SQL generation. At the core of SpatialSQL, several specially designed agents are coordinated to interpret user intent, construct spatial SQL queries, and iteratively refine them based on execution feedback. Additionally, SpatialSQL integrates a platform for monitoring and managing the entire interaction lifecycle, including chat histories, SQL execution traces, and user feedback, through an administrative console. To support interactive exploration, SpatialSQL surfaces intermediate reasoning artifacts and execution results, enabling users to inspect and guide the query generation process. We demonstrate SpatialSQL through a unified user interface and management console that together support transparent query construction and system observability.

[Abstract source](https://api.openalex.org/works/W7212771062) · [License](https://creativecommons.org/licenses/by-nc-nd/4.0/)

AI-assisted source screening; selected sections were inspected. No record is marked as read by the user. Admission is a bounded evidence decision, not a claim of exhaustive coverage.
