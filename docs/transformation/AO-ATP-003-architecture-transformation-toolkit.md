# AO-ATP-003 — Architecture Transformation Toolkit

| Field | Value |
|---|---|
| Identifier | AO-ATP-003 |
| Title | Architecture Transformation Toolkit |
| Version | 0.1.0 |
| Status | Proposed practitioner guidance |
| Authority | Agentic-Operation |
| Classification | Non-normative methods, decision and reference toolkit |
| Parent guidance | [AO-ATP-001](../transformation/AO-ATP-001-enterprise-architecture-and-service-delivery-transformation-playbook.md) |
| Integration register | [AO-ATP-002](../transformation/AO-ATP-002-cross-programme-integration-and-dependency-register.md) |
| Initial worked example | [AO-WE-001](../examples/AO-WE-001-fault-management-opendea-aop-worked-example.md) |
| Toolkit home | [Architecture Transformation Toolkit](../toolkit/architecture-transformation/README.md) |

## 1. Purpose

AO-ATP-003 operationalizes the transformation direction established by AO-ATP-001. It provides reusable practitioner instruments, decision frameworks, transformation patterns, method-selection guidance and templates for analysing, designing, sequencing and assuring changes to enterprise work, software architecture and service delivery in the context of Agentic Operations.

It is an instrumentation and practitioner-enablement layer. It does not replace the playbook, establish a new enterprise metamodel, prescribe a universal target architecture, or assert that agentic execution is preferable for every kind of work.

## 2. The transformation question

> **How must we redesign the enterprise's work, services, systems, decision rights and human-agent relationships so that business outcomes can be realized through governed, model-grounded and continuously assured coordination of human and non-human capabilities?**

The outcome is the design constraint. Technology, automation, agents, APIs, service decomposition and platform choices are means to be evaluated against it, not ends in themselves.

## 3. Relationship to existing programme assets

| Asset | Responsibility | AO-ATP-003 relationship |
|---|---|---|
| AO-ATP-001 | Strategic and architectural transformation playbook, principles and lifecycle | Parent method; toolkit instruments make its guidance actionable |
| AO-ATP-002 | Cross-programme dependencies, evidence and integration reconciliation | Supplies dependency and authority boundaries; this toolkit does not remediate upstream issues |
| AO-OAR-001 | Operational assurance review | Related assurance baseline; not replaced by transformation-specific verification |
| AO-WE-001 | Fault-management OpenDEA–AOP worked example | Initial application context and source of known gaps; not claimed as validated production architecture |
| OpenDEA | Canonical enterprise and information-systems semantics | Referenced by canonical identity, version and typed relationship; not redefined here |
| AOP programme | Normative operational specification, toolchain and runtime discipline | Referenced through its current contracts and versions; not duplicated or modified here |

This document and its supporting toolkit are owned by Agentic-Operation. Upstream repositories retain authority over their own schemas, catalogues, procedures, tools and release processes.

## 4. Scope

The toolkit supports transformation of:
- enterprise capabilities, value streams, business processes and business services;
- software systems, components, functions, information-system services and integration interfaces;
- data, information, events, context and evidence flows;
- human work, deterministic automation and agent-assisted or agent-executed work;
- service-delivery models, decision rights, controls and operational responsibilities;
- transition architectures and the assurance of transformation increments.

It is suitable for legacy, monolithic, modular, distributed, service-oriented, event-driven, cloud, hybrid and agentic environments. It does not assume that a particular architecture style is the desired destination.

## 5. Out of scope

This toolkit does not:
- amend OpenDEA or AOP normative definitions, schemas, catalogues or implementation;
- create canonical enterprise entities or claim authority over upstream records;
- prescribe a vendor, agent framework, model, cloud or software stack;
- mandate microservices, event-driven architecture, agentization or wholesale replacement;
- provide a universal maturity score, risk score, weighting scheme or business case formula;
- certify production readiness or business value;
- substitute for legal, security, safety, privacy, regulatory or domain-owner approval;
- claim AO-WE-001 fixture data represents independently verified production evidence.

## 6. Transformation lifecycle

Use the lifecycle as an iterative navigation model, not a mandatory waterfall. Revisit earlier phases when evidence, constraints or outcomes change.

