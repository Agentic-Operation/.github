# Architecture Transformation Instrument Catalogue

This catalogue defines reusable practitioner instruments. Apply them selectively according to the transformation question, consequence and available evidence.

## Standard instrument record

Each instrument is described by purpose, applicability, trigger, inputs, procedure, outputs, decision use and limitations. The catalogue is guidance, not a mandatory sequence.

## Discovery and baseline

### AT-D01 — Outcome and Stakeholder Framing
- **Purpose:** Establish the outcome, beneficiaries, accountable stakeholders and operating constraints.
- **Trigger:** A transformation opportunity is proposed or its scope is unclear.
- **Inputs:** Strategy, service commitments, stakeholder needs, risk and regulatory constraints.
- **Procedure:** Identify outcome owner and beneficiaries; state observable outcome conditions; define scope, exclusions, constraints and baseline measures; distinguish outcome from proposed solution.
- **Outputs:** Transformation Intent Brief, outcome statement, stakeholder and accountability map.
- **Decision use:** Confirms whether the transformation has a legitimate outcome and bounded scope.
- **Limitations:** Interviews and strategy statements do not independently prove current performance or causal contribution.

### AT-D02 — Value-Stream Boundary Analysis
- **Purpose:** Define the end-to-end work boundary relevant to the outcome.
- **Trigger:** Work spans teams, systems, channels or organizations.
- **Inputs:** Outcome frame, customer/service journey, process documentation and case evidence.
- **Procedure:** Identify trigger, start and end conditions, consumers, hand-offs, outcome states, exclusions and adjacent value streams.
- **Outputs:** Boundary statement, context map, included/excluded work.
- **Decision use:** Prevents local optimization that moves cost or risk outside the selected boundary.
- **Limitations:** A boundary is an analytical choice and must be validated with affected owners.

### AT-D03 — Capability-to-Outcome Traceability
- **Purpose:** Link intended outcomes to the enterprise abilities and responsibilities that contribute to them.
- **Trigger:** The transformation risks becoming application- or project-centric.
- **Inputs:** Outcome frame, canonical capability model and ownership information.
- **Procedure:** Resolve capabilities by canonical identity; map contribution and dependencies; identify unsupported claims and gaps.
- **Outputs:** Capability traceability view and unresolved mapping register.
- **Decision use:** Tests whether proposed changes preserve or improve the required enterprise ability.
- **Limitations:** Capability mapping does not prove that a capability is operationally effective.

### AT-D04 — Process and Work Discovery
- **Purpose:** Reconstruct documented and actual work, including variants, decisions, exceptions and informal hand-offs.
- **Trigger:** Procedures may not reflect actual execution or automation is being considered.
- **Inputs:** SOPs, case records, interviews, system events, observation permissions and process-owner input.
- **Procedure:** Establish lawful observation and data minimization; sample representative cases; map actors, tasks, decisions, exceptions and outcomes; compare observed variants with approved procedure; validate with process owners.
- **Outputs:** Work model, variant analysis, exception register and evidence gaps.
- **Decision use:** Informs process redesign and human/deterministic/agentic work disposition.
- **Limitations:** Samples may be biased or incomplete; mined patterns are not automatically approved business rules.

### AT-D05 — Architecture Inventory and Responsibility Mapping
- **Purpose:** Identify systems and the responsibilities they actually realize.
- **Trigger:** Application inventories or diagrams are incomplete, stale or name-based.
- **Inputs:** Architecture repository, runtime observations, service catalogues, source repositories and owner interviews.
- **Procedure:** Resolve canonical entities and versions; identify system, component, function, service, interface, data and owner; validate responsibility against implementation and runtime evidence.
- **Outputs:** Architecture inventory, responsibility map and unverified-claim register.
- **Decision use:** Establishes the baseline for refactoring and impact analysis.
- **Limitations:** Repository presence or declared ownership does not prove deployment, availability or runtime use.

### AT-D06 — Service Contract and Dependency Mapping
- **Purpose:** Understand consumers, providers, interaction contracts and dependency behaviour.
- **Trigger:** Service boundaries, integration risk or migration sequencing are unclear.
- **Inputs:** API/event/file contracts, service catalogues, telemetry, deployment records and dependency owners.
- **Procedure:** Map provider, consumer, contract, protocol, data, failure semantics, versioning, SLO and dependency direction; distinguish service from interface and implementation.
- **Outputs:** Contract map, dependency graph and contract gap list.
- **Decision use:** Informs wrapping, extraction, integration redesign and coexistence.
- **Limitations:** Static contracts may not reveal undocumented runtime coupling.

### AT-D07 — Evidence and Provenance Assessment
- **Purpose:** Assess the reliability and limits of architecture and operational assertions.
- **Trigger:** Material decisions rely on mixed documentation, telemetry, interviews or fixtures.
- **Inputs:** Claims, source artefacts, versions, observations and accountable owners.
- **Procedure:** Classify each assertion; record source, date, scope, version, owner and limitation; preserve conflicts; identify evidence needed to raise confidence.
- **Outputs:** Evidence register and unresolved evidence plan.
- **Decision use:** Determines which claims can support design or acceptance decisions.
- **Limitations:** Confidence labels are not substitutes for domain-specific assurance criteria.

