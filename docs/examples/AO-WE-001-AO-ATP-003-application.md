# AO-WE-001 / AO-ATP-003 — Architecture Transformation Application

| Field | Value |
|---|---|
| Identifier | AO-WE-001-ATP-003 |
| Title | Fault Management Architecture Transformation Application |
| Version | 0.1.0 |
| Status | Proposed architecture assessment; no implementation or runtime validation claimed |
| Authority | Agentic-Operation |
| Classification | Non-normative application and decision-support artefact |
| Scenario baseline | [AO-WE-001](./AO-WE-001-fault-management-opendea-aop-worked-example.md) |
| Method | [AO-ATP-003](../transformation/AO-ATP-003-architecture-transformation-toolkit.md) |
| Reconciliation date | 2026-11-26 |

## 1. Purpose and decision boundary

This document applies the AO-ATP-003 instruments to the fault-management scenario already documented in AO-WE-001. It converts the existing crosswalk and its explicit defects into a structured transformation assessment: evidence register, architecture realization dispositions, work dispositions, target-state principles, transition increments and acceptance conditions.

It is not a redesign authorization, an implementation specification, a production architecture, or a claim that the scenario is operationally validated. All proposed dispositions remain subject to the relevant enterprise, OpenDEA and AOP authorities.

The companion registers are:

- [Architecture discovery and evidence register](./AO-WE-001-discovery-and-evidence-register.md)
- [Architecture disposition decision register](./AO-WE-001-architecture-disposition-register.md)
- [Work disposition register](./AO-WE-001-work-disposition-register.md)
- [Transition and acceptance plan](./AO-WE-001-transition-and-acceptance-plan.md)

## 2. Transformation intent

### Intended enterprise outcome

Restore the affected network service within the applicable service window, minimize customer and operational impact, and preserve a verifiable record of diagnosis, authorization, intervention and restoration.

### Scope

The assessment covers the work and architecture required to correlate alarms, diagnose a line fault, perform a loopback test, resolve or dispatch, notify planning, reconcile inventory where applicable, verify restoration and preserve the case record.

### Explicit exclusions

- It does not define or amend OpenDEA metamodels, canonical entities, catalogue records or identifiers.
- It does not resolve the AOP SOP/manifest conflicts or modify AOP specifications, skills, harnesses, runtime or conformance contracts.
- It does not assert which production OSS, line-test, dispatch, planning or customer-master systems are deployed.
- It does not select vendors, products, cloud platforms or agent frameworks.
- It does not establish a measured performance baseline or business case.

### Pivotal architecture question

**Which responsibilities should remain deterministic, which work requires human judgment or authorization, and where does bounded agentic coordination improve end-to-end fault restoration without weakening service contracts, operational controls, evidence integrity or accountability?**

The question is deliberately broader than whether a fault-management agent can execute the SOP. It tests the operating model, service architecture, work allocation and authority system together.

## 3. Baseline diagnosis

The existing AO-WE-001 crosswalk establishes useful architecture anchors, but it does not establish an executable or approved architecture.

| Area | Baseline finding | Transformation implication |
|---|---|---|
| Outcome and capability | Incident and Problem Management is an active capability record; Network Monitoring Service is a supporting Business Service, not the affected customer service | Preserve capability/outcome traceability; resolve the actual affected service and service commitment |
| Process | Exact network line fault-management process is unresolved; adjacent platform incident process/activity records are candidates | Do not bind execution to the adjacent candidate process; obtain process-owner disposition |
| System identity | OSS is a system-class context; a canonical System instance was not resolved | Establish actual system and deployment identities before binding runtime integrations |
| Components and functions | Relevant components are active; several Information System Functions are planned/proposed | Treat catalogue records as semantic anchors, not approved callable functions |
| Services and interfaces | Service/interface records are active and bound in catalogue data, but approval remains proposed | Validate approval, deployment, consumer/provider identity, contract and operational availability |
| Unmapped responsibilities | Loopback test, fault resolution and planning notification lack verified function/service/interface mappings | Keep these integration points unresolved; do not infer from labels |
| Work authority | Dispatch threshold and decision-rights ladder conflict; on-call escalation semantics conflict | No agentic dispatch or policy-dependent action until AOP authority is reconciled and externally enforced |
| Skill coverage | Resolve-fault and reconcile-inventory appear as permitted actions without explicit skill bindings | Exclude from executable scope until governed skill/tool bindings and authority are complete |
| Event evidence | 36/40 cases have events outside declared case interval; 36/40 have non-monotonic event order; all 40 have cycle-time mismatch | Fixture is unsuitable for performance measurement or runtime acceptance |
| Measures | p50 fixture measure is not equivalent to admitted arithmetic-mean MTTR; other measures are candidate | Resolve measure semantics and source data before baseline or outcome claims |
| Runtime assurance | Reference harness gate was not run for this integration | Require reproducible run, version/digest pinning, conformance and replay evidence |