1. **Frame intent and outcomes.** Establish the stakeholder, outcome, value-stream boundary, constraints, accountable owner and measures.
2. **Discover the current state.** Reconstruct documented and observed work, capabilities, processes, services, systems, components, interfaces, data and dependencies.
3. **Diagnose constraints and opportunities.** Separate verified facts from hypotheses; identify outcome gaps, coupling, hand-offs, authority issues, risk and evidence deficiencies.
4. **Decide the target disposition.** Decide what work and architecture to retain, redesign, automate, agent-enable, refactor, extract, replace, retire or leave unresolved.
5. **Design transition architecture.** Define target and intermediate states, contracts, coexistence, migration increments, dependencies and rollback.
6. **Engineer and integrate.** Implement bounded changes, controls, service contracts, AOP/harness bindings and operational capabilities.
7. **Verify and assure.** Test semantic, functional, service, integration, authority, security, resilience and operational properties.
8. **Transition, measure and evolve.** Move work safely, compare outcomes with baseline, manage drift and feed evidence into controlled revision.

Each phase should produce explicit outputs and decisions. A phase is not complete merely because a document or diagram exists.

## 7. Instrument groups

The toolkit is organized into six groups:

| Group | Practitioner question | Principal outputs |
|---|---|---|
| Discovery and baseline | What exists, what happens, and what evidence supports the description? | Outcome frame, architecture inventory, work model, evidence register |
| Diagnosis and analysis | What prevents the required outcome, and why? | Gap analysis, dependency and coupling analysis, constraints |
| Target architecture decisions | What should change, remain, or be delegated, and on what grounds? | Work and architecture dispositions, decision records |
| Transformation and refactoring | How can the target be reached safely? | Pattern selection, transition architecture, transformation backlog |
| Verification and assurance | What evidence demonstrates correctness and readiness? | Verification plan, test evidence, acceptance decision |
| Transformation management | How are decisions, dependencies and increments governed? | ADRs, ownership, traceability, change and acceptance records |

The detailed instrument catalogue is maintained in the [instrument catalogue](../toolkit/architecture-transformation/instrument-catalogue.md).

## 8. Decision discipline

Two decisions must remain distinct:

### 8.1 Work disposition

A work unit may be human-owned, human-assisted, agent-assisted, agent-executed under bounded authority, deterministic automation, redesigned, eliminated or unresolved. These describe how work should be performed and governed.

### 8.2 Architecture realization disposition

A system or architecture responsibility may be retained, wrapped, refactored, modularized, extracted, integrated, agent-enabled, replaced, retired or newly introduced. These describe how the technical realization should evolve.

Do not infer one disposition from the other. Agent-executed work does not automatically require microservices; a service may be agent-enabled without changing its implementation; deterministic automation may be the correct target for stable rules.

Use the [decision frameworks](../toolkit/architecture-transformation/decision-frameworks.md) and record material decisions with evidence, alternatives, rationale, risks, owner and review conditions.

## 9. Transformation patterns

Patterns are reusable design guidance, not recipes. Their applicability depends on context, constraints, service contracts, authority, operational capability and evidence.

The initial pattern set is:
- Legacy Service Agent Enablement;
- Human Approval Boundary;
- Deterministic Core with Agentic Coordination;
- Exception-Driven Agentic Operations.

See [transformation patterns](../toolkit/architecture-transformation/transformation-patterns.md). Further patterns should be added from reviewed applications, not by speculative catalogue expansion.

## 10. Methods and tools

Select methods and tools according to the question, available evidence, domain and decision consequence. The toolkit describes method families and tool categories, their inputs, outputs, limitations and lifecycle fit in [methods and tools](../toolkit/architecture-transformation/methods-and-tools.md).

Tool output is evidence with a scope and limitation, not automatic semantic truth. Process-mining output does not by itself establish approved business semantics; an application inventory does not prove runtime behaviour; static analysis does not establish business value; a passing test does not prove production readiness.

## 11. Evidence and integrity rules

Every material architecture assertion and transformation decision should be classified sufficiently to distinguish:
- observed fact;
- approved or normative model;
- repository-declared assertion;
- inferred relationship;
- practitioner hypothesis;
- proposed target;
- unresolved gap;
- verified test result;
- operational observation;
- measured outcome.