### AT-D08 — Current-State Architecture Reconstruction
- **Purpose:** Assemble linked views of enterprise intent, work, services, systems, information and controls.
- **Trigger:** No sufficiently coherent baseline exists.
- **Inputs:** AT-D01 through AT-D07 outputs and canonical models.
- **Procedure:** Build linked views; resolve identifiers; distinguish observed from approved state; mark missing relationships and assumptions; validate with owners.
- **Outputs:** Versioned current-state model and gap register.
- **Decision use:** Establishes the baseline for diagnosis and target design.
- **Limitations:** A model is a representation; it does not itself establish completeness or runtime truth.

## Diagnosis and analysis

### AT-A01 — Outcome-to-Architecture Gap Analysis
Compare required outcome conditions with the capabilities, work, services, systems and controls that realize them. Record each gap, evidence, impact, owner and uncertainty. Output: prioritized gap register. Do not assume every gap requires software change.

### AT-A02 — Work Fragmentation and Hand-off Analysis
Identify queues, duplicate entry, wait states, rework, ownership discontinuities and manual coordination. Validate with case evidence and affected workers. Output: hand-off and fragmentation analysis. Do not equate fewer hand-offs with better outcomes without examining control and quality effects.

### AT-A03 — Decision-Boundary Analysis
Map decisions, decision inputs, authority, policy, reversibility, consequence and escalation. Distinguish recommendation from authorization and execution. Output: decision-rights map and unresolved authority list.

### AT-A04 — Service Dependency and Coupling Analysis
Examine static and runtime dependencies, shared data, release coupling, failure propagation and ownership. Output: dependency and coupling findings. Do not use coupling metrics alone to justify extraction.

### AT-A05 — Information Ownership and Context Analysis
Identify systems of record, data stewardship, provenance, freshness, access, purpose and context availability. Output: information/context contract gaps. Do not treat an agent's accessible context as authoritative merely because it is retrievable.

### AT-A06 — Exception and Failure-Path Analysis
Review normal, exceptional, degraded, denied, timeout, duplicate and recovery paths. Output: failure-mode and exception register. Happy-path demonstrations are insufficient for consequential work.

### AT-A07 — Operational Constraint and Change-Friction Analysis
Assess deployment constraints, service windows, skills, support model, release frequency, observability, cost and organizational dependencies. Output: constraints and delivery bottleneck analysis.

### AT-A08 — Trust, Authority and Control-Boundary Analysis
Identify identities, permissions, delegated authority, policy enforcement, approval, separation of duties, audit and intervention. Output: control-boundary map. Model instructions alone are not an enforcement mechanism.

### AT-A09 — Agent Suitability and Delegation Analysis
Evaluate work characteristics, context, variability, consequence, reversibility, deterministic constraints, human judgment and verification feasibility. Output: reasoned work disposition, controls and unresolved questions, not an unsupported universal score.

### AT-A10 — Architecture Evidence Quality Assessment
Assess coverage, currency, provenance, consistency and traceability of architecture claims. Output: evidence-quality findings and remediation needs. Do not confuse documentation completeness with architecture correctness.

## Target architecture and transition

### AT-T01 — Work Disposition Assessment
Apply the work dispositions defined in the decision frameworks to a bounded work unit. Record accountable owner, evidence, authority and controls. Output: approved or proposed work disposition.

### AT-T02 — Architecture Realization Disposition
Evaluate retain, wrap, refactor, modularize, extract, integrate, agent-enable, replace, retire and introduce alternatives. Output: architecture disposition decision and ADR where required.

### AT-T03 — Target Service and Responsibility Design
Define business service promise, information-system service contract, provider/consumer, functions, components, interfaces, information and ownership using canonical semantics. Output: target responsibility and contract view.

### AT-T04 — Human-Agent Operating Boundary Design
Specify what humans and agents may observe, recommend, approve and execute; define escalation, override, pause, termination and accountability. Output: authority and interaction design.

### AT-T05 — Transition Strategy Selection
Compare incremental enhancement, modularization, wrapping, strangler transition, parallel operation, selective extraction, replacement, process redesign and agentic overlay. Output: strategy rationale and constraints.

### AT-T06 — Transition Architecture Planning
Define current, intermediate and target states, migration sequence, coexistence, dependencies, rollback and acceptance. Output: transition architecture plan.

## Verification and management

### AT-V01 — Architecture and Semantic Conformance
Validate canonical identifiers, schema, typed relationships, ownership and model consistency. Output: conformance evidence and exceptions.

### AT-V02 — Contract and Integration Verification
Test interface and service contracts, compatibility, failure semantics, idempotency and consumer/provider expectations. Output: test results and contract defects.

### AT-V03 — Scenario, Negative and Recovery Verification
Exercise normal, exceptional, adversarial, denied, timeout, retry and recovery scenarios. Output: reproducible scenario evidence.

### AT-V04 — Authority and Human Intervention Verification
Exercise approval, rejection, escalation, pause, termination and override through real control paths. Output: evidence of enforced authority and intervention.

### AT-V05 — Operational Readiness and Outcome Verification
Assess monitoring, support, recovery, operational ownership and outcome measures against a valid baseline. Output: readiness and outcome evidence, with limitations.

### AT-M01 — Transformation Backlog and Dependency Management
Translate approved decisions into owned increments with dependencies, risk, verification and acceptance. Output: traceable transformation backlog.

### AT-M02 — Transformation Increment Acceptance
Consolidate implementation, test, control, operational and outcome evidence; record acceptance authority and residual risks. Output: explicit acceptance or rejection decision.

## Instrument selection

Select the smallest set of instruments sufficient to resolve the decision. Record why material instruments were omitted, especially where the omission affects confidence or risk. Instruments may be repeated as new evidence emerges.
