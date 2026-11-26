# Agentic Operations: Conceptual Baseline and Cross-Programme Boundary Contract

| Field | Value |
|---|---|
| Document ID | AO-CBC-001 |
| Version | 0.1.0 |
| Status | Draft for Review |
| Authority | Agentic-Operation |
| Related programme | agentic-operating-procedure |
| Scope | Enterprise operating model, programme boundaries and integration contracts |

## 1. Purpose

This document establishes the conceptual baseline for Agentic Operations as an enterprise operating model and defines its relationship with the Agentic Operating Procedure (AOP) programme and the AI Agent management standards maintained by Agentic-Operation.

It is a cross-programme alignment contract. It does not amend, supersede or reinterpret the normative authority of either programme. Changes to AOP foundations, specifications, architecture or governance remain subject to the AOP programme's own change process. Changes to Agentic-Operation standards remain subject to the governance of their owning repositories.

The baseline is intended to guide the Agentic-Operation organization profile, documentation architecture, enterprise reference architecture, governance model and transformation guidance.

## 2. Foundational definition

**Agentic Operations is the enterprise operating model through which an organization organizes, governs, executes, measures and continuously improves its work using coordinated human and non-human agents operating within defined intent, context, authority, constraints and accountability.**

It is not synonymous with deploying AI agents, automating existing procedures or introducing an agent orchestration platform.

As an enterprise operating model, Agentic Operations addresses:

- enterprise intent, strategy and business outcomes;
- value streams, operating capabilities and operational responsibilities;
- organizational accountability and the allocation of work between human and non-human actors;
- decision rights, delegation and bounded autonomy;
- operational context, semantics and information dependencies;
- governance, risk, security, control and assurance;
- performance, evidence, value realization and continuous improvement;
- the evolution of workforce, organization, processes, services and technology.

The enterprise retains accountability for its outcomes. Delegating work to an agent does not transfer organizational accountability to that agent.

## 3. Critical semantic distinction: operating model and operating mode

The AOP Foundations repository defines Agentic Operations at level 6 of its six-level conceptual hierarchy as **the broader operating mode**. Its hierarchy is:

1. Agentic Operating Engineering — the discipline.
2. Agentic Operating Procedure — the operational specification.
3. Agent Skill — the reusable capability.
4. Domain Agent Harness — the controlled execution environment.
5. Agent — the execution actor.
6. Agentic Operations — the broader operating mode.

This hierarchy is an established AOP conceptual baseline and must not be silently changed by Agentic-Operation.

The enterprise operating model and the broader operating mode are related but not interchangeable:

- **Operating mode** describes the resulting regime of work: how human and non-human actors participate in and execute operational work, including the degree and distribution of delegated authority.
- **Operating model** describes how the enterprise intentionally designs, organizes, governs, funds, operates, measures and evolves that regime to achieve business outcomes.

Accordingly, Agentic Operations as an enterprise operating model governs and evolves the broader agentic operating mode. The AOP hierarchy describes the engineering and execution constructs through which agentic operational work is specified and performed.

This distinction preserves the AOP hierarchy while establishing the enterprise-level scope of Agentic-Operation.

## 4. Four complementary concerns

### 4.1 Enterprise operating model — Agentic-Operation

Defines the enterprise design and management of agentic work. It establishes the business rationale, outcomes, organizational responsibilities, operating capabilities, governance, performance expectations and transformation direction.

It answers:

- Why and where should the enterprise operate agentically?
- What outcomes and value streams are in scope?
- How are responsibilities allocated between people and non-human agents?
- What authority may be delegated, and under what conditions?
- How are risk, accountability, performance and value governed?
- How does the enterprise transition and mature?

### 4.2 Operational engineering and procedure — agentic-operating-procedure

The AOP programme defines the discipline and engineering foundations for specifying, governing and assuring operational execution by agents.

Its established repository boundaries include:

- `aop-foundations`: the AOP concept, hierarchy, glossary and conceptual boundaries.
- `aop-spec`: the normative AOP model, eight dimensions, procedure structure, identifiers, schemas, Agent Skill contract, security and conformance clauses.
- `aop-architecture`: architecture, layering, trust boundaries and pipeline topology.
- `aop-context-graph`: the representation of observed operational work.
- `aop-toolkit`: engineering and tooling implementations.
- `aop-reference-harness`: reference runtime and controlled execution.
- `aop-registry`: publication, versioning, provenance and discovery.
- `aop-conformance`: AOP and harness conformance.
- `aop-governance`: AOP programme change control and decisions.
- `aop-landscape`: comparison with adjacent disciplines.