Detailed source claims, source artefacts and limitations are recorded in AO-WE-001 and the companion discovery register.

## 4. Architecture realization dispositions

These dispositions concern technical responsibilities, not who performs the work. They are proposed assessment outcomes, not approved ADRs.

| Responsibility | Proposed disposition | Rationale and constraint |
|---|---|---|
| Existing alarm collection and correlation realization | Retain, subject to verification | Existing service/interface and component records provide useful anchors. Confirm actual implementation, approval, consumers, contract and runtime characteristics before relying on them |
| Agent access to approved alarm services | Wrap / agent-enable conditionally | Use narrow, typed contracts, workload identity, external authorization, audit correlation and bounded read-only scope. Do not expose broad OSS credentials |
| Loopback-test execution | Unresolved; verify then integrate or introduce | No verified canonical function/service/interface or deployment identity is established. Do not create a local substitute in this assessment |
| Fault-resolution action | Unresolved; retain deterministic mechanisms where verified | The source does not define the realization or complete skill binding. Determine actual repair action, side effects, idempotency, safety interlocks and verification before deciding |
| Field dispatch | Retain existing service boundary; agent-enable only after approval control | Existing Field Dispatch Service/Interface records are active but proposed for approval. Dispatch remains approval-required according to the manifest decision-rights ladder until the AOP owner resolves the conflicting threshold rule |
| Planning notification | Unresolved; integrate only after semantic and ownership resolution | No matching planning service/interface was established. Acknowledgement and failure handling must be defined by the planning owner |
| Resource inventory | Retain existing service boundary; defer agent write access | Resource Inventory Service/Interface records exist, but approval and actual runtime binding are unverified. Reconcile read versus write authority and skill coverage |
| Trouble-ticket record | Retain as a candidate system-of-record boundary | The Trouble Ticketing Service/Interface is identified, but actual system identity, record semantics, lifecycle and deployment binding still require confirmation |
| End-to-end coordination | Agentic overlay, conditional | AOP may coordinate context-sensitive sequencing only after policy, work, service contracts, skill bindings, identity, state and recovery are governed. It must not replace deterministic controls |
| Case corpus and metric pipeline | Remediate before use | Correct source semantics/data and add deterministic validation. Do not build performance dashboards from invalid fixture values |

No recommendation is made to decompose the OSS into microservices or replace it wholesale. The available evidence does not establish that internal modularity, deployment topology or runtime coupling is deficient.

## 5. Work dispositions

Work disposition is independent of architecture disposition. The provisional allocation is:

