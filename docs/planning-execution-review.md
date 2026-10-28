# Planning and Execution: DB Conference Papers for MAS

Updated 2026-10-27. The earlier five-paper display was an incomplete admitted subset, not the size of the relevant literature. This review restores explicitly documented collaboration-support mechanisms within application papers. It does not admit a paper merely because it uses multiple agents for a database task.

**Scope:** publication years 2024–2026; ICDE, SIGMOD/PACMMOD and PVLDB, with CIDR labeled separately. Explicit collaborating LLM agents are required. Each work has one primary layer. Research papers, demos and visions are labeled separately. A documented demo mechanism is evidence of a design, not evidence of general performance gains.

**Current focused list: 13 primary works — 2 Planning and 11 Execution.** Two related demo publications are linked separately rather than counted as independent mechanisms. This is a bounded review, not an exhaustive absence claim.

**Layer boundary from ACDS §§3–4:** Planning organizes logical tasks, prerequisites and admissible sharing. Execution manages agent invocations, assignment, communication, validation and runtime scheduling. Names such as “planner” in other papers do not determine their layer.

## Planning

| Paper | Venue / year | Topic | Relevant mechanism | Evidence scope |
|---|---|---|---|---|
| [Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First](https://www.vldb.org/cidrdb/papers/2026/p32-liu.pdf) | CIDR 2026 · extension · vision | Task Decomposition and Merge | Identify redundant exploration and share compatible work across agents. | Core vision |
| [A Demonstration of QueryArtisan:  Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code](https://www.vldb.org/pvldb/vol18/p5263-tang.pdf) | PVLDB 2025 · demo | Task and Dependency Extraction | Prepare subtask requirements, prerequisite queries and constraints before handing work to execution agents. | Application component |

## Execution

| Paper | Venue / year | Topic | Relevant mechanism | Evidence scope |
|---|---|---|---|---|
| [Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective](https://arxiv.org/pdf/2603.16104) | SIGMOD 2026 · research | Workflow Optimization | Rewrite agent workflow graphs and schedule execution to reuse shared computation. | Core system |
| [Rethinking Query Optimization for Multi-Agent Systems](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf) | PVLDB 2026 · VLDB 2027 cycle · vision | Workflow Optimization | Jointly choose agent topology, models and execution engines under cost, latency and quality objectives. | Core vision |
| [AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models](https://www.vldb.org/pvldb/vol17/p3920-zhu.pdf) | PVLDB 2024 · research | Agent Scheduling | Use workflow state to choose the next agent and control retries and termination. | Application component |
| [Demonstration of DB-GPT: Next Generation Data Interaction System Empowered by Large Language Models](https://www.vldb.org/pvldb/vol17/p4365-chen.pdf) | PVLDB 2024 · demo | Workflow Management | Represent and orchestrate multi-agent execution using a declarative workflow DAG. | Application component |
| [DeepEye: A Steerable Self-driving Data Agent System](https://arxiv.org/pdf/2603.28889) | SIGMOD 2026 · demo | Workflow Optimization | Compile agent workflows, check dependencies and schemas, and run independent branches in parallel. | Application component |
| [DataLab: A Unified Platform for LLM-Powered Business Intelligence](https://arxiv.org/html/2412.02205v3) | ICDE 2025 · research | Communication Optimization | Exchange structured information through a shared buffer and route it to the relevant agents. | Application component |
| [D-Bot: Database Diagnosis System using Large Language Models](https://www.vldb.org/pvldb/vol17/p2514-li.pdf) | PVLDB 2024 · research | Communication Optimization | Summarize agents' execution records and exchange concise evidence for cross-review. | Application component |
| [SQL-Factory: A Multi-Agent Framework for High-Quality and Large-Scale SQL Generation](https://www.vldb.org/pvldb/vol19/p292-gao.pdf) | PVLDB 2025 · VLDB 2026 cycle · research | Agent Scheduling | Use a shared result pool and quality statistics to choose which agent team runs next. | Application component |
| [MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization](https://arxiv.org/pdf/2601.18320) | SIGMOD 2026 · research | Execution Validation | Check prerequisites and execution constraints, control recovery, and bound agent interaction loops. | Application component |
| [OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment](https://arxiv.org/pdf/2502.14913) | SIGMOD 2025 · research | Execution Validation | Validate each agent output against its input and upstream results before passing it to downstream agents. | Application component |
| [SpatialSQL: A Multi-Agent System for Interactive and Observable Spatial Text-to-SQL](https://www.vldb.org/pvldb/vol19/p4522-tong.pdf) | PVLDB 2026 · demo | Execution Analysis | Record linked interaction and execution traces for monitoring, replay and failure inspection. | Application component |

## Section-level evidence and limits

### Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First

**Primary layer:** Planning · **Topic:** Task Decomposition and Merge

**MAS evidence:** Supervisor and field agents; the proposal explicitly considers sharing across agents and turns.

**Relevant mechanism:** Identify redundant exploration and share compatible work across agents.

**Inspected source:** [§§2–3 and §5.2](https://www.vldb.org/cidrdb/papers/2026/p32-liu.pdf).

**Limit:** A research vision with motivating cases; no completed general MAS planner is established.

**Abstract — original text from the existing library**

Large Language Model (LLM) agents, acting on their users’ behalf to manipulate and analyze data, are likely to become the dominant workload for data systems in the future. When working with data, agents employ a high-throughput process of exploration and solution formulation for the given task, one we call agentic speculation. The sheer volume and inefficiencies of agentic speculation can pose challenges for present-day data systems. We argue that data systems need to adapt to more natively support agentic workloads. We take advantage of the characteristics of agentic speculation that we identify, i.e., scale, heterogeneity, redundancy, and steerability—to outline a number of new research opportunities for a new agent-first data systems architecture, ranging from new query interfaces, to new query processing techniques, to new agentic memory stores.

[Abstract source](https://www.vldb.org/cidrdb/2026/supporting-our-ai-overlords-redesigning-data-systems-to-be-agent-first.html). Version: CIDR official proceedings abstract.

### A Demonstration of QueryArtisan:  Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code

**Primary layer:** Planning · **Topic:** Task and Dependency Extraction

**MAS evidence:** A Task Interpreter Agent prepares work for an Analysis Executor Agent; a Process Supervisor Agent checks the process and returns errors.

**Relevant mechanism:** Prepare subtask requirements, prerequisite queries and constraints before handing work to execution agents.

**Inspected source:** [§2 and §3, pp5264–5265](https://www.vldb.org/pvldb/vol18/p5263-tang.pdf).

**Limit:** Retain only the task/prerequisite preparation mechanism. Its cost-based optimization of data operators is not evidence of optimizing agent topology. The demo does not independently evaluate a general dependency extractor.

**Abstract — original text from the existing library**

Querying and analyzing data in data lakes requires substantial manual intervention, including numerous data preprocessing steps, and often demands complex domain expertise. However, the advent of Large Language Models (LLMs) has introduced a promising solution to these challenges by providing a unified framework for interpreting the heterogeneous datasets within data lakes. In this paper, we demonstrate QueryArtisan, a novel LLM-powered analytical system tailored for data lakes. It enables users to issue complex queries in natural language without the need for domain-specific expertise. The system automatically executes user-submitted queries and performs data processing and analysis based on the query results. QueryArtisan extends beyond traditional ETL (Extract, Transform, Load) processes by generating just-in-time code customized for dataset-specific tasks. A suite of heterogeneous operators is developed to process data across various modalities. In addition, a cost-based query optimization mechanism is integrated to improve the efficiency of the generated code. Furthermore, QueryArtisan can dynamically instantiate multiple agents in response to user-defined analytical requirements to perform further in-depth analysis of the retrieved data.

[Abstract source](https://api.openalex.org/works/W4414243402). Version: OpenAlex indexed abstract.

### Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective

**Primary layer:** Execution · **Topic:** Workflow Optimization

**MAS evidence:** Evaluates multi-agent debate, expert/critic reflection and expert/summarizer collaboration.

**Relevant mechanism:** Rewrite agent workflow graphs and schedule execution to reuse shared computation.

**Inspected source:** [§4, Figure 2 and §7.1](https://arxiv.org/pdf/2603.16104).

**Limit:** Starts from a supplied DAG, with one base model and local operations; deterministic caching rules do not establish arbitrary semantic equivalence.

**Abstract — original text from the existing library**

Agentic workflows are composed of sequences of interdependent Large Language Model (LLM) calls, and they have become a dominant workload in modern AI systems. These workflows exhibit extensive redundancy from overlapping prompts and intermediate results due to speculative and parallel exploration. Existing LLM serving systems, such as vLLM, focus on optimizing individual inference calls and overlook cross-call dependencies, leading to significant inefficiencies. This paper rethinks LLM and agent serving from a data systems perspective and introduces Helium, a workflow-aware serving framework that models agentic workloads as query plans and treats LLM invocations as first-class operators. Helium integrates proactive caching and cache-aware scheduling to maximize reuse across prompts, KV states, and workflows. Through these techniques, Helium bridges classic query optimization principles with LLM serving, achieving up to 1.56× speedup over state-of-the-art agent serving systems on various workloads. Our results demonstrate that end-to-end optimization across workflows is essential for scalable and efficient LLM-based agents.

[Abstract source](https://api.openalex.org/works/W7161545122). Version: OpenAlex indexed abstract.

### Rethinking Query Optimization for Multi-Agent Systems

**Primary layer:** Execution · **Topic:** Workflow Optimization

**MAS evidence:** Uses a real 10-agent pipeline and discusses dependencies between collaborating agents.

**Relevant mechanism:** Jointly choose agent topology, models and execution engines under cost, latency and quality objectives.

**Inspected source:** [§§3–5, pp48–51](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf).

**Limit:** The integrated optimization loop is a research agenda, not a completed and comprehensively evaluated optimizer.

**Abstract — original text from the existing library**

The proliferation of large language models (LLMs) has accelerated the adoption of agent-based data pipelines. Yet current approaches remain ad hoc, relying on fixed structures, predefined LLMs, and single execution engines, without systematic optimization across heterogeneous data sources and engines. This paper presents NOMA, a query optimization framework for multi-agent data pipelines. We argue that optimizing agentic pipelines is a fundamentally different query optimization problem, with central challenges: (i) a multidimensional search and objective space, where topology, model, and engine choices must be optimized jointly across latency, cost, and accuracy; (ii) a variable pipeline topology; (iii) the co-existence of diverse data models, leaving no common operator algebra; and (iv) the significant cost of executing these pipelines. Our controlled experiment over a real-world 10-agent pipeline reveals extreme variance (153× cost, 5× latency, 25% quality) and that optimal plans are heterogeneous configurations no user would construct manually. Our analysis of real deployments confirms these inefficiencies are systematic. We present NOMA as an integrated optimization loop in which plan generation, cost estimation, runtime refinement, and semantic caching reinforce one another across executions, setting a community-wide research agenda on query optimization for multi-agent systems.

[Abstract source](https://www.vldb.org/pvldb/vol20/p46-kaoudi.pdf). Version: Published PVLDB PDF, abstract extracted from page 1.

### AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models

**Primary layer:** Execution · **Topic:** Agent Scheduling

**MAS evidence:** User, Planner, Engineer, Executor and Critic exchange outputs and feedback under a common scheduler.

**Relevant mechanism:** Use workflow state to choose the next agent and control retries and termination.

**Inspected source:** [§4.3, Algorithms 1–3; §5.4 and Table 5, pp3926–3930](https://www.vldb.org/pvldb/vol17/p3920-zhu.pdf).

**Limit:** Only its scheduling mechanism is retained. Its tabular-QA accuracy is application-specific; it is not a general resource scheduler.

**Abstract — original text from the existing library**

With the growing significance of data analysis, several studies aim to provide precise answers to users' natural language questions from tables, a task referred to as tabular question answering (TQA). The state-of-the-art TQA approaches are limited to handling only single-table questions. However, real-world TQA problems are inherently complex and frequently involve multiple tables, which poses challenges in directly extending single-table TQA designs to handle multiple tables, primarily due to the limited extensibility of the majority of single-table TQA methods. This paper proposes AutoTQA, a novel Auto nomous T abular Q uestion A nswering framework that employs multi-agent large language models (LLMs) across multiple tables from various systems (e.g., TiDB, BigQuery). AutoTQA comprises five agents: the User , responsible for receiving the user's natural language inquiry; the Planner , tasked with creating an execution plan for the user's inquiry; the Engineer , responsible for executing the plan step-by-step; the Executor , provides various execution environments (e.g., text-to-SQL) to fulfill specific tasks assigned by the Engineer ; and the Critic , responsible for judging whether to complete the user's natural language inquiry and identifying gaps between the current results and initial tasks. To facilitate the interaction between different agents, we have also devised agent scheduling algorithms. Furthermore, we have developed LinguFlow, an open-source, low-code visual programming tool, to quickly build and debug LLM-based applications, and to accelerate the creation of various external tools and execution environments. We also implemented a series of data connectors, which allows AutoTQA to access various tables from multiple systems. Extensive experiments show that AutoTQA delivers outstanding performance on four representative datasets.

[Abstract source](https://api.openalex.org/works/W4404181300). Version: OpenAlex indexed abstract.

### Demonstration of DB-GPT: Next Generation Data Interaction System Empowered by Large Language Models

**Primary layer:** Execution · **Topic:** Workflow Management

**MAS evidence:** The demonstration has a planner, three analysis agents and an aggregation agent; AWEL explicitly expresses multi-agent execution plans.

**Relevant mechanism:** Represent and orchestrate multi-agent execution using a declarative workflow DAG.

**Inspected source:** [§§2.3–2.4 and §3, pp4367–4368](https://www.vldb.org/pvldb/vol17/p4365-chen.pdf).

**Limit:** Retain the AWEL and multi-agent orchestration design. The demo does not establish a cost-based MAS optimizer or performance guarantees.

**Abstract — original text from the existing library**

The recent breakthroughs in large language models (LLMs) are positioned to transition many areas of software. In this paper, we present DB-GPT, a revolutionary and product-ready Python library that integrates LLMs into traditional data interaction tasks to enhance user experience and accessibility. DB-GPT is designed to understand data interaction tasks described by natural language and provide context-aware responses powered by LLMs, making it an indispensable tool for users ranging from novice to expert. Its system design supports deployment across local, distributed, and cloud environments. Beyond handling basic data interaction tasks like Text-to-SQL with LLMs, it can handle complex tasks like generative data analysis through a Multi-Agents framework and the Agentic Workflow Expression Language (AWEL). The Service-oriented Multi-model Management Framework (SMMF) ensures data privacy and security, enabling users to employ DB-GPT with private LLMs. Additionally, DB-GPT offers a series of product-ready features designed to enable users to integrate DB-GPT within their product environments easily. The code of DB-GPT is available at Github.

[Abstract source](https://api.openalex.org/works/W4404181113). Version: OpenAlex indexed abstract.

### DeepEye: A Steerable Self-driving Data Agent System

**Primary layer:** Execution · **Topic:** Workflow Optimization

**MAS evidence:** Autonomous AgentNodes have private contexts and standardized input/output ports; a global planner and workflow engine coordinate them with ToolNodes.

**Relevant mechanism:** Compile agent workflows, check dependencies and schemas, and run independent branches in parallel.

**Inspected source:** [§§2.1–2.3, PDF pp2–4](https://arxiv.org/pdf/2603.28889).

**Limit:** Retain the DBMS-inspired workflow engine, not the analytics application. The demo describes the design without a standalone scheduler benchmark.

**Abstract — original text from the existing library**

Large Language Models (LLMs) have revolutionized natural language interaction with data. The ''holy grail'' of data analytics is to build autonomous Data Agents that can self-drive complex data analysis workflows. However, current implementations are still limited to linear ''ChatBI'' systems. These systems struggle with joint analysis across heterogeneous data sources (e.g., databases, documents, and data files) and often encounter ''context explosion'' in complex and iterative data analysis workflows. To address these challenges, we present DeepEye, a production-ready data agent system that adopts a workflow-centric architecture to ensure scalability and trustworthiness. DeepEye introduces a Unified Multimodal Orchestration protocol, enabling seamless integration of structured and unstructured data sources. To mitigate hallucinations, it employs Hierarchical Reasoning with context isolation, decomposing complex intents into autonomous AgentNodes and deterministic ToolNodes. Furthermore, DeepEye incorporates a database-inspired Workflow Engine (comprising a Compiler, Validator, Optimizer, and Executor) that guarantees structural correctness and accelerates execution via runtime topological optimization. In this demonstration, we showcase DeepEye's ability to orchestrate complex workflows to generate diverse multimodal outputs -- including Data Videos, Dashboards, and Analytical Reports -- highlighting its advantages in transparent execution, automated optimization, and human-in-the-loop reliability.

[Abstract source](https://api.openalex.org/works/W7147241239). Version: OpenAlex indexed abstract.

### DataLab: A Unified Platform for LLM-Powered Business Intelligence

**Primary layer:** Execution · **Topic:** Communication Optimization

**MAS evidence:** A proxy and specialized agents communicate while completing a common BI task.

**Relevant mechanism:** Exchange structured information through a shared buffer and route it to the relevant agents.

**Inspected source:** [§V and §VII-D; §VI for the context-DAG boundary](https://arxiv.org/html/2412.02205v3).

**Limit:** Only the evaluated communication component is retained. Its notebook-cell DAG retrieves context rather than extracting a future collaboration plan.

**Abstract — original text from the existing library**

Business intelligence (BI) transforms large volumes of data within modern organizations into actionable insights for informed decision-making. Recently, large language model (LLM)-based agents have streamlined the BI workflow by automatically performing task planning, reasoning, and actions in executable environments based on natural language (NL) queries. However, existing approaches primarily focus on individual BI tasks such as NL2SQL and NL2VIS. The fragmentation of tasks across different data roles and tools lead to inefficiencies and potential errors due to the iterative and collaborative nature of BI. In this paper, we introduce DataLab, a unified BI platform that integrates a one-stop LLM-based agent framework with an augmented computational notebook interface. DataLab supports various BI tasks for different data roles in data preparation, analysis, and visualization by seamlessly combining LLM assistance with user customization within a single environment. To achieve this unification, we design a domain knowledge incorporation module tailored for enterprise-specific BI tasks, an inter-agent communication mechanism to facilitate information sharing across the BI workflow, and a cell-based context management strategy to enhance context utilization efficiency in BI notebooks. Extensive experiments demonstrate that DataLab achieves state-of-the-art performance on various BI tasks across popular research benchmarks. Moreover, DataLab maintains high effectiveness and efficiency on real-world datasets from Tencent, achieving up to a 58.58% increase in accuracy and a 61.65% reduction in token cost on enterprise-specific BI tasks.

[Abstract source](https://arxiv.org/abs/2412.02205). Version: arXiv abstract; may differ from published version.

### D-Bot: Database Diagnosis System using Large Language Models

**Primary layer:** Execution · **Topic:** Communication Optimization

**MAS evidence:** Several selected LLM experts analyze the same anomaly, exchange summarized procedures/results and revise their findings through cross-review.

**Relevant mechanism:** Summarize agents' execution records and exchange concise evidence for cross-review.

**Inspected source:** [§7, pp2521–2522](https://www.vldb.org/pvldb/vol17/p2514-li.pdf).

**Limit:** Retain the coordination and message-preparation mechanism. Database diagnosis itself is MAS for DB, and generic MAS-wide gains are not established.

**Abstract — original text from the existing library**

Database administrators (DBAs) play an important role in managing database systems. However, it is hard and tedious for DBAs to manage vast database instances and give timely response (waiting for hours is intolerable in many online cases). In addition, existing empirical methods only support limited diagnosis scenarios, which are also labor-intensive to update the diagnosis rules for database version updates. Recently large language models (LLMs) have shown great potential in various fields. Thus, we propose D-Bot , an LLM-based database diagnosis system that can automatically acquire knowledge from diagnosis documents, and generate reasonable and well-founded diagnosis report (i.e., identifying the root causes and solutions) within acceptable time (e.g., under 10 minutes compared to hours by a DBA). The techniques in D-Bot include ( i ) offline knowledge extraction from documents, ( ii ) automatic prompt generation (e.g., knowledge matching, tool retrieval), ( iii ) root cause analysis using tree search algorithm, and ( iv ) collaborative mechanism for complex anomalies with multiple root causes. We verify D-Bot on real benchmarks (including 539 anomalies of six typical applications), and the results show D-Bot can effectively identify root causes of unseen anomalies and significantly outperforms traditional methods and vanilla models like GPT-4.

[Abstract source](https://api.openalex.org/works/W4401352024). Version: OpenAlex indexed abstract.

### SQL-Factory: A Multi-Agent Framework for High-Quality and Large-Scale SQL Generation

**Primary layer:** Execution · **Topic:** Agent Scheduling

**MAS evidence:** Generation, Expansion and Management teams coordinate; a Management Agent consumes a Critical Agent's evaluation and changes the active team.

**Relevant mechanism:** Use a shared result pool and quality statistics to choose which agent team runs next.

**Inspected source:** [§3, §4.1 and §5, pp294–303](https://www.vldb.org/pvldb/vol19/p292-gao.pdf).

**Limit:** Retain its data-driven team scheduling and shared result-pool mechanism. SQL diversity, executability and coverage remain application-specific criteria.

**Abstract — original text from the existing library**

High quality SQL corpus is essential for intelligent databases. For example, Text-to-SQL requires SQL queries and corresponding natural language questions as training samples. However, collecting such a query corpus remains challenging in practice due to the high cost of manual annotation, which highlights the importance of automatic SQL generation. Despite recent advances, existing generation methods still face limitations in achieving both diversity and cost-effectiveness. Besides, many methods also treat all tables equally, which overlooks schema complexity and leads to under-utilization of structurally rich tables. To address these issues, this paper proposes a multi-agent framework for high-quality and large-scale SQL generation, dubbed SQL-Factory. It decomposes the generation process into three collaborative teams: the Generation Team explores diverse query structures using a powerful language model, the Expansion Team scales promising patterns via a lightweight language model, and the Management Team adaptively schedules the workflow and evaluates the quality of synthesized queries. This modular framework ensures a balanced trade-off between diversity, scalability, and generation cost. We apply SQL-Factory to four widely used benchmarks and generate over 300,000 SQL queries with less than $200 API cost. Our generated queries achieve higher diversity compared to other methods, and extensive experiments demonstrate that the generated queries significantly improve model performance in various downstream tasks.

[Abstract source](https://api.openalex.org/works/W7139098105). Version: OpenAlex indexed abstract.

### MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization

**Primary layer:** Execution · **Topic:** Execution Validation

**MAS evidence:** A Coordinator Agent orchestrates Database/Query, Visualization Implementation and Validation/Evaluation agents through feedback.

**Relevant mechanism:** Check prerequisites and execution constraints, control recovery, and bound agent interaction loops.

**Inspected source:** [§§4.2–4.3 and §6.3, Tables 3–4](https://arxiv.org/pdf/2601.18320).

**Limit:** Retain the rule-governed collaboration mechanism and its ablation. Visualization is the application, not a fourth survey dimension. Bounded termination is not a guarantee that every generated answer is correct.

**Abstract — original text from the existing library**

Real-world visualization tasks involve complex, multi-modal requirements that extend beyond simple text-to-chart generation, requiring reference images, code examples, and iterative refinement. Current systems exhibit fundamental limitations: single-modality input, one-shot generation, and rigid workflows. While LLM-based approaches show potential for these complex requirements, they introduce reliability challenges including catastrophic failures and infinite loop susceptibility. To address this gap, we propose MultiVis-Agent, a logic rule-enhanced multi-agent framework for reliable multi-modal and multi-scenario visualization generation. Our approach introduces a four-layer logic rule framework that provides mathematical guarantees for system reliability while maintaining flexibility. Unlike traditional rule-based systems, our logic rules are mathematical constraints that guide LLM reasoning rather than replacing it. We formalize the MultiVis task spanning four scenarios from basic generation to iterative refinement, and develop MultiVis-Bench, a benchmark with over 1,000 cases for multi-modal visualization evaluation. Extensive experiments demonstrate that our approach achieves 75.63% visualization score on challenging tasks, significantly outperforming baselines (57.54-62.79%), with task completion rates of 99.58% and code execution success rates of 94.56% (vs. 74.48% and 65.10% without logic rules), successfully addressing both complexity and reliability challenges in automated visualization generation.

[Abstract source](https://api.openalex.org/works/W7151398635). Version: OpenAlex indexed abstract.

### OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment

**Primary layer:** Execution · **Topic:** Execution Validation

**MAS evidence:** Extraction, Generation, Refinement and Alignment agents exchange intermediate results; §3.1 explicitly addresses error accumulation across collaborating agents.

**Relevant mechanism:** Validate each agent output against its input and upstream results before passing it to downstream agents.

**Inspected source:** [Author version §3.1, §§3.4–3.5 and §4.3, Table 4](https://arxiv.org/pdf/2502.14913).

**Limit:** Retain only inter-agent consistency checking and correction. The rules and evaluation are Text-to-SQL-specific; this is not a general MAS correctness guarantee. Section references use the author preprint, whose layout differs from the published article.

**Abstract:** [Original abstract/source entry](https://api.openalex.org/works/W4411403530). The existing library does not reproduce the full abstract; the mechanism description above is our paraphrase.

### SpatialSQL: A Multi-Agent System for Interactive and Observable Spatial Text-to-SQL

**Primary layer:** Execution · **Topic:** Execution Analysis

**MAS evidence:** Planner, Context Retrieval, Knowledge Retrieval, SQL Generator and SQL Validator exchange context, drafts and feedback.

**Relevant mechanism:** Record linked interaction and execution traces for monitoring, replay and failure inspection.

**Inspected source:** [§§2.2–2.3, pp4523–4524](https://www.vldb.org/pvldb/vol19/p4522-tong.pdf).

**Limit:** Retain structured trace collection and inspection. The demo does not prove general causal error attribution or an evaluated automatic root-cause algorithm.

**Abstract — original text from the existing library**

With significant advancements in Large Language Models (LLMs) in recent years, text-to-SQL has emerged as a prominent paradigm for querying databases, aiming to transform natural language into executable database queries. Despite the outstanding performance of previous works on relational databases, few studies have addressed spatial queries, where both data and queries are related to spatial information. Compared to text-to-SQL tasks on relational databases, generating spatial SQL from natural language remains challenging due to the complexity of geometric operations and spatial reasoning. To tackle these issues, this paper presents SpatialSQL, a multi-agent system for interactive and observable spatial text-to-SQL generation. At the core of SpatialSQL, several specially designed agents are coordinated to interpret user intent, construct spatial SQL queries, and iteratively refine them based on execution feedback. Additionally, SpatialSQL integrates a platform for monitoring and managing the entire interaction lifecycle, including chat histories, SQL execution traces, and user feedback, through an administrative console. To support interactive exploration, SpatialSQL surfaces intermediate reasoning artifacts and execution results, enabling users to inspect and guide the query generation process. We demonstrate SpatialSQL through a unified user interface and management console that together support transparent query construction and system observability.

[Abstract source](https://api.openalex.org/works/W7212771062). Version: OpenAlex indexed abstract.

## Related demo publications

| Publication | Relation and evidence limit |
|---|---|
| [UNITQA: A Unified Automated Tabular Question Answering System with Multi-Agent Large Language Models](https://doi.org/10.1145/3722212.3725140) — SIGMOD 2025 · demo | UNITQA is related to AutoTQA and describes five agents with FSM scheduling. Official demo-list metadata and the existing indexed abstract were checked; its full paper was unavailable in this pass. Keep as a related publication, not another independently verified scheduler. |
| [Demonstration of MultiVis-Agent: Interactively Generating Reliable Visualizations via Logic-Rule Agents](https://doi.org/10.1145/3788853.3801584) — SIGMOD 2026 · demo | Demo of MultiVis-Agent. The author institution confirms the central coordinator and logic-rule design. The research paper supplies the detailed mechanism and ablation evidence; do not count the demo as another method. |

## Candidates and boundaries kept visible

These entries are not silently discarded or represented as confirmed DB-for-MAS results.

| Paper | Tentative reading group / status | Reason |
|---|---|---|
| [Efficient Neural-Symbolic Data System via Multi-Agent Collaboration](https://icde2026.github.io/deft-papers.html) | Planning candidate · primary content pending | Official ICDE 2026 DEFT publication metadata is verified. Publisher access did not expose the paper; secondary summaries do not justify a confirmed mechanism or layer. |
| [Towards Unsupervised Entity Alignment for Highly Heterogeneous Knowledge Graphs](https://github.com/eduzrh/AdaCoAgentEA) | Execution candidate · protocol details pending | AdaCoAgentEA's author repository confirms collaborating agents and communication protocols, but detailed primary-paper evidence on what the protocol manages and how it is evaluated is still missing. |
| [Carnot: Interpretable, Interactive, and Optimized Execution of Deep Research Queries](https://www.vldb.org/pvldb/vol19/p4642-russo.pdf) | Planning-related boundary · not admitted as MAS optimization | Carnot §2.3 confirms a QueryPlanner, a data-discovery subagent and an LLM-assisted optimizer. Its inspected optimization/revision machinery targets semantic query operators; a separate collaboration-support mechanism is not sufficiently established. |
| [AutoPrep: Natural Language Question-Aware Data Preparation with a Multi-Agent Framework](https://www.vldb.org/pvldb/vol18/p3504-fan.pdf) | Planning-related application · outside the main list | AutoPrep has cooperating Planner and Programmer agents, but its logical plan describes data-preparation operations. Those plans are not automatically MAS collaboration plans. |
| [DocETL: Agentic Query Rewriting and Evaluation for Complex Document Processing](https://www.vldb.org/pvldb/vol18/p3035-shankar.pdf) | Planning-related application · outside the main list | DocETL uses generation and validation agents to optimize document-processing plans. Using a MAS as the optimizer does not establish optimizing the MAS itself. |
| [Multi-Objective Agentic Rewrites for Unstructured Data Processing](https://www.vldb.org/pvldb/vol19/p3062-shankar.pdf) | Planning-related optimizer · outside the main list | MOAR searches semantic-operator rewrites. Its plan cost/quality objectives alone do not establish a collaborating MAS as the optimized object. |
| [Credo: Declarative Control of LLM Pipelines via Beliefs and Policies](https://www.vldb.org/pvldb/vol19/p4518-lu.pdf) | Execution-related system · MAS not established | Credo manages beliefs, policies and LLM pipeline operators. Mentioning AutoGen in related work does not establish a collaborating MAS in the demonstrated system. |
| [AgenticScholar: Agentic Data Management with Pipeline Orchestration for Scholarly Corpora](https://arxiv.org/pdf/2603.13774) | Planning-related system · MAS not established | AgenticScholar has a hybrid planner and composable operators. The inspected primary text does not establish multiple collaborating autonomous agents. |
| [Mil: Cost-guided Minimum Makespan Scheduling for Applications of Multiple LLMs](https://www.vldb.org/pvldb/vol19/p1893-fang.pdf) | Scheduling-related system · MAS not established | Mil schedules multiple-model applications; ensembling, routing and chained summarization do not by themselves establish a cooperating LLM MAS. |
| [HEXGEN-FLOW: Optimizing LLM Inference Request Scheduling for Agentic Text-to-SQL](https://arxiv.org/pdf/2505.05286v3) | Confirmed MAS workload support · primary layer: Inference Infrastructure | HEXGEN-FLOW v3 evaluates CHESS-style workflows and MAC-SQL. MAC-SQL explicitly has collaborating agents. Restore MAS-support evidence, but its optimized object is inference-request serving, so do not force it into Planning or Execution. |
| [SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning](https://www.vldb.org/pvldb/vol18/p4874-chang.pdf) | Supporting Planning algorithm · primary layer remains Action | SagaLLM Algorithm 1 constructs roles and dependencies; keep this as a chapter reference. Its principal contribution remains transactional compensation/recovery; no duplicate primary entry is added. |
| [SAGA: Synthetic Agentic Graph Architecture for Temporal Benchmark Generation](https://www.vldb.org/pvldb/vol19/p4834-zhang.pdf) | Execution-related application · outside the main list | SAGA partitions generation tasks into time blocks; its replay engine labels anomalies in generated graph data. This is not evidence of recovering erroneous MAS executions or synchronizing arbitrary agent state. |
| [NL2SQLBench: A Modular Benchmarking Framework for LLM-Enabled NL2SQL Solutions](https://www.vldb.org/pvldb/vol19/p1001-hou.pdf) | Execution analysis candidate — not admitted | The abstract and introduction establish modular benchmarking of NL2SQL algorithms, including cost and latency. They do not establish a MAS-specific collaboration-analysis mechanism; a multi-agent benchmarking implementation alone is insufficient. |

## Where the earlier multi-agent records went

All records carrying the earlier M label remain in the library. A pending support-mechanism review is not a negative finding about the paper. The table includes works outside the two requested layers.

| Earlier multi-agent record | Current decision | Primary layer or reason |
|---|---|---|
| [Agent-OM: Leveraging LLM Agents for Ontology Matching](https://doi.org/10.14778/3712221.3712222) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [AutoTQA: Towards Autonomous Tabular Question Answering through Multi-Agent Large Language Models](https://doi.org/10.14778/3685800.3685816) | include_component | Execution |
| [D-Bot: Database Diagnosis System using Large Language Models](https://doi.org/10.14778/3675034.3675043) | include_component | Execution |
| [Demonstration of DB-GPT: Next Generation Data Interaction System Empowered by Large Language Models](https://doi.org/10.14778/3685800.3685876) | include_component | Execution |
| [DataLab: A Unified Platform for LLM-Powered Business Intelligence](https://doi.org/10.1109/icde65448.2025.00326) | include_component | Execution |
| [Rabbit: Retrieval-Augmented Generation Enables Better Automatic Database Knob Tuning](https://doi.org/10.1109/icde65448.2025.00284) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Towards Unsupervised Entity Alignment for Highly Heterogeneous Knowledge Graphs](https://doi.org/10.1109/icde65448.2025.00283) | hold_primary_content | AdaCoAgentEA's author repository confirms collaborating agents and communication protocols, but detailed primary-paper evidence on what the protocol manages and how it is evaluated is still missing. |
| [Adda: Towards Efficient in-Database Feature Generation via LLM-based Agents](https://doi.org/10.1145/3725262) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [AgentTune: An Agent-Based Large Language Model Framework for Database Knob Tuning](https://doi.org/10.1145/3769758) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Drama : Unifying Data Retrieval and Analysis for Open-Domain Analytic Queries](https://doi.org/10.1145/3769781) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [OmniTune: A Universal Framework for Query Refinement via LLMs](https://doi.org/10.1145/3722212.3725121) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [OpenSearch-SQL: Enhancing Text-to-SQL with Dynamic Few-shot and Consistency Alignment](https://doi.org/10.1145/3725331) | include_component | Execution |
| [UNITQA: A Unified Automated Tabular Question Answering System with Multi-Agent Large Language Models](https://doi.org/10.1145/3722212.3725140) | related_demo_not_independent_method | UNITQA is related to AutoTQA and describes five agents with FSM scheduling. Official demo-list metadata and the existing indexed abstract were checked; its full paper was unavailable in this pass. Keep as a related publication, not another independently verified scheduler. |
| [A Demonstration of QueryArtisan:  Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code](https://doi.org/10.14778/3750601.3750647) | include_component | Planning |
| [AutoPrep: Natural Language Question-Aware Data Preparation with a Multi-Agent Framework](https://doi.org/10.14778/3748191.3748211) | not_admitted_direction | AutoPrep has cooperating Planner and Programmer agents, but its logical plan describes data-preparation operations. Those plans are not automatically MAS collaboration plans. |
| [DocETL: Agentic Query Rewriting and Evaluation for Complex Document Processing](https://doi.org/10.14778/3746405.3746426) | not_admitted_direction | DocETL uses generation and validation agents to optimize document-processing plans. Using a MAS as the optimizer does not establish optimizing the MAS itself. |
| [SQL-Factory: A Multi-Agent Framework for High-Quality and Large-Scale SQL Generation](https://doi.org/10.14778/3778092.3778093) | include_component | Execution |
| [SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning](https://doi.org/10.14778/3750601.3750611) | include_system | Action |
| [Accurate Table Question Answering with Accessible LLMs](https://doi.org/10.1109/icde65706.2026.00020) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [FELA: A Multi-Agent Evolutionary System for Feature Engineering of Industrial Event Log Data](https://doi.org/10.1109/icde65706.2026.00292) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [LEAF-SQL: Level-Wise Exploration with Adaptive Fine-Graining for Text-to-SQL Skeleton Prediction](https://doi.org/10.1109/icde65706.2026.00181) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [ANTEATER: A Filter-then-Scrutinize Architecture for End-to-End Attack Investigation](https://doi.org/10.1145/3802012) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Adda: An Agent-Driven in-Database Feature Generation System](https://doi.org/10.1145/3788853.3801606) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Chatty-KG: A Multi-Agent AI System for On-Demand Conversational Question Answering over Knowledge Graphs](https://doi.org/10.1145/3786632) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [ConDABench: Interactive Evaluation of Language Models for Data Analysis](https://doi.org/10.1145/3788853.3803099) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [DeepEye: A Steerable Self-driving Data Agent System](https://doi.org/10.1145/3788853.3801612) | include_component | Execution |
| [Demonstration of MultiVis-Agent: Interactively Generating Reliable Visualizations via Logic-Rule Agents](https://doi.org/10.1145/3788853.3801584) | related_demo_not_independent_method | Demo of MultiVis-Agent. The author institution confirms the central coordinator and logic-rule design. The research paper supplies the detailed mechanism and ablation evidence; do not count the demo as another method. |
| [Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective](https://doi.org/10.1145/3802046) | include_system | Execution |
| [MultiVis-Agent: A Multi-Agent Framework with Logic Rules for Reliable and Comprehensive Cross-Modal Data Visualization](https://doi.org/10.1145/3786670) | include_component | Execution |
| [A Demo of Interactive Thematic Data Collection on the Live Web](https://doi.org/10.14778/3827998.3828064) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [CoeusBI: A Comprehensive Interactive Business Intelligence System Powered by LLMs at Baidu](https://doi.org/10.14778/3827998.3828017) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [DataMagic: Transforming Tabular Data into Data Insight Video](https://doi.org/10.14778/3827998.3828057) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Hypothesis Exploration with LLM-driven Intelligent Orchestration System](https://doi.org/10.14778/3827998.3828129) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [NL2SQLBench: A Modular Benchmarking Framework for LLM-Enabled NL2SQL Solutions](https://doi.org/10.14778/3796195.3796211) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [Rethinking Query Optimization for Multi-Agent Systems](https://doi.org/10.14778/3845598.3845602) | include_vision | Execution |
| [Revisiting Task-Oriented Dataset Search in the Era of Large Language Models: Challenges, Benchmark, and Solution](https://doi.org/10.14778/3796195.3796209) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |
| [SAGA: Synthetic Agentic Graph Architecture for Temporal Benchmark Generation](https://doi.org/10.14778/3827998.3828134) | not_admitted_direction | SAGA partitions generation tasks into time blocks; its replay engine labels anomalies in generated graph data. This is not evidence of recovering erroneous MAS executions or synchronizing arbitrary agent state. |
| [SpatialSQL: A Multi-Agent System for Interactive and Observable Spatial Text-to-SQL](https://doi.org/10.14778/3827998.3828055) | include_component | Execution |
| [SuperDRI: Graph-Guided Autonomous Troubleshooting for Cloud Databases](https://doi.org/10.14778/3827998.3828095) | pending_mechanism_review | 已有多 agent 证据，协作支撑机制尚待逐项复审；暂不纳入，不等于已判定为无关或只有 MAS for DB。 |

**Review limits:** selected full-text sections and official/author metadata were checked. The historical library has not been fully read. No paper is marked as human-read; experiments were not reproduced. Main-conference papers, related demos, provisional leads and wrong-direction applications are not interchangeable evidence.
