# AO-WE-001 — Transition and Acceptance Plan

| Field | Value |
|---|---|
| Identifier | AO-WE-001-PLAN-TRANSITION |
| Status | Proposed staged plan; no implementation authorization |
| Assessment | [AO-WE-001 / AO-ATP-003 application](./AO-WE-001-AO-ATP-003-application.md) |
| Decision register | [Architecture disposition register](./AO-WE-001-architecture-disposition-register.md) |
| Work register | [Work disposition register](./AO-WE-001-work-disposition-register.md) |
| Date | 2026-11-26 |

## 1. Transition objective

Progress from an architecture crosswalk and reference fixture to a reproducible, controlled integration demonstration, without implying production deployment or business outcome realization.

The sequence is gated by semantic authority, service contracts, AOP policy, data integrity, human control and evidence quality. An agent deployment is not the first increment.

## 2. State definitions

### Current state

- AO-WE-001 is an architecture crosswalk with source-pinned OpenDEA records and AOP fixture references.
- Exact business process, several system identities and some function/service/interface bindings remain unresolved.
- Relevant function records are planned/proposed; service/interface records are active/proposed.
- AOP manifest/SOP authority conflicts and missing skill bindings remain open.
- The 40-case corpus fails timestamp/order/cycle-time checks under its apparent field semantics.
- Metric definitions are not fully aligned; reference harness integration gate has not been run.
- No end-to-end enterprise outcome evidence is available.

### Target reference state

- The scenario has a named enterprise owner, affected service, service commitment and process authority.
- Canonical semantic mappings are verified or retained as explicit gaps.
- Every callable operation has an approved service contract, implementation binding, identity scope and failure semantics.
- AOP actions and skills are consistent with one authority model and conformance evidence.
- Human approval and intervention are exercised through real enforcement paths.
- Case/run/service/outcome evidence is correlated and replayable.
- Fixture, simulated and test results are distinguished; no live claims are made without live evidence.

### Coexistence rule

The existing/manual operational path remains authoritative until the relevant controlled increment is accepted. No parallel execution may create duplicate dispatch, repair or inventory side effects. Any parallel test must use isolated test systems or explicit single-writer controls.

## 3. Increment plan

| Increment | Scope | Required owners | Verification / exit criteria | Rollback or stop condition |
|---|---|---|---|---|
| I-00 — Intent and ownership | Confirm affected service, outcome, service window, process owner, scenario owner, system owners and permitted evidence | Enterprise service/process owners | Signed scope and ownership record; outcome and completion conditions explicit | Stop if outcome, process authority or evidence permissions cannot be established |
| I-01 — Semantic and source remediation | Process disposition; system and service crosswalk; AOP authority/skill reconciliation; corpus and metric repair | OpenDEA catalogue owners; AOP owners; scenario owner | Canonical IDs/versions or explicit unresolved gaps; policy/skill conformance; corpus schema, chronology and metric checks pass | Do not proceed to integration with unresolved critical authority or data semantics |
| I-02 — Service contract verification | Confirm deployed providers, consumer contracts, API/event schemas, identities, errors, idempotency, audit and operational ownership | OSS, line-test, dispatch, planning, inventory and ticketing owners | Contract tests, runtime binding evidence, negative authorization tests, failure and duplicate tests | Retain current/manual path; revoke test credentials and remove unapproved adapters |
| I-03 — Human control implementation | Dispatch approval, escalation, pause, termination, revocation, intervention and case evidence correlation | Operations authority, security, AOP owner | Tests for approval/rejection/expiry/revocation/altered payload/wrong role/duplicate/timeout and evidence trace | No consequential agent action if enforcement can be bypassed or audit is incomplete |
| I-04 — Reproducible AOP integration | Pin artefacts/digests; run toolkit, harness, conformance and replay on corrected fixture | AOP programme and integration lead | Reproducible logs, content digests, conformance results, replay and explicit evidence classification | Stop on nondeterministic or unexplained result; preserve logs and return to source correction |
| I-05 — Controlled pilot | Start with read-only case-context assembly and bounded agent-assisted diagnosis; expand only by separate approval | Enterprise operations owner, risk/security, process owner | Pilot scenarios, exception outcomes, human workload, service impact, control effectiveness and rollback readiness reviewed | Immediate pause for unauthorized action, lost evidence, unsafe recommendation or service degradation |
| I-06 — Outcome evaluation | Compare validated measures to an approved baseline and decide whether to scale, revise or stop | Outcome owner, metric owner, operations leadership | Metric definitions, valid denominator/window, independent source evidence and limitations accepted | No scale decision if attribution or source integrity is insufficient |

## 4. Transition architecture controls

### Identity and access
- Use workload identities for agents and services.
- Scope permissions to the case, action and environment.
- Separate read, diagnostic, dispatch, inventory-write and ticket-update privileges.
- Apply deny-by-default and external authorization; model instructions are not a security boundary.