AOP answers how operational work is observed, modelled, specified, constrained, executed and assured. It does not own the enterprise operating model as a whole.

### 4.3 AI Agent identity and management — Agentic-Operation

Agentic-Operation maintains enterprise-facing AI Agent management standards and related reference management services.

The standards include:

- **Spec-443 — AI Agent Profile:** the agent's identity and descriptive management profile.
- **Spec-444 — AI Agent Bootstrap:** the initialization and provisioning contract.
- **Spec-445 — AI Agent Card:** the discovery and capability-declaration contract.
- **Model Management Authority:** governed model records, approval, provenance and model dependency management.

These standards make agents identifiable and manageable within an enterprise environment. They do not replace an AOP, grant operational authority merely through declared capability, or define the enterprise operating model by themselves.

### 4.4 Enterprise adoption and transformation — Agentic-Operation

Defines how the enterprise progresses from experimentation to sustained operating model change. It includes readiness, portfolio selection, controlled adoption, operational integration, value-stream redesign, workforce evolution, governance maturity and value realization.

Adoption is not merely a deployment lifecycle. It is the managed evolution of enterprise operating capabilities and accountabilities.

## 5. Programme authority and responsibility boundaries

| Concern | Primary authority | Boundary |
|---|---|---|
| Enterprise Agentic Operations operating model | Agentic-Operation | Enterprise intent, operating capabilities, organizational design, governance, performance and transformation |
| AOP discipline and conceptual foundations | agentic-operating-procedure / aop-foundations | Definition of AOP, six-level hierarchy, vocabulary and conceptual boundaries |
| Normative AOP specification | agentic-operating-procedure / aop-spec | Eight dimensions, procedure structure, identifiers, schemas, Agent Skill contract, security and conformance |
| AOP architecture and execution engineering | agentic-operating-procedure | AOP architecture, observed-work context, tooling, harness, registry and conformance |
| AI Agent management standards | Agentic-Operation | Spec-443, Spec-444, Spec-445 and model management authority |
| Enterprise agent portfolio and management | Agentic-Operation | Enterprise-facing management, lifecycle, inventory, governance and service integration |
| Enterprise adoption and transformation | Agentic-Operation | Readiness, transformation progression, organizational change and value realization |
| Cross-programme integration | Jointly governed | Explicit, versioned contracts for shared concepts, dependencies and interfaces |

Neither programme may unilaterally redefine the other's normative artefacts. A change that crosses an authority boundary requires an agreed change contract, with the receiving programme retaining approval authority over its own artefacts.

## 6. Cross-programme integration contracts

### 6.1 Enterprise-to-procedure contract

Agentic-Operation establishes the enterprise outcomes, accountable ownership, business context, policy obligations and assurance expectations within which operational work is to be performed.

AOP provides the engineering and specification mechanisms to represent the operational intent, context, constraints, authority, capabilities, coordination, control and assurance requirements.

The integration must preserve:

- business outcome and operational intent;
- accountable business and operational ownership;
- relevant context and semantic dependencies;
- policy, regulatory and risk constraints;
- decision rights and escalation boundaries;
- expected outcomes and evidence requirements.

Agentic-Operation must not redefine the eight mandatory AOP dimensions or their normative semantics.

### 6.2 Procedure-to-agent contract

AOP specifies the operational requirements and the governed use of capabilities. Agentic-Operation's agent management standards describe and manage the participating agents and their declared capabilities, bootstrap context and discovery interfaces.

The integration must preserve:

- stable agent identity and version;
- declared capabilities and constraints;
- approved model dependencies and provenance;
- required skills, tools and environment bindings;
- authorization and delegation boundaries;
- operational traceability and evidence.

A declared capability, an Agent Card, or technical access to a tool does not independently establish permission to perform an operational action. Operational authority must be established and enforced through the applicable governance and execution controls.

### 6.3 Agent-to-enterprise contract

The enterprise operating model defines the conditions under which agents participate in enterprise work. Agent management services support the lifecycle and management of agents within that environment.

