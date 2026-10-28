# Planning Layer: Strict MAS and DB-Venue Review

Updated 2026-10-27 after a component-level re-review. The earlier one-entry Planning display was an incomplete subset. The current [Planning and Execution reading list](planning-execution-review.md) includes documented support mechanisms within application papers, with section evidence and limits. The scope still requires explicit collaborating LLM agents and verified target DB venues.

| Layer | Data Management | Data Preparation | Data Analysis |
|---|---|---|---|
| **Planning** | **Task Decomposition and Sharing** | **Agent Role and Dependency Extraction** | **Task Reuse Analysis** |

These topic boundaries do not imply that each topic has a dedicated, independently evaluated solution. Agent Role and Dependency Extraction covers logical role/task construction and prerequisites; QueryArtisan supports only the task-level component. Concrete agent selection and assignment belong to Execution.

## What each topic owns

| Topic | Concise task | Output | Boundary |
|---|---|---|---|
| Task Decomposition and Sharing | Organize agents' requests into tasks and merge compatible work. | A logical collaboration plan. | Changes the plan; excludes worker assignment, model choice and runtime scheduling. |
| Agent Role and Dependency Extraction | Extract logical roles, tasks, inputs, outputs and prerequisites. | Structured planning input. | Prepares task descriptions; does not select agent instances or reconstruct notebook context. |
| Task Reuse Analysis | Determine whether agents can share a task or result. | Reuse conditions and admissible sharing candidates. | Analyzes sharing validity; excludes cache storage, eviction and KV management. |

The distinction between the first and third topics is an output boundary: analysis determines whether sharing is valid; management applies an admissible merge to the plan. Cross-layer papers may appear under multiple supported topics. Primary-layer labels in the review inventory are retained for unique-paper counts, not as a restriction on display.

## ACDS boundary

ACDS §3.1–3.3 (local PDF pp6–7) treats the input as a workload, constructs logical units and dependencies, rewrites compatible units and produces `SQ = <U, precedence>`. Execution §4 maps these units to agent invocations, implementations and stages. We follow that distinction even where other authors call executable workflows “plans.” The ACDS manuscript supplies the organizing framework; it is not counted as a newly verified DB conference publication.

## Papers that survive the strict gates