### Approval and intervention
- Bind approval to an immutable action proposal, exact payload, case context/version, approver identity/role and expiry.
- Reject changed, stale, duplicated, revoked or out-of-scope approvals.
- Provide pause, terminate, revoke and human takeover paths.
- Do not allow agent self-approval or approval inferred from absence of rejection.

### Service and state integrity
- Validate contracts and payload schemas.
- Define idempotency, retry, timeout, compensation and reconciliation.
- Preserve a single authoritative writer for consequential state.
- Verify outcomes against authoritative systems independently of invocation success.

### Evidence and provenance
Correlate at minimum:
- case and source-record identity;
- AOP version and digest;
- harness/toolkit version and digest;
- agent and skill identity/version;
- tool/service identity and contract version;
- policy decision and approval reference;
- request, response, acknowledgement and correlation IDs;
- resulting operational state and verification evidence.

## 5. Acceptance gates

| Gate | Acceptance question | Minimum evidence | Current status |
|---|---|---|---|
| G-0 Intent | Is the outcome, scope, affected service and accountable owner explicit? | Approved intent and ownership | Open |
| G-1 Baseline | Are current work, architecture and evidence sufficiently understood? | Discovery register, source pins, observed evidence and limitations | Partial; crosswalk only |
| G-2 Target | Are work and architecture dispositions justified and approved? | ADRs/decision records, process-owner approval, alternatives and risks | Proposed only |
| G-3 Contracts | Are services, interfaces, identities and failure semantics verified? | Approved contracts, runtime bindings and contract/negative tests | Open |
| G-4 Authority | Are AOP permissions, skills, human approval and intervention unambiguous and enforced? | Reconciled normative artefacts and enforcement tests | Open |
| G-5 Integration | Does the pinned AOP toolchain execute reproducibly with traceable evidence? | Gate logs, digests, conformance and replay | Not run |
| G-6 Operational readiness | Can the operation be supported, monitored, recovered and rolled back? | Runbooks, owner acceptance, recovery tests and pilot evidence | Open |
| G-7 Outcome | Is improvement demonstrated against a valid baseline? | Approved metric definitions and independent operational evidence | Not available |

## 6. Acceptance decision rules

- A passed schema or contract test is not proof of runtime deployment.
- A successful AOP run is not proof of business outcome realization.
- A simulated result is not pilot or live operational evidence.
- A pilot is not production approval.
- An active catalogue lifecycle does not override proposed approval status.
- No agent-executed consequential action is accepted without externally enforced authority, recovery and independent outcome verification.
- No performance claim is accepted from the current 40-case fixture.

## 7. Rollback and stop criteria

Stop the affected increment and return to the last accepted operating state if any of the following occurs:

1. An action executes without the required authority or approval.
2. A service call causes an unbounded, duplicate or unreconciled side effect.
3. The agent acts on stale, contradictory or untraceable context.
4. Human pause, termination or revocation cannot be enforced.
5. Case/run/service evidence cannot be correlated or is materially incomplete.
6. Restoration cannot be independently verified.
7. The transition causes material service degradation or loss of operational control.

Rollback must restore the prior routing and authority path, revoke temporary credentials, reconcile any side effects, preserve evidence and notify the accountable operational owner.

## 8. Outstanding decisions and owners

| Decision | Required owner | Evidence required |
|---|---|---|
| Affected customer service and service commitment | Enterprise service owner | Canonical service identity and approved commitment |
| Admitted network line fault-management process | OpenDEA process catalogue owner / process owner | Approved process record or explicit governed gap |
| Actual OSS and external system instances | Enterprise/system owners | Deployment identity, environment and ownership |
| ISF approval and component allocation | OpenDEA ISF owner | Approved records and implementation validation |
| ISS/interface approval and runtime binding | OpenDEA service/interface owners | Approval, endpoint/provider identity and contract tests |
| Dispatch and escalation authority precedence | AOP programme owner and operations authority | Reconciled SOP/manifest and conformance tests |
| Missing action skill bindings | AOP programme owner | Skill/tool contract and registry/conformance evidence |
| Case timestamp/cycle-time semantics and corrected corpus | AOP Toolkit / Context Graph owners | Versioned source and automated quality gate |
| Metric semantics and baseline | AOP and OpenDEA Metrics owners | Approved measure definition and independently reproducible values |
| Reference integration and replay | AOP programme / integration lead | Pinned reproducible execution evidence |

## 9. Current transition recommendation

Authorize planning and evidence remediation for I-00 and I-01 only. Do not authorize service integration, consequential agent execution or pilot activity until their respective gates are met. The manual/established operational path remains authoritative in the interim.

Acceptance of this plan means acceptance of the proposed sequence as a planning baseline only. Each increment requires its own accountable acceptance decision.