The integration must preserve:

- named human or organizational accountability;
- ownership of business and operational outcomes;
- explicit delegation and revocation of authority;
- appropriate human oversight and escalation;
- risk, security and control obligations;
- lifecycle, performance and change governance.

### 6.4 Evidence and improvement contract

Operational execution evidence should inform both procedural improvement and enterprise performance management, while retaining provenance and appropriate access controls.

AOP-related evidence can inform procedural coverage, execution correctness, control effectiveness, conformance and assurance.

Enterprise-level evidence can inform business outcomes, value realization, workforce effectiveness, service performance, risk exposure and operating model maturity.

Observed facts, derived assessments and management decisions must remain distinguishable.

## 7. Enterprise transformation progression

The following five stages are a conceptual progression for enterprise adoption. They are not yet a normative maturity model, scoring framework or conformance scheme.

### Stage 1 — Experimentation

Labs, prototypes and proofs of concept establish technical feasibility and explore business hypotheses.

Focus: problem selection, feasibility, initial value hypotheses, risk discovery and controlled experimentation.

### Stage 2 — Controlled adoption

Selected use cases enter bounded pilots with named business ownership and explicit operating constraints.

Focus: agent identity, approved models, defined authority, human oversight, test evidence, escalation and business relevance.

### Stage 3 — Operational integration

Agents become managed participants in production processes, services and operational environments.

Focus: production readiness, integration with enterprise procedures and systems, operational ownership, governance, monitoring, incident management and measurable outcomes.

### Stage 4 — Value-stream transformation

The enterprise redesigns end-to-end value streams to take advantage of coordinated human and non-human work across functional and system boundaries.

Focus: cross-functional coordination, shared context, dynamic work allocation, end-to-end performance and continuous optimization.

### Stage 5 — Agentic enterprise

Agentic operating principles are embedded in the enterprise operating model and continuously evolved under accountable governance.

Focus: enterprise-wide accountability, adaptive operating capabilities, coordinated bounded autonomy, continuous assurance, sustained value and managed evolution of the human and non-human workforce.

**Progression principle:** The transformation unit is the business outcome and value stream, not the individual agent. Agent count, model count or pilot count is not a sufficient measure of enterprise transformation.

Progression between stages must eventually be supported by defined capabilities, evidence, outcomes and governance criteria. Those criteria belong in a separately governed transformation and maturity deliverable.

## 8. Illustrative integration scenario

Consider customer order resolution:

1. Agentic-Operation defines the intended customer outcome, accountable business owner, service expectations, risk boundaries and performance measures.
2. AOP engineering specifies the operational work, including context, decisions, constraints, variants, exceptions and evidence obligations.
3. Spec-443 describes the participating agent and its declared characteristics and capabilities.
4. Spec-444 establishes the approved initialization and provisioning context.
5. Spec-445 exposes the agent's discovery and capability declaration.
6. Agent management services manage the agent within the enterprise environment.
7. The AOP-governed execution environment enforces the procedural and decision boundaries and captures execution evidence.
8. Enterprise performance management evaluates the customer outcome, service effectiveness, risk and realized value.
9. Evidence informs procedural improvement and the evolution of the enterprise operating model.

This scenario illustrates the separation of responsibilities. It is not a mandatory deployment topology or a claim that one programme's runtime services replace the other's.

## 9. Governance principles

1. **Authority preservation:** each programme retains authority over its declared subject matter.
2. **Explicit contracts:** cross-programme dependencies are documented, versioned and reviewable.
3. **No silent semantic change:** changes to shared concepts, schemas or normative requirements require explicit review by the owning authority.
4. **Enterprise accountability:** organizational accountability remains with designated human and institutional authorities.
5. **Bounded autonomy:** delegated authority is explicit, justified, enforceable, observable and revocable.
6. **Evidence-based assurance:** claims of capability, conformance, performance and value are supported by traceable evidence.
7. **Interoperability:** integration uses declared interfaces and contracts rather than duplicated normative specifications.
8. **Evolution without duplication:** new requirements are assigned to the appropriate authority rather than recreated in adjacent programmes.

## 10. Repository and documentation implications

The Agentic-Operation organization should be the authoritative enterprise-facing home for:

