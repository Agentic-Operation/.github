# Architecture Transformation Methods and Tools

This guide helps practitioners select methods and tool categories for a defined transformation question. It does not endorse a vendor or prescribe a single toolchain.

## 1. Selection principles

1. Start with the decision or uncertainty, not a preferred tool.
2. Establish the required input data, permissions and evidence quality.
3. Understand what the method can and cannot establish.
4. Triangulate important findings with independent sources.
5. Preserve provenance, version and scope of generated evidence.
6. Do not equate tool output with approved business semantics or architecture truth.
7. Consider privacy, security, retention, access and operational impact before collecting data.

## 2. Method selection by question

| Practitioner question | Candidate methods | Useful outputs | Important limitations |
|---|---|---|---|
| What outcome and value are required? | Outcome framing, stakeholder analysis, capability mapping, value-stream mapping | Outcome frame, capability contribution, scope | Maps and interviews do not prove causal value |
| How does work actually happen? | Process discovery, case analysis, observation, process mining | Variants, hand-offs, bottlenecks, exceptions | Event logs may be incomplete, biased or semantically weak |
| What responsibilities do systems realize? | Architecture inventory, source analysis, runtime observation, responsibility mapping | System/component/function inventory | Names and static repositories do not prove deployed runtime responsibility |
| Where is coupling constraining change? | Static dependency analysis, runtime tracing, change coupling, cohesion analysis | Dependency graph and coupling hypotheses | Metrics are context-sensitive and do not alone justify service extraction |
| What should service boundaries be? | Domain-driven design, bounded-context analysis, service design, contract analysis | Responsibility boundaries and service contracts | Bounded contexts require domain validation; they are not automatically deployment units |
| How should legacy capability be preserved? | Strangler transition, facade/wrapper, modularization, parallel operation | Migration options and coexistence design | Introduces routing, data consistency and operational complexity |
| Should work be agent-executed? | Work decomposition, delegation analysis, authority and risk analysis | Work disposition and controls | Model capability alone does not establish safe delegation |
| How should agents consume services? | AOP design, harness design, API/contract design, least-privilege analysis | Governed execution and interface requirements | Agent instructions are not enforcement controls |
| How can target behaviour be tested? | Contract tests, scenario tests, property tests, negative tests, simulation, replay | Reproducible verification evidence | Passing tests cover only defined conditions and environments |
| How can outcomes be verified? | Baseline measurement, operational telemetry, service-level analysis, causal evaluation where feasible | Outcome comparison and limitations | Attribution may be confounded; activity metrics are not outcome proof |

## 3. Tool categories

### 3.1 Enterprise architecture and semantic modelling
**Use for:** canonical entity identity, typed relationships, architecture views, ownership, impact analysis and model conformance.

**Inputs:** metamodel, catalogues, root model, architecture assertions and versions.

**Outputs:** linked architecture model, allocations, dependency views and validation results.

**Limitations:** repository population and model conformance do not prove deployment or runtime truth. Use canonical upstream semantics rather than inventing local equivalents.

### 3.2 Process modelling and process-mining tools
**Use for:** documenting intended work, discovering observed execution paths, variants, wait times and rework.

**Inputs:** controlled process models, event logs, case identifiers, timestamps and domain interpretation.

**Outputs:** process models, variants, performance analysis and exception candidates.

**Limitations:** event-log quality, missing events, case stitching and selection bias can materially distort findings. Process owners must validate business meaning.

### 3.3 Software architecture discovery and static analysis
**Use for:** code dependency, module structure, call graph, change coupling, complexity and candidate responsibility boundaries.

**Inputs:** source code, build metadata, dependency manifests and repository history.

**Outputs:** dependency graphs, static findings and refactoring hypotheses.

**Limitations:** static analysis may miss runtime configuration, dynamic calls, external dependencies and business semantics.

### 3.4 Runtime observability and distributed tracing
**Use for:** actual service calls, latency, failure paths, traffic, dependency behaviour and operational bottlenecks.

**Inputs:** instrumentation, traces, logs, metrics, correlation IDs and access controls.

