# AO-ATP-001 — Enterprise Architecture and Service Delivery Transformation Playbook

| Field | Value |
|---|---|
| Identifier | AO-ATP-001 |
| Title | Enterprise Architecture and Service Delivery Transformation Playbook |
| Version | 0.1.0 |
| Status | Proposed planning guidance |
| Authority | Agentic-Operation |
| Classification | Non-normative, method and reference guidance |
| Related assurance baseline | [AO-OAR-001](../assurance/AO-OAR-001-operational-assurance-review.md) |
| Conceptual baseline | [AO-CBC-001](../architecture/AO-CBC-001-conceptual-baseline.md) |
| OpenDEA foundation | [TechNeHub Labs](https://github.com/technehub-labs/) |
| AOP foundation | [Agentic Operating Procedure](https://github.com/agentic-operating-procedure) |

## 1. Purpose

Agentic Operations requires more than adding AI agents to an existing application estate or automating individual tasks. It changes how an enterprise defines work, composes services, allocates decisions, coordinates execution, manages authority and measures outcomes.

This playbook is intended to help enterprise leaders and practitioners plan that change across two connected transformation domains:

1. **Operational architecture transformation:** move from procedure-led work with predominantly predetermined execution to work governed by versioned Agentic Operating Procedures (AOPs), coordinated human and non-human agents, bounded authority and verifiable outcomes.
2. **Enterprise and software architecture transformation:** move from architecture descriptions centred primarily on applications, integrations and fixed service flows to a model-grounded architecture that relates enterprise purpose, capabilities, processes, business services, information-system services, system functions, components, interfaces, information, controls and outcomes.

The playbook brings together:
- Agentic-Operation's enterprise operating model, AI Agent management standards and operational assurance;
- AOP's normative operational specification, toolchain, context graph, reference harness and conformance assets;
- OpenDEA's enterprise architecture, canonical metamodel, catalogs, semantic runtime and architecture visualization.

It provides a planning method and worked-example paths. It does not declare these portfolios to be a unified production platform, prescribe a single vendor stack, or change the normative authority of any participating programme.

## 2. The pivotal question

The central question for an enterprise is:

> **How must we redesign the enterprise's work, services, systems, decision rights and human-agent relationships so that business outcomes can be realized through governed, model-grounded and continuously assured coordination of human and non-human capabilities?**

This question is deliberately broader than:
- Which tasks can be automated?
- Which agents should we deploy?
- Which applications should we replace?
- Which APIs should we expose to agents?
- Which model or agent framework should we standardize on?

Those are downstream design decisions. The starting point is the enterprise outcome and the work system that produces it.

The transformation should answer, for every selected value stream:
1. What outcome is required, for whom, and under what service and risk conditions?
2. What capabilities and business processes contribute to that outcome?
3. What work actually occurs, including variants, exceptions, hand-offs and informal workarounds?
4. Which decisions and actions are deterministic, judgment-intensive, delegable, approval-gated or prohibited?
5. Which business services and information-system services support the work?
6. Which system functions, components, interfaces, data and external dependencies realize those services?
7. What should remain human-led, become agent-assisted, become agent-executed or be redesigned altogether?
8. What AOP, skills, harness controls, agent identities, model bindings and trust mechanisms are required?
9. How will the enterprise verify the work, intervene, recover and demonstrate outcomes?
10. What is the safe transition path from the current architecture to the target operating architecture?

## 3. Architecture principles

### 3.1 Model the enterprise before refactoring its software

Software refactoring should be guided by an explicit model of the enterprise and its operating context. Do not start by decomposing monoliths, introducing agents, or replacing integration technology without first understanding the capabilities, processes, services, responsibilities and outcomes the software exists to support.

### 3.2 Keep business intent distinct from implementation

A business capability, business process, business service, information-system function, information-system service, component and integration interface are related but not interchangeable concepts.

The OpenDEA metamodel is the semantic authority for these distinctions. Use canonical entity definitions and typed relationships; do not create local synonyms or conflate catalog records.

### 3.3 Preserve service contracts while changing realization

A service contract can remain stable while its realization changes from a fixed application flow to a composition of system functions, services, agents, human decisions and external capabilities. Separate what the service promises from how it is fulfilled.

### 3.4 Treat AOP as an operational specification, not a prompt

AOP makes intent, context, constraints, authority, capabilities, coordination, control and assurance explicit. It is not a prompt template, a rewritten SOP, or a process diagram with an agent assigned to each step.

### 3.5 Separate proposal, authorization and execution

An agent may interpret, recommend and propose. Authorization must be enforced independently of the agent's own model context. Execution must be bounded by the approved procedure, delegated authority, policy and runtime controls.

### 3.6 Design for coexistence and progressive transition

The target architecture will usually contain existing applications, services, integration platforms, human work, agents and new runtime capabilities together. Migration must be incremental, reversible where possible and governed by evidence.

### 3.7 Make evidence a first-class architecture concern

The architecture must be able to establish what was intended, what was observed, what was authorized, what executed, what changed and whether the intended outcome was achieved.

## 4. The architecture model: enterprise intent to executable work

The following view connects the enterprise model to agentic execution. It is a conceptual integration view, not a new OpenDEA or AOP metamodel.

```text
ENTERPRISE STRATEGY, STAKEHOLDERS AND OUTCOMES
                    |
                    v
        BUSINESS CAPABILITIES / VALUE STREAMS
                    |
                    v
       BUSINESS PROCESSES / BUSINESS SERVICES
                    |
          SOPs + observed work evidence
                    |
                    v
       AOP: INTENT, CONTEXT, CONSTRAINTS,
       AUTHORITY, CAPABILITIES, COORDINATION,
              CONTROL, ASSURANCE
                    |
                    v
          DOMAIN AGENT HARNESS / RUNTIME
                    |
        +-----------+------------+
        |           |            |
        v           v            v
      HUMAN       AGENTS      SYSTEM SERVICES
   authorities   and skills   and components
        |           |            |
        +-----------+------------+
                    |
                    v
       VERIFIED ACTIONS AND SERVICE RESULTS
                    |
                    v
       OPERATIONAL / BUSINESS OUTCOME EVIDENCE
                    |
                    v
       ASSESS, LEARN, REVISE AND RE-ENGINEER
```

OpenDEA provides the enterprise semantic model and the information-systems architecture vocabulary. AOP provides the governed operational specification and runtime discipline. Agentic-Operation establishes the enterprise operating model, AI Agent management and assurance context.

## 5. OpenDEA as the architecture-grounding model

### 5.1 Use the canonical semantic foundation

OpenDEA describes the enterprise as a connected, governable and evolvable semantic model. Its canonical metamodel is maintained in [dea-metamodel](https://github.com/technehub-labs/dea-metamodel); the enterprise concept structure is maintained in [dea-metaframework](https://github.com/technehub-labs/dea-metaframework); and the architecture layers and building-block allocation are maintained in [dea-architecture-framework](https://github.com/technehub-labs/dea-architecture-framework).

The metamodel distinguishes its normative source from generated projections and informative documentation. Architecture teams should consume the normative metamodel, version-pinned schemas, catalog records and typed relationships rather than treating diagrams or a viewer as semantic authority.

### 5.2 Distinguish the information-systems concepts

The Information Systems Semantic Architecture programme establishes a particularly important distinction for software and service refactoring:

| OpenDEA concept | Architectural question | Refactoring relevance |
|---|---|---|
| Business Capability | What durable ability does the enterprise require to deliver value? | Defines the business ability that must persist even as processes and systems change |
| Business Process | What purposeful enterprise work is performed to produce an outcome? | Defines the work being redesigned and the process boundaries |
| Business Service | What business-facing service or value proposition is offered to a consumer? | Defines the business service promise and consumer relationship |
| InformationSystemFunction (ISF) | What behaviour does an information system or one of its components perform? | Identifies system behaviour and functional responsibility |
| InformationSystemComponent (ISC) | What architectural constituent encapsulates a responsibility, structure or execution boundary? | Identifies application and integration components and their boundaries |
| InformationSystemService (ISS) | What service contract does an information system or software platform provide to a consumer? | Defines the service contract independently of its implementation |
| IntegrationInterface (II) | Through what interaction boundary is information or functionality exchanged? | Defines API, event, file, stream or other integration interaction surfaces |
| System / Information System | Which system is involved, and what is its architectural role? | Grounds system inventory, ownership, dependencies and lifecycle |
| Information / Data / Event | What information is consumed, produced, transformed or exchanged? | Grounds data contracts, lineage, event semantics and context |
| Relationship | How are the entities connected, and what is the meaning of that connection? | Enables impact analysis, dependency analysis and model validation |

Do not collapse these concepts:
- A capability is not a process.
- A process is not a system function.
- A system function is not a service contract.
- A service contract is not a component.
- A component is not an interface.
- An API is not the service itself.
- A service description does not prove that an implementation exists or is available.

The information-systems semantic architecture is being implemented through the CR-017 onward sequence in the metamodel programme. The reviewed CR documents identify CR-017 as the shared semantic architecture and CR-018 through CR-021 as the entity and relationship implementation sequence, with CR-022 for artifact and conformance closure. Treat the current status of each CR and catalog as a live dependency to verify before adopting a particular entity or repository path. In particular, some catalog READMEs still describe scaffold or rename states while the Information System Service catalog reports a populated state. Do not infer completion of an upstream CR from a downstream README alone.

### 5.3 Model the current and target architecture

For each selected value stream, establish linked views rather than a single application landscape diagram:

1. **Outcome and stakeholder view:** stakeholder, outcome, value proposition, service promise, measures and accountable owner.
2. **Capability view:** business capabilities required and their current realization.
3. **Process and work view:** business processes, activities, tasks, decisions, variants, exceptions and hand-offs.
4. **Business service view:** service contracts and consumer relationships.
5. **Information-systems view:** systems, system functions, components, information-system services and integration interfaces.
6. **Information and context view:** information assets, data entities, events, provenance, freshness and access constraints.
7. **AOP execution view:** procedures, skills, harness, agents, models, tools, authority and coordination.
8. **Governance and assurance view:** policies, guardrails, risks, approvals, controls, audit evidence and outcome verification.
9. **Transition view:** current state, target state, intermediate states, dependencies, migration increments and retirement criteria.

Use typed relationships from the canonical metamodel. Avoid maintaining independent spreadsheets or diagrams that duplicate entity definitions without stable references and reconciliation.

### 5.4 OpenDEA tools and entry points

| Resource | Use in the transformation | Evidence/status caveat |
|---|---|---|
| [dea-architecture-framework](https://github.com/technehub-labs/dea-architecture-framework) | Root model, architecture layers, building blocks and allocation | Check the current model version and allocation rules |
| [dea-metaframework](https://github.com/technehub-labs/dea-metaframework) | Enterprise Concept Framework and conceptual coordinates | Use as the concept framework, not as a substitute for process discovery |
| [dea-metamodel](https://github.com/technehub-labs/dea-metamodel) | Canonical entity/relationship semantics, schemas, validation and reference runtime | Normative semantic source is the metamodel specification; generated projections are derived |
| [Business Capability Catalog](https://github.com/technehub-labs/dea-catalog-business-capabilities) | Capability discovery and mapping to enterprise concerns | Use canonical capability records and their evidence/methodology |
| [Business Process Catalog](https://github.com/technehub-labs/dea-catalog-business-processes) | Process context, process identity, decomposition and process relationships | A context coordinate does not automatically imply a process |
| [Information System Function Catalog](https://github.com/technehub-labs/dea-catalog-system-functions) | Inventory system behaviours and functional responsibility | Repository README describes a scaffold/rename state; verify current canonical allocation and populated records |
| [Information System Component Catalog](https://github.com/technehub-labs/dea-catalog-application-components) | Model application/integration components and responsibility boundaries | Repository README describes a scaffold/rename state; verify current canonical allocation and population |
| [Information System Service Catalog](https://github.com/technehub-labs/dea-catalog-information-system-services) | Model information-system service contracts and consumers | README reports 623 admitted records; validate the current catalog and its gates before use |
| [API Contract Catalog](https://github.com/technehub-labs/dea-catalog-api-contracts) | Model API contract artefacts separately from integration interfaces and services | README describes population as gated; do not assume a complete API inventory |
| [Digital Enterprise Reference Architecture](https://github.com/technehub-labs/dea-catalog-reference-architecture) | Engagement sequencing and architecture deliverable blueprint | Reference guidance, not an automatically executed transformation |
| [DEA Web Viewer](https://github.com/technehub-labs/dea-web-viewer) | Visual exploration and stakeholder-facing model views | A viewer is a projection of the model, not the semantic authority |

The OpenDEA metamodel repository also contains a reference validator and runtime architecture documentation. The runtime architecture separates the semantic registry, knowledge graph, semantic services, integration and agent interfaces. The conceptual architecture explicitly distinguishes model, observed runtime state, assertion, evidence and derived knowledge. Those distinctions are important when agents consume architecture data or propose changes.

## 6. AOP as the operational engineering and transformation toolchain

### 6.1 The SOP-to-AOP method

The AOP programme's reference method is an observe, model, compile, lint, execute and assure pipeline. It is evidence-led: the SOP is a hypothesis about work; observed cases establish how work actually occurs; the governance manifest establishes what an agent may decide; the compiler produces an AOP that can be validated against the normative specification.

```text
CONTROLLED SOP
     |
     v
OBSERVE REAL WORK
case records, variants, decisions, exceptions, provenance
     |
     v
CONTEXT GRAPH OF WORK
entities, relationships, case stitching, operational twin
     |
     v
MINE AND EXTRACT
variants, decision rules, thresholds, provenance
     |
     v
GOVERNANCE MANIFEST
permitted / prohibited actions, authority classes, skills,
risk axes, context access, human hand-offs
     |
     v
COMPILE AOP
     |
     v
LINT AND NORMATIVE CONFORMANCE
     |
     v
EXECUTE IN A BOUNDED DOMAIN HARNESS
     |
     v
VERIFY, RECORD, REPLAY AND EVALUATE
```

### 6.2 AOP tools and their roles

| AOP resource | Role in the method | Practical starting point |
|---|---|---|
| [AOP Foundations](https://github.com/agentic-operating-procedure/aop-foundations) | Defines the AOP discipline, concepts and hierarchy | Establish conceptual and authority boundaries before tool selection |
| [AOP Specification](https://github.com/agentic-operating-procedure/aop-spec) | Normative AOP document model, eight dimensions and clauses | Validate against the current schema and normative clauses |
| [AOP Context Graph](https://github.com/agentic-operating-procedure/aop-context-graph) | Captures observed work, case records, stitching, operational twin and drift | Build an evidence-backed corpus of representative work |
| [AOP Toolkit](https://github.com/agentic-operating-procedure/aop-toolkit) | SOP parsing, variant mining, decision-rule extraction, AOP compilation and linting | Use the CLI walkthrough and included fault-management fixtures |
| [AOP Reference Harness](https://github.com/agentic-operating-procedure/aop-reference-harness) | Runtime loop, external guardrail, credential broker, escalation, evidence and replay | Run the end-to-end reference gate and study its explicit limits |
| [AOP Registry](https://github.com/agentic-operating-procedure/aop-registry) | Publishes and versions AOP artefacts | Govern publication and retrieval of approved AOPs |
| [AOP Conformance](https://github.com/agentic-operating-procedure/aop-conformance) | Validates AOP documents and harnesses; supports certification | Run document and harness profiles, including must-fail fixtures |
| [AOP Governance](https://github.com/agentic-operating-procedure/aop-governance) | Owns AOP change and programme governance | Route normative changes through AOP governance |

The AOP Toolkit README identifies the command surface as `python3 -m aop_toolkit`. Its reference walkthrough includes:

```bash
python3 -m aop_toolkit parse-sop fixtures/sop/rb-line-001.md

python3 -m aop_toolkit mine \
  fixtures/cases/fault-management-cases.jsonl \
  --authority-map <authority-map.json>

python3 -m aop_toolkit compile \
  --sop fixtures/sop/rb-line-001.md \
  --cases fixtures/cases/fault-management-cases.jsonl \
  --manifest fixtures/manifests/fault-management.json \
  --version v0.1.0 \
  --out aop.json

python3 -m aop_toolkit lint aop.json
```

Use the current repository README and CLI help for exact flags and environment requirements; the commands above reflect the documented reference walkthrough, not a guarantee about every released package version.

### 6.3 Worked example: line fault management

The AOP Toolkit contains a concrete example:
- Source SOP: `fixtures/sop/rb-line-001.md`
- Observed cases: `fixtures/cases/fault-management-cases.jsonl` (40 cases)
- Governance manifest: `fixtures/manifests/fault-management.json`
- Toolkit: [aop-toolkit](https://github.com/agentic-operating-procedure/aop-toolkit)

The SOP objective is to restore a reported line fault within the maintenance window while minimizing customer impact. Its steps include alarm correlation, loopback testing, fault resolution, field-crew dispatch and planning notification.

The example demonstrates why a direct SOP-to-agent conversion is unsafe:
- The observed case corpus provides evidence of variants and actual execution paths.
- The governance manifest distinguishes autonomous, approval-required and prohibited actions.
- Dispatch may require supervisor approval under specified conditions.
- Network configuration changes and direct customer contact are prohibited in the example.
- Context elements have declared sources, trust classes and access rules.
- The AOP includes hand-offs, validation obligations, intervention and drift obligations.

The example is a worked reference, not an assertion that its rules are suitable for another enterprise or domain. A real transformation must replace the fixture SOP, case corpus, context, decision rules, authorities, risk assessments and measures with approved enterprise-specific evidence.

### 6.4 How to run the worked example as an enterprise exercise

1. Select a real, bounded operational procedure and its accountable owner.
2. Confirm the SOP version, approval state, scope, exclusions and intended outcomes.
3. Collect representative cases, including normal, exceptional, failed, escalated and manually overridden work.
4. Declare the observation surface, data minimization, access, privacy, retention and provenance rules before collecting evidence.
5. Stitch cases into an operational context graph; preserve uncertainty and conflicting assertions.
6. Mine variants and decision patterns. Review mined rules with the people who own the work.
7. Create a governance manifest that explicitly classifies each decision and action as permitted, approval-required, prohibited or unresolved.
8. Compile and lint the AOP; resolve missing process/catalog mappings as explicit gaps rather than inventing canonical records.
9. Run AOP document conformance and harness conformance, including negative and adversarial tests.
10. Execute in a controlled environment with human approvals and real enforcement outside the model context.
11. Compare verified outcomes against the baseline and feed drift, exceptions and new variants into controlled AOP revision.

## 7. Worked example: refactoring a software-backed service

Use the fault-management scenario to demonstrate how OpenDEA and AOP work together. The purpose is to teach the architecture method, not to prescribe a specific telco architecture.

### 7.1 Start with the business outcome

Outcome: restore affected service within the required maintenance window while minimizing customer impact.

Identify:
- affected stakeholder and customer segment;
- business capability responsible for service assurance;
- business process that handles fault resolution;
- business service promise and service-level conditions;
- operational measures such as restoration time, first-time resolution, repeat fault rate and customer impact.

The Business Process Catalog provides the process semantics and decomposition. The Business Capability Catalog provides the durable business ability. The business service definition remains distinct from the information-system service contracts that support it.

### 7.2 Discover the current software realization

Model the actual systems and their responsibilities rather than inferring architecture from application names.

| Observed responsibility | OpenDEA modeling concern | Questions for the architect |
|---|---|---|
| Alarm correlation | InformationSystemFunction, InformationSystemComponent | Which system performs correlation? Which component owns the behaviour? What data and events does it consume? |
| Loopback testing | InformationSystemFunction, InformationSystemService, IntegrationInterface | Is testing a function inside a system, a service offered to another consumer, or both through separate records? |
| Fault ticket management | InformationSystemService and component | What service contract is offered to operators and agents? What is the system of record? |
| Crew dispatch | Business process, InformationSystemService, IntegrationInterface | Which business authority can request dispatch? What external side effect occurs? |
| Planning notification | InformationSystemService and interface | What contract and acknowledgement prove the planning system received the notification? |
| Network restoration | InformationSystemFunction and operational outcome | What system evidence proves restoration rather than merely recording a completed task? |

The same software product may host multiple components and functions. A component may provide multiple services. A service may be exposed through multiple interfaces. Model these relationships explicitly; do not assume a one-to-one mapping.

### 7.3 Design the agentic realization

The target may retain the existing systems of record while changing the way work is coordinated:

- AOP governs the fault-management work and its eight dimensions.
- The harness enforces the approved action and authority rules.
- Agents interpret the case, correlate evidence, select permitted diagnostic skills and propose next actions.
- Existing information-system services remain the means of accessing alarm, testing, ticketing, dispatch and planning capabilities.
- Human supervisors approve actions when required and retain the authority to pause, terminate or redirect work.
- The execution record links the AOP version, context snapshot, agent/model/tool versions, authority decisions, service calls, acknowledgements and verified outcome.

The agent does not replace every system function. It may coordinate existing functions and services through governed interfaces, while some functions remain deterministic software and some decisions remain human-owned.

### 7.4 Decide what to refactor

Refactoring options should be evaluated against the model and evidence:

- **Retain:** existing system function and service already satisfy the target contract and assurance needs.
- **Wrap:** expose a stable service contract around a legacy function without changing its internals.
- **Refactor:** change component boundaries or internal implementation to improve reliability, observability, security or modularity.
- **Extract:** separate a cohesive function into an independently governed component or service where there is a clear ownership and operational reason.
- **Replace:** retire an implementation only when the target capability and service contract can be preserved and migration risk is controlled.
- **Agent-enable:** make a function or service safely consumable by an agent through scoped interfaces, context contracts, policy enforcement and audit.
- **Human-retain:** explicitly preserve human execution or decision-making where risk, regulation, ambiguity or stakeholder impact requires it.

The decision must be based on service quality, coupling, data ownership, change frequency, risk, economics and target operating requirements, not on a blanket preference for microservices or agents.

## 8. Methodology for refactoring traditional software and service-delivery architecture

### Phase A — Establish the enterprise architecture baseline

**Objective:** understand the enterprise and its current service delivery system before choosing a target.

Activities:
- identify strategic outcomes, value streams, capabilities and accountable owners;
- inventory business processes and controlled SOPs;
- inventory business services, information-system services, system functions, components, interfaces and systems;
- map data, events, dependencies, contracts and operational controls;
- discover actual runtime interactions, queues, manual hand-offs and workarounds;
- identify architecture assertions and evidence sources, distinguishing approved model from observed state.

Deliverables:
- scoped OpenDEA model and stakeholder viewpoints;
- current-state process/service/system maps;
- dependency and integration graph;
- evidence register and confidence gaps;
- prioritized architecture questions.

Exit condition: the enterprise can trace the selected outcome to the processes, services, systems and responsibilities that currently realize it.

### Phase B — Observe and reconstruct actual work

**Objective:** reconcile documented procedure with actual execution.

Activities:
- select representative work cases;
- establish lawful and proportionate observation;
- capture task, step, actor, application, decision, exception, escalation and outcome evidence;
- stitch cases and identify variants;
- compare observed work with SOPs and process catalog records;
- identify undocumented work, control bypasses and data-quality gaps.

Deliverables:
- case corpus and provenance;
- context graph;
- variant and exception analysis;
- SOP-to-observed-work gap report.

Exit condition: process owners validate the observed work model and its known limitations.

### Phase C — Design the target operating model and AOPs

**Objective:** specify how work should be performed under agentic conditions.

Activities:
- decide which tasks are human-led, agent-assisted, agent-executed or prohibited;
- define decision rights, authority classes, approvals and escalation;
- define the eight AOP dimensions;
- bind required skills, information-system services and tools;
- define coordination, conflict, recovery, verification and audit obligations;
- define human-agent and agent-agent trust requirements.

Deliverables:
- approved target operating model;
- AOPs and governance manifests;
- skills and harness requirements;
- authority and trust model;
- conformance and scenario test plan.

Exit condition: each AOP is traceable to an approved work scope and has explicit constraints, authority and assurance obligations.

### Phase D — Design target software and service architecture

**Objective:** determine what software and service changes are necessary to support the target operating model.

Activities:
- map each required action to existing or proposed InformationSystemFunction records;
- map execution responsibilities to InformationSystemComponent records;
- define InformationSystemService contracts and consumers;
- define IntegrationInterface and API/event/file/stream contracts;
- determine data/context access, provenance and freshness requirements;
- identify synchronous, asynchronous, event-driven and human-mediated interactions;
- evaluate modularization, extraction, wrapping, replacement and agent-enablement options;
- design service ownership, SLOs, security boundaries and operational support.

Deliverables:
- target OpenDEA model;
- service and interface contracts;
- component and deployment architecture;
- integration and context architecture;
- architecture decision records and refactoring backlog.

Exit condition: each target service/function has an owner, consumer, contract, implementation strategy, security policy and verification method.

### Phase E — Engineer, integrate and assure

**Objective:** implement the target increment without losing control of existing operations.

Activities:
- build or adapt service interfaces and system functions;
- implement harness and external enforcement controls;
- integrate identity, model authority, agent registry, tools and policy decision points;
- run AOP and service contract conformance;
- test normal, exceptional, adversarial, failure and recovery scenarios;
- verify end-to-end traceability and evidence integrity.

Deliverables:
- versioned implementation and deployment artefacts;
- automated integration and assurance pipeline;
- verified run and action evidence;
- operational runbooks and rollback plan.

Exit condition: the increment passes its technical, operational, security and governance acceptance criteria in a controlled environment.

### Phase F — Transition, operate and continuously improve

**Objective:** move work safely to the new operating model and sustain performance.

Activities:
- progressive release and workload migration;
- monitor service quality, AOP drift, exceptions, control effectiveness and agent behaviour;
- maintain human intervention and rollback capability;
- reassess models, agents, skills, tools, procedures and dependencies after material change;
- compare operational and business outcomes to baseline;
- retire redundant components only after dependencies and service obligations are satisfied.

Deliverables:
- transition and decommission records;
- service and operating dashboards;
- outcome and value reports;
- updated architecture and AOP versions;
- continuous improvement backlog.

Exit condition: the target operating model is stable, owned, measurable and demonstrably delivering its intended outcomes.

## 9. Traditional architecture patterns: what changes and what remains

| Traditional architecture concern | Agentic Operations-era treatment |
|---|---|
| Application portfolio | Model systems, components, functions and ownership; add agent/harness/runtime dependencies without losing existing system-of-record boundaries |
| Business process | Retain business purpose and outcome; discover actual variants; specify governed execution in AOP where suitable |
| Service-oriented architecture | Preserve consumer-facing contracts; distinguish business services from information-system services and their interfaces |
| API-led integration | Keep APIs as one interface type; include events, streams, files and human-mediated interaction boundaries where relevant |
| Workflow/BPM engines | Retain deterministic orchestration where valuable; use AOP for governed, context-sensitive execution and explicit authority |
| Microservices | Use only where cohesive responsibility, independent lifecycle, scale or ownership justifies service decomposition |
| Rules engines | Retain deterministic policy and decision logic where appropriate; make decision authority, provenance and human override explicit |
| ESB/iPaaS | Preserve integration controls and system connectivity; add scoped agent access, context minimization and auditable invocation |
| RPA | Reassess fragile UI automation; prefer supported service contracts and controlled interfaces, retaining UI automation only where justified |
| Data platforms and knowledge graphs | Distinguish authoritative data, observed state, assertions, derived knowledge and evidence; preserve lineage and freshness |
| Human operations | Make human decision rights, escalation, intervention, collaboration and accountability explicit in the operating design |
| Monitoring and observability | Extend service telemetry with AOP run/action evidence, policy decisions, approvals, model/tool versions and verified outcomes |

Agentic Operations does not make all traditional architecture patterns obsolete. It changes their role, relationships and governance requirements.

## 10. Trust, authority and human-agent service delivery

The target architecture must enforce:
- workload and agent identity, provenance and version binding;
- least-privilege access to information-system services and tools;
- authority independent of the agent's own reasoning context;
- action-scoped and time-bounded delegation;
- approval-gated high-impact and irreversible actions;
- context provenance, minimization and freshness;
- fail-closed behavior when policy, context or authority is unknown;
- conflict arbitration for multi-agent coordination and shared resources;
- emergency stop, revocation, rollback and recovery;
- tamper-evident evidence and replay;
- accountable human ownership of business outcomes.

Co-opetition may be used to compare alternative proposals or strategies. It must not permit competing agents to seize permissions, interfere with shared workloads, conceal evidence or perform conflicting side effects. Proposal generation, arbitration and execution authority remain separate.

## 11. Evidence and success measures

Every transformation increment should establish a baseline and measure outcomes at multiple levels.

| Level | Example measures |
|---|---|
| Stakeholder | Service experience, resolution quality, accessibility, trust and satisfaction |
| Business | Revenue, retention, cost-to-serve, working capital, risk-adjusted margin |
| Value stream | End-to-end lead time, throughput, first-time-right, rework, exception rate |
| Service | Availability, latency, error rate, recovery time, contract compliance |
| Agentic execution | AOP conformance, run success, unauthorized action attempts, escalation and intervention rates |
| Trust and governance | Approval quality, policy violations, audit completeness, revocation effectiveness |
| Workforce | Human workload, cognitive burden, hand-off quality, override quality and employee experience |
| Economics | Total cost per verified outcome, including model, service, infrastructure, integration, oversight and assurance costs |

Do not use agent count, task volume, token consumption or automation percentage as stand-alone evidence of transformation success.

## 12. Recommended programme sequence for Agentic-Operation

This playbook should guide a sequenced programme of separately scoped work packages.

| Sequence | Work package | Proposed output | Dependency / boundary |
|---:|---|---|---|
| 0 | AO-ATP-001 review and adoption | Agreed enterprise architecture transformation method | This document; non-normative |
| 1 | Reference worked-example integration | One complete SOP → observed work → OpenDEA model → AOP → harness → outcome evidence walkthrough | Use AOP's fault-management fixture; do not fork AOP normative artefacts |
| 2 | Enterprise architecture refactoring method | Model-first current/target/transition architecture method using OpenDEA concepts | Integrate by reference to OpenDEA; semantic changes belong in OpenDEA governance |
| 3 | Agentic service-delivery reference architecture | Reference patterns for agent-enabled business services and information-system services | AOP runtime and trust contracts remain AOP-owned |
| 4 | Human-agent trust and authority framework | Enterprise decision rights, delegation, co-opetition, oversight and accountability patterns | Align with AO-OAR-001 and AOP normative security model |
| 5 | Integrated assurance and operational engineering plan | Deployment, security, observability, resilience, conformance and support plan | Address AO-OAR-001 findings |
| 6 | Enterprise transformation assessment and value method | Baselines, capability/service/process assessments, benefit and risk evidence | Reuse relevant OpenDEA assessment contracts; avoid inventing a new maturity model without approval |
| 7 | Practitioner enablement and adoption assets | Role-based playbooks, worked examples, templates, tooling guide and training | Enterprise, architecture, engineering, operations and assurance personas |

### 12.1 First implementation scenario

Use the AOP fault-management example as the first shared worked scenario because it already has a source SOP, a 40-case corpus, a governance manifest and a documented toolkit pipeline.

Extend the exercise with an OpenDEA architecture model that links:
- the enterprise outcome and stakeholder;
- business capability and business process;
- business service and its consumers;
- systems and information-system functions;
- information-system components and services;
- integration interfaces and data/context dependencies;
- AOP, skills, harness, agents, model and tool bindings;
- operational evidence, measures and verified outcome.

The worked example should make missing or unverified catalog mappings explicit. It must not manufacture canonical OpenDEA entities or silently change OpenDEA identifiers.

### 12.2 Suggested practitioner entry points

| Persona | First question | Start with |
|---|---|---|
| Board / executive sponsor | Which outcomes and risks justify changing the operating model? | Outcome baseline, AO-CBC-001, AO-OAR-001 and transformation stages |
| Chief operating officer / process owner | Which work should be redesigned, and what must remain accountable to people? | SOP observation, process catalog and AOP method |
| Enterprise architect | What is the current and target enterprise model? | OpenDEA architecture framework, metamodel, capabilities, processes and reference architecture |
| Solution / software architect | Which functions, components, services and interfaces need to change? | OpenDEA Information Systems Semantic Architecture and service/function catalogs |
| Operations / service leader | How will the new operating model be run, supported and recovered? | AOP harness, service SLOs, runbooks and AO-OAR-001 |
| AI / agent engineer | How are agents provisioned, discovered, constrained and verified? | Spec-443/444/445, model authority, AOP toolkit, harness and conformance |
| Risk / security / compliance | What authority and trust evidence makes the work acceptable? | AOP security clauses, enterprise trust model, approval and audit evidence |
| Transformation / value lead | How will the enterprise prove benefits and avoid activity-based claims? | Baseline, outcome hierarchy and assessment/value evidence |

## 13. Governance and ownership boundaries

| Concern | Authority |
|---|---|
| Agentic Operations enterprise operating model, transformation guidance and enterprise outcome assurance | Agentic-Operation |
| AI Agent Profile, Bootstrap, Card and Model Management Authority | Agentic-Operation |
| AOP discipline, conceptual hierarchy, normative model, schemas and clauses | AOP programme |
| AOP toolkit, context graph, reference harness, registry and conformance | AOP programme |
| OpenDEA architecture layers, semantic metamodel, entity definitions and relationships | OpenDEA / TechNeHub Labs |
| OpenDEA catalog records, allocation and conformance | Owning OpenDEA catalog repositories |
| Enterprise adoption and cross-programme integration | Agentic-Operation, in agreement with the relevant authority owners |

This playbook does not:
- redefine OpenDEA entities or relationships;
- declare an OpenDEA CR implemented based solely on a catalog README;
- change AOP's six-level conceptual hierarchy or eight dimensions;
- reproduce AOP normative security or execution clauses as Agentic-Operation standards;
- make the current reference services production-ready;
- prescribe microservices, agent frameworks or vendor products as universal answers;
- declare the five Agentic Operations transformation stages to be a maturity scoring model.

Where the enterprise method identifies a semantic gap, raise it with the relevant OpenDEA authority. Where it identifies an AOP normative gap, raise it through AOP governance. Agentic-Operation should own the enterprise integration, guidance, adoption and outcome-assurance view.

## 14. Conclusion

The central transformation is not from applications to agents. It is from an enterprise whose work, services and systems are predominantly designed around fixed execution paths to an enterprise that can deliberately coordinate human and non-human capabilities within explicit intent, semantic context, authority, constraints and assurance.

OpenDEA helps the enterprise understand what it is, what it does, which systems and services realize its capabilities, and how those elements relate and change. AOP specifies how selected work should be performed and assured under agentic conditions. Agentic-Operation connects those foundations to enterprise governance, AI Agent management, service delivery and measurable business outcomes.

The recommended first step is a single end-to-end worked example that demonstrates both transformations together: model the business outcome and current software/service architecture in OpenDEA; observe actual work; transform the SOP into an AOP using the AOP toolchain; execute under a bounded harness; and trace the verified result back to service and enterprise outcomes.

Only after that complete path is understood and evidenced should the organization scale the methodology across additional value streams and architecture domains.