- the Agentic Operations enterprise operating model;
- business rationale, value propositions and executive guidance;
- enterprise capabilities and reference architecture;
- AI Agent identity and management standards;
- enterprise governance, risk and assurance;
- integration with AOP and other operational engineering specifications;
- enterprise adoption, transformation and maturity;
- value realization and performance measurement.

The organization should not duplicate or claim normative ownership of AOP's conceptual foundations, metamodel, schemas, conformance clauses, architecture or AOP programme governance.

The existing Agentic-Operation organization profile contains substantive material on Spec-443, Spec-444, Spec-445, Model Management Authority, management services, conformance, business scenarios, personas and AI-agent consumption. This baseline does not authorize removing or replacing that material. Any profile change must be additive or reorganizational, with the existing substantive content retained and its destination traceable.

## 11. Reconnaissance notes and open points

The repository review identified a discrepancy that must remain visible until resolved:

- The AOP Governance repository map lists `aop-evaluation`, `aop-adoption` and `aop-examples`.
- The current repository listing accessible during this review returned 11 repositories and did not include those three names.
- AOP Foundations also maps Agentic Operations to `aop-adoption`, with `aop-examples` and `aop-landscape` as supporting homes.

This is an estate inventory and repository-map reconciliation item for the AOP programme. This baseline does not assume that the three repositories exist, nor does it assign their responsibilities to Agentic-Operation. Their status should be confirmed with the AOP programme owner.

The TM Forum IG1579 guidebook, *Agentic Operations: The Operating Model for 2030 AI-Native Telco*, is a relevant industry-facing reference for the enterprise operating model framing. It should be treated as an external reference and contextual alignment point, not as a replacement for the programme-specific authority boundaries established here.

## 12. Decisions proposed for approval

| Decision | Proposed position |
|---|---|
| Enterprise definition | Adopt the definition in Section 2 |
| Operating model versus operating mode | Preserve the AOP level-6 operating-mode concept; define the enterprise operating model as the governance and design framework that shapes and evolves that mode |
| Programme boundaries | Adopt the authority allocation in Section 5 |
| AOP relationship | Treat AOP as the engineering and operational specification foundation for governed agentic execution |
| Agent management standards | Retain Spec-443, Spec-444, Spec-445 and Model Management Authority within Agentic-Operation |
| Transformation progression | Adopt the five stages as a conceptual progression only |
| Cross-programme governance | Require explicit, versioned contracts for shared concepts and dependencies |
| Existing organization profile | Preserve all existing substantive content through additive change and traceable relocation only |

## 13. Acceptance criteria

This baseline is ready for approval when:

- Agentic Operations has an unambiguous enterprise operating model definition.
- Operating model and operating mode are distinguished without changing the AOP six-level hierarchy.
- Agentic Operating Engineering, AOP, Agent Skill, Domain Agent Harness and Agent retain their established conceptual distinctions.
- Agentic-Operation and AOP authority boundaries are explicit.
- Spec-443, Spec-444, Spec-445 and Model Management Authority are accurately positioned.
- Cross-programme integration contracts are documented.
- The transformation progression is clearly identified as conceptual, not yet a maturity assessment.
- Repository inventory discrepancies are recorded rather than silently resolved.
- No existing normative specification is redefined or weakened.
- The existing Agentic-Operation profile content is protected from loss in subsequent changes.

## 14. Follow-on change sequence

Subject to approval of this baseline:

1. **CR-AO-ORG-001 — Organization Purpose and Authority:** align the organization profile with the enterprise operating model while preserving existing substantive content.
2. **CR-AO-MODEL-001 — Agentic Operations Conceptual Model:** formalize principles, dimensions, concepts and terminology.
3. **CR-AO-ARCH-001 — Enterprise Reference Architecture:** establish enterprise architecture and integration with AOP and agent management services.
4. **CR-AO-DOC-001 — Documentation Architecture:** establish documentation hierarchy, navigation and authoritative-source conventions.
5. **CR-AO-TRANS-001 — Enterprise Transformation Model:** develop readiness, adoption and maturity progression.
6. **CR-AO-GOV-001 — Enterprise Governance Model:** formalize accountability, autonomy, risk, control and assurance.
7. **CR-AO-MEAS-001 — Value and Performance Measurement:** establish outcome, value-realization and maturity measurement.

---

**End of document.**