**Outputs:** runtime dependency evidence and operational profiles.

**Limitations:** telemetry may be sampled, incomplete or affected by instrumentation gaps. Collection must be proportionate and privacy-aware.

### 3.5 API, event and contract tooling
**Use for:** interface schemas, compatibility, consumer/provider expectations, event evolution and contract testing.

**Inputs:** API specifications, schemas, event definitions, version policy and consumer inventory.

**Outputs:** contract artefacts, compatibility checks and test results.

**Limitations:** a valid contract does not prove that a provider is deployed, available or semantically fit for a business purpose.

### 3.6 Data lineage and context tooling
**Use for:** source-of-truth analysis, lineage, freshness, provenance, access and context quality.

**Inputs:** data catalogues, lineage metadata, ownership and policy.

**Outputs:** data-flow maps, lineage evidence and context contracts.

**Limitations:** lineage may be partial; discoverability does not imply permission or authority.

### 3.7 AOP and agent engineering toolchains
**Use for:** operational specification, skills, context graph, compilation, linting, registry, harness execution and conformance.

**Inputs:** approved SOP/work evidence, AOP specification, governance manifest, skills, tool contracts and authority model.

**Outputs:** versioned AOP artefacts, conformance results, execution evidence and replay records.

**Limitations:** follow current AOP programme documentation and release versions. Agentic-Operation does not redefine AOP normative contracts. Compilation or conformance does not prove business outcomes.

### 3.8 Testing, simulation and digital-twin tools
**Use for:** scenario exploration, what-if analysis, failure injection, control testing and behaviour evaluation.

**Inputs:** explicit model assumptions, scenarios, state, rules, data and validation targets.

**Outputs:** scenario results, sensitivity findings and test evidence.

**Limitations:** simulation validity depends on model fidelity, calibration and scope. A simulated outcome is not live operational evidence.

### 3.9 CI/CD, governance and evidence systems
**Use for:** automated checks, traceable changes, versioning, approvals, deployment evidence and audit records.

**Inputs:** source, policies, tests, identities, approvals and release metadata.

**Outputs:** build/test results, change history, attestations and deployment records.

**Limitations:** a green pipeline proves only the checks actually executed and configured.

## 4. Tool evaluation checklist

Before selecting a tool, ask:
- Does it address a defined decision or evidence gap?
- Are inputs accessible, lawful, sufficiently complete and trustworthy?
- Can output be versioned and traced to source?
- Does it integrate with canonical architecture identities?
- What assumptions and blind spots does it introduce?
- Can results be independently checked?
- Does it expose sensitive information or create new operational risk?
- Who owns the tool, configuration, data and output?
- What happens if it becomes unavailable or changes version?
- What is the total cost of adoption and operation?

## 5. Method and tool mapping across the lifecycle

| Lifecycle phase | Common methods/tools |
|---|---|
| Frame intent | Stakeholder analysis, outcome mapping, capability mapping |
| Discover | Process discovery, architecture repository, code analysis, telemetry, data lineage |
| Diagnose | Process mining, dependency analysis, risk and authority assessment |
| Decide target | Domain analysis, service design, delegation analysis, ADRs |
| Plan transition | Strangler/modularization planning, dependency sequencing, migration modelling |
| Engineer | Contract tooling, AOP toolchain, CI/CD, policy enforcement, observability |
| Verify | Conformance, contract tests, scenario tests, simulation, replay, human intervention tests |
| Operate and evolve | Telemetry, outcome measurement, drift analysis, governance and controlled revision |

## 6. Methodological cautions

- Process-mining output is not automatically approved business semantics.
- An application inventory is not a complete architecture.
- A static dependency graph is not a full runtime dependency model.
- Microservices are not the default target.
- Agentization is not inherently superior to deterministic automation.
- A model-generated recommendation is not an approved architecture decision.
- A successful test is not production operational evidence.
- Agent deployment counts are not business outcome measures.
- A diagram is not a verified architecture.
- A proposed target is not an implementation commitment.
- Tool availability does not confer authority to access data or execute actions.