| Paper | Venue / publication year | Evidence relevant to Planning | Cross-layer placement |
|---|---|---|---|
| [Supporting Our AI Overlords: Redesigning Data Systems to be Agent-First](https://www.vldb.org/cidrdb/papers/2026/p32-liu.pdf) | **CIDR 2026 — separate DB conference extension; vision** | §3 and §5.2 propose pruning redundant probes and sharing work across agents and turns using goals, phase and accuracy needs. Supports decomposition/sharing and reuse as research topics. | **Planning / Task Decomposition and Sharing; Task Reuse Analysis** |
| [A Demonstration of QueryArtisan: Real-Time Data Lake Analysis via Dynamically Generated Data Manipulation Code](https://www.vldb.org/pvldb/vol18/p5263-tang.pdf) | **PVLDB 2025 — demo; component evidence** | §3 identifies subtask requirements, prerequisite queries and constraints before the Analysis Executor receives work. Retain this task-preparation mechanism only. | **Planning / Task and Dependency Extraction** |
| [Efficient LLM Serving for Agentic Workflows: A Data Systems Perspective — Helium](https://doi.org/10.1145/3802046) | **SIGMOD 2026 — system** | The [author extended version](https://arxiv.org/pdf/2603.16104), §4, implements pruning, identical-subgraph merging and deterministic result reuse. Figure 2 and §7.1 explicitly include multi-agent debate and expert/critic collaboration. | **Planning / Task Decomposition and Sharing; Task Reuse Analysis**; also Execution and Inference Infrastructure |
| [SagaLLM: Context Management, Validation, and Transaction Guarantees for Multi-Agent LLM Planning](https://www.vldb.org/pvldb/vol18/p4874-chang.pdf) | **PVLDB 2025 — experience/system** | Algorithm 1 (p4879) constructs roles and dependencies from task descriptions. This supplies limited evidence for preparing structured task/dependency information. | **Planning / Task Decomposition and Sharing; Agent Role and Dependency Extraction**; also Action / Compensation and Recovery |

**The Planning paper list displays four distinct works:** SagaLLM, Helium, Agent-First and QueryArtisan. Cross-layer placement reflects the mechanism discussed in each entry. The earlier focused inventory has two primary Planning records for counting purposes; this does not limit the displayed list. See the [paper list](../README.md#planning) for source/PDF links and topic-by-topic matching boundaries. This is a bounded evidence result, not a claim that no other Planning work exists.

Helium starts from a supplied workflow DAG. Its structural matching and deterministic-result rules do not establish arbitrary natural-language task equivalence, automatic role discovery, or safe merging of side-effecting actions. SagaLLM does not independently evaluate a general task/dependency extraction algorithm. The CIDR proposal is not a completed optimizer. These distinctions determine what can be claimed for each topic.

| Topic | Current evidence | What remains open in this corpus |
|---|---|---|
| Task Decomposition and Sharing | Task-structure construction in SagaLLM; concrete structural rewriting in Helium; broader MAS-aware work selection proposed by the CIDR paper. | How to derive and merge logical work while preserving every participating agent's requirements. |
| Agent Role and Dependency Extraction | QueryArtisan prepares prerequisites and constraints before agent handoff; SagaLLM contains a construction step. | A separately evaluated method for extracting and checking general logical collaboration dependencies. |
| Task Reuse Analysis | Helium checks matching structure/inputs and deterministic outputs; CIDR discusses goal-aware sharing. | Conditions for valid reuse across different contexts, permissions, source versions and output requirements. |

## What the GitHub lists changed

The lists were treated as discovery inputs, not authority for MAS or venue status:

- [HKUSTDial/awesome-data-agents](https://github.com/HKUSTDial/awesome-data-agents) contains many data-task applications, single-agent approaches, workshops and papers from other venues. Its autonomy levels do not correspond to the ACDS functional layers.
- [kyegomez/awesome-multi-agent-papers](https://github.com/kyegomez/awesome-multi-agent-papers) matches DataLab and AllHands in our cached DB conference records. Their primary sources lead to different decisions.
- [DataLab](https://arxiv.org/html/2412.02205v3), ICDE 2025, is retained **only for its evaluated inter-agent data-exchange component** (§V and §VII-D). Its proxy and specialized agents exchange structured information through a shared buffer. It belongs to **Execution / Communication Optimization**. Its cell DAG (§VI) retrieves relevant notebook context; it is not a Planning dependency extractor.
- [AllHands](https://www.microsoft.com/en-us/research/publication/allhands-ask-me-anything-on-large-scale-verbatim-feedback-via-large-language-models/), ICDE 2025, describes one QA-agent framework with planner, code-generation and execution components (§3.4). The inspected evidence does not establish the required cooperating MAS. It is not admitted merely because the repository lists it.

The initial repository pass did not establish a new primary Planning entry. The subsequent review of the existing library restored QueryArtisan's specific task-preparation component and several Execution mechanisms. Unmatched preprints remain **not admitted for lack of verified target-venue evidence**, not asserted to have no DB version anywhere.

## Removed from the active Planning list

| Paper/group | Why it does not pass the current gates |
|---|---|
| DocETL | Generation and validation agents optimize document-processing queries; this is not evidence that its target is the collaboration system itself. |
| AOP, SIC, Palimpzest, LOTUS, Abacus | Useful semantic pipeline or constraint methods, but no required MAS optimization evidence established by the inspected material. Analogies no longer enter this list. |
| From RAG to Agentic AI | Explicit MAS vision, but **LLM+Graph@VLDB workshop**, not a main-conference publication. |
| AFlow | [ICLR 2025 proceedings](https://proceedings.iclr.cc/paper_files/paper/2025/hash/5492ecbce4439401798dcd2c90be94cd-Abstract-Conference.html); fails the DB venue gate. |
| Planning with Multi-Constraints via Collaborative Language Agents | [COLING 2025 proceedings](https://aclanthology.org/2025.coling-main.672/); fails the DB venue gate. |
| NiagaraCQ, SharedDB, Eddies | Historical foundations, outside both the recent window and explicit LLM-MAS requirement. |
| stratum | [PVLDB paper](https://www.vldb.org/pvldb/vol19/p3799-phani.pdf) evaluates AIDE-generated pipeline batches (§5); multiple pipeline variants do not establish multiple collaborating agents. |

NOMA remains **Execution**: joint agent topology, model and engine selection is not a new Planning primary entry. *Efficient Neural-Symbolic Data System via Multi-Agent Collaboration* is confirmed in the [ICDE 2026 DEFT list](https://icde2026.github.io/deft-papers.html), but sufficient primary content for its mechanism remains unavailable; it is held out rather than classified from its title.

## Decision for this round

Use the three topics in the opening table. Prioritize the concrete question **when multiple agents may share logical work or reuse a result**. Keep extraction as an explicitly open topic with limited current evidence. Do not expand Planning to fill sparse cells with agent scheduling, communication, context retrieval, caching or recovery.

AI-assisted review; selected sections and metadata were checked, not every full paper in the historical library. No user-read status or independent experimental reproduction is claimed. The [audit](../data/strict_mas_review.json) records source snapshots, individual admission decisions and evidence limits.