| Work unit | Proposed disposition | Conditions |
|---|---|---|
| Alarm intake and correlation | Deterministic automation with agent-assisted interpretation | Deterministic correlation rules remain authoritative where defined; agent may explain and assemble context, with evidence links and uncertainty |
| Case context assembly | Agent-assisted | Read-only, case-scoped access; source provenance and freshness visible; no inferred facts silently promoted |
| Loopback-test planning | Agent-assisted | Agent may recommend diagnostic sequence; execution remains unavailable until approved test contract, safety limits and skill binding are established |
| Loopback-test execution | Unresolved | Requires verified system/function, constrained credential, permitted test scope, safety controls and independently observable result |
| Fault diagnosis | Agent-assisted | Recommendations grounded in current telemetry, topology and case evidence; confidence/uncertainty and alternatives exposed; human escalation for ambiguous/high-consequence cases |
| Fault resolution | Unresolved; deterministic execution preferred for verified stable actions | Do not enable execution until the action, preconditions, side effects, rollback/compensation and skill/tool authority are explicit |
| Field dispatch decision | Human-owned approval; agent-assisted preparation | Agent prepares evidence and dispatch proposal; named supervisor authorizes; external policy gate binds approval to exact payload, context and expiry |
| Dispatch execution | Deterministic service invocation after valid approval | External authorization, idempotency, duplicate protection, acknowledgement and audit linkage required |
| Planning notification | Deterministic automation after contract resolution; agent-assisted preparation | No execution until planning owner confirms target, payload, acknowledgement and failure semantics |
| Inventory reconciliation | Unresolved; human-supervised until authority is explicit | Determine whether action is read-only or write-capable, identify system of record and reconcile skill/tool binding |
| Restoration verification | Deterministic checks plus human exception handling | Verify against authoritative network/service state; ticket closure or agent assertion alone is insufficient |
| Case record and evidence assembly | Deterministic persistence with agent-assisted summarization | Preserve original events, decision/approval identities, invocations, acknowledgements, versions and immutable provenance |

The supervisor remains accountable for reserved operational decisions and interventions. Technical capability, model confidence or tool availability does not confer authority.

## 6. Target architecture principles

The target is a governed coordination architecture, not a prescribed product topology.

1. **Outcome and process authority:** resolve the affected service, service window, process owner, case boundary and completion conditions before implementation.
2. **Canonical semantic joins:** use verified OpenDEA identities and typed relationships. Preserve unresolved mappings as explicit gaps.
3. **Service contract boundary:** agents consume narrow, versioned service contracts through controlled interfaces; they do not receive direct, broad system access.
4. **Deterministic control plane:** identity, authorization, approval enforcement, idempotency, safety interlocks, state transitions and audit persistence remain externally enforced.
5. **Bounded agentic coordination:** agents interpret context, assemble evidence, recommend, sequence permitted work and manage exceptions within explicit limits.
6. **Human authority:** approval, pause, termination, exception judgment and reserved decisions are assigned to named roles and enforced outside the agent.
7. **Evidence continuity:** correlate case, AOP/run, agent, skill, tool invocation, policy decision, human approval, service request/response and verified outcome.
8. **Independent outcome verification:** restoration is established from authoritative service/network evidence, not from a successful tool response or generated summary.
9. **Reversible transition:** preserve current operational path and define routing, coexistence, rollback and data reconciliation before cutover.
10. **Measurement integrity:** establish valid metric semantics and data quality before making improvement claims.

### Conceptual flow

```text
Business outcome and service commitment
                 |
Approved process and work boundary
                 |
Case context + authoritative evidence
                 |
AOP-governed coordination (once upstream defects are resolved)
          /                 \
 Human authority       Deterministic services
 approval / exception  test / dispatch / ticket /
 intervention          inventory / notification
          \                 /
           External policy and identity enforcement
                         |
              Verified operational state
                         |
          Correlated evidence and case record
                         |
             Validated outcome measures
```

This is a target responsibility view. It does not assert that the listed services are currently connected or deployed.

## 7. Transformation sequence

The recommended order is dependency-driven. Do not begin by deploying an agent against the present fixture.