Where relevant, record source, source version or commit, observation date, owner, scope, confidence/limitation and canonical identifier. Preserve conflicting evidence rather than silently resolving it. A missing canonical mapping remains a visible gap; do not invent an entity or identifier.

Keep fixture, simulated, test, pilot and live operational evidence distinct. Do not promote claims beyond what the evidence establishes.

## 12. Assurance and acceptance

Verification should address the relevant dimensions of semantic integrity, work integrity, service contracts, functional correctness, integration, agent authority, human authority, security and trust, resilience, transition readiness and outcome realization.

Use the assurance gates as decision points:
1. intent and scope accepted;
2. current-state baseline sufficiently evidenced;
3. target and transition decisions justified;
4. engineering and contract tests passed;
5. operational controls and readiness demonstrated;
6. intended outcomes measured against an appropriate baseline.

These are practitioner guidance gates, not a new normative assurance standard or compulsory delivery methodology. Acceptance must be made by the accountable authority using evidence appropriate to the consequence.

## 13. Applying the toolkit to AO-WE-001

AO-WE-001 is the initial reference application. It provides a fault-management context in which to exercise outcome framing, work discovery, architecture inventory, dependency analysis, authority assessment, work and architecture disposition, transition planning and verification.

The existing worked example records unresolved process mappings, proposed or planned catalogue records, incomplete service bindings, AOP authority and skill issues, fixture data-quality defects and absent end-to-end enterprise outcome evidence. AO-ATP-003 does not close those issues. It provides the instruments with which a subsequent application can assess them consistently.

The initial application should therefore:
- preserve the fixture classification and known data-quality limitations;
- resolve canonical OpenDEA identities and lifecycle states from current upstream sources;
- distinguish business process, business service, system function, component, information-system service and interface;
- evaluate each work unit independently for human, deterministic and agentic disposition;
- evaluate each software responsibility independently for retain/wrap/refactor/extract/agent-enable/replace decisions;
- retain unresolved authority, skill, metric and integration gaps as explicit decisions or dependencies;
- require reproducible test, approval, service-invocation and outcome evidence before claiming an executable integrated reference.

## 14. Practitioner workflow

1. Read AO-ATP-001 to understand the transformation intent and architecture principles.
2. Read AO-ATP-002 to understand known cross-programme dependencies and authority boundaries.
3. Select a bounded value stream and accountable owner.
4. Complete the Transformation Intent Brief.
5. Build the discovery and evidence register before making target-state claims.
6. Select only the instruments needed to resolve the actual questions; document omissions and rationale.
7. Record work and architecture dispositions separately.
8. Compare alternatives and record material decisions.
9. Define transition increments, dependencies, controls, verification and acceptance.
10. Obtain approval from the relevant business, architecture, operational, security and risk authorities.
11. Execute a bounded increment and retain reproducible evidence.
12. Review outcomes and revise the model and plan through controlled governance.

## 15. Maintenance and evolution

AO-ATP-003 is proposed practitioner guidance. Changes to this toolkit should be managed through the Agentic-Operation repository's change governance. Pattern and instrument additions should identify the problem addressed, evidence from application, limitations and relationship to existing material.

Do not change upstream OpenDEA or AOP assets through this repository. Raise changes with their respective owners and record the dependency in AO-ATP-002 where material.

## 16. Related resources

- [AO-ATP-001 — Enterprise Architecture and Service Delivery Transformation Playbook](./AO-ATP-001-enterprise-architecture-and-service-delivery-transformation-playbook.md)
- [AO-ATP-002 — Cross-Programme Integration and Dependency Register](./AO-ATP-002-cross-programme-integration-and-dependency-register.md)
- [AO-OAR-001 — Operational Assurance Review](../assurance/AO-OAR-001-operational-assurance-review.md)
- [AO-CBC-001 — Conceptual Baseline](../architecture/AO-CBC-001-conceptual-baseline.md)
- [AO-WE-001 — Fault Management OpenDEA–AOP Worked Example](../examples/AO-WE-001-fault-management-opendea-aop-worked-example.md)
- [Architecture Transformation Toolkit](../toolkit/architecture-transformation/README.md)