| Increment | Focus | Exit condition |
|---|---|---|
| I-00 — Establish authority and evidence | Confirm scenario owner, affected customer service, process owner, system owners, source versions and evidence permissions | Scope, owners, service outcome and evidence provenance accepted |
| I-01 — Repair semantic and source defects | Resolve process disposition; verify system/function/service/interface identities; reconcile AOP policy and skill bindings; correct or re-specify case corpus and metric definitions | Canonical mappings or explicit governed gaps; policy and skills consistent; corpus checks pass |
| I-02 — Establish deterministic service contracts | Verify service deployment and approvals; define loopback, resolution and planning integration contracts; establish identity, scopes, idempotency, errors and audit | Contract tests and negative authorization tests pass in a controlled test environment |
| I-03 — Establish human approval and operational controls | Implement dispatch approval binding, escalation, pause, termination, revocation, recovery and case evidence correlation | Approval and intervention scenarios pass through real enforcement paths |
| I-04 — Execute controlled AOP integration | Pin AOP/toolkit/harness versions and digests; execute conformance and reference gate against corrected scenario | Reproducible run and replay evidence retained; no unresolved critical authority or data defect |
| I-05 — Pilot bounded coordination | Pilot selected read-only/low-consequence coordination before any consequential agent execution | Operational owner accepts pilot evidence, exceptions, control effectiveness and rollback readiness |
| I-06 — Measure and decide scale | Compare valid outcomes to validated baseline; review safety, service quality, customer impact, cost and human workload | Evidence-based scale, revise or stop decision by accountable authority |

The sequence is a proposal. It does not authorize changes in OpenDEA or AOP repositories. Upstream work must proceed through their own change authorities.

## 8. Principal risks and controls

| Risk | Required control |
|---|---|
| Agent bypasses policy by direct service access | External identity, authorization and policy enforcement; deny-by-default scopes |
| Dispatch occurs without valid approval | Approval bound to exact action, payload, case context, approver, role and expiry; enforce at execution boundary |
| Duplicate or stale side effects | Idempotency keys, replay protection, state preconditions and reconciliation |
| Invalid or stale case context | Provenance, timestamp, source identity, freshness and contradiction handling |
| Successful invocation mistaken for restoration | Independent network/service-state verification |
| Agent hides unresolved uncertainty | Explicit unknown state, confidence limitations and mandatory escalation conditions |
| Runtime trace cannot establish accountability | Correlate case/run, versions, agent, skill, tool, policy, approval and service evidence |
| Transition interrupts service or duplicates actions | Parallel-run policy, single-writer controls, routing plan, rollback and reconciliation |
| Invalid data produces false performance claims | Versioned corpus validation and metric-definition governance |

## 9. Unresolved decisions

The following cannot be decided by Agentic-Operation on the current evidence:

1. Which customer-facing network service and service commitment define successful restoration?
2. Which admitted business process governs network line fault management?
3. Which concrete OSS and external system instances are in scope, and who owns them?
4. Are the existing Information System Function, Service and Interface records approved and bound to deployed implementations?
5. What are the authoritative contracts for loopback testing, fault resolution and planning notification?
6. What is the precedence between dispatch threshold logic and the AOP decision-rights ladder?
7. Does the prohibited on-call action mean no automated dispatch/escalation, while human handoff remains allowed?
8. Which skills and tools implement resolution and inventory reconciliation, and what authority do they require?
9. What are the corrected semantics and provenance for case timestamps, event ordering and cycle time?
10. Which recovery-time statistic, denominator, observation window and first-pass measure will be governed?
11. Which operational environment and authority path will support the reference harness integration and controlled pilot?

Each decision requires its named upstream or enterprise owner and evidence; this assessment does not fill the gaps by assumption.

## 10. Current recommendation

**Proceed with I-00 and I-01 only.** The scenario is sufficiently concrete to define a transformation path, but not sufficiently governed or evidenced to authorize runtime integration or agent-executed consequential work.

Preserve existing deterministic service responsibilities where they are verified. Use agents first for bounded context assembly, interpretation and coordination. Keep dispatch human-approved and externally enforced. Defer loopback execution, fault-resolution execution, planning notification and inventory writes until their semantics, service bindings, skill coverage and authority are resolved.

This is a proposed architecture disposition, not an approved implementation decision.

## 11. Acceptance status

The application itself is accepted as a structured assessment only when its source references, limitations, proposed decisions and unresolved ownership are reviewed. It does not advance AO-WE-001 beyond its current status of architecture crosswalk; execution remains unvalidated.

A validated reference example still has to satisfy the acceptance criteria in AO-WE-001 Section 11 and the increment-specific gates in [the transition and acceptance plan](./AO-WE-001-transition-and-acceptance-plan.md).
