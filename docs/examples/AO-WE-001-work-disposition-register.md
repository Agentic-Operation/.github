# AO-WE-001 — Work Disposition Register

| Field | Value |
|---|---|
| Identifier | AO-WE-001-REG-WORK |
| Status | Proposed work allocation; subject to process, risk and AOP-owner approval |
| Method | AO-ATP-003 Agentic Work Disposition Assessment |
| Assessment | [AO-WE-001 / AO-ATP-003 application](./AO-WE-001-AO-ATP-003-application.md) |
| Date | 2026-11-26 |

This register assesses work, not software components. It must not be read as an AOP manifest, an executable permission list or a change to the source SOP.

## Disposition definitions

- **Human-owned:** accountable human performs the judgment/action.
- **Human-assisted:** tools or agents support a human performer/decision-maker.
- **Agent-assisted:** agent interprets, prepares or recommends; an authorized actor decides or executes.
- **Agent-executed under bounded authority:** agent may execute only within an externally enforced scope and verified recovery/assurance controls.
- **Deterministic automation:** stable, explicit rules are executed by deterministic software.
- **Unresolved:** evidence, authority, service contract or controls are insufficient.

## Work-unit assessment

| ID | Work unit | Proposed disposition | Reason | Preconditions / controls | Status |
|---|---|---|---|---|---|
| W-01 | Receive and correlate alarms | Deterministic automation; agent-assisted explanation | Correlation is a stable system responsibility where rules and source data are defined; agent can assemble context | Verified alarm contract, source provenance, case scoping, deterministic correlation and audit | Conditional |
| W-02 | Assemble case context | Agent-assisted | Cross-source interpretation may benefit from synthesis, but source authority and freshness must remain visible | Read-only access, source/version/timestamp references, contradiction handling, data minimization | Proposed |
| W-03 | Select diagnostic path | Agent-assisted | Agent can compare evidence and propose next diagnostic step; process owner retains policy authority | Approved diagnostic policy, uncertainty handling, bounded alternatives and escalation | Proposed |
| W-04 | Execute loopback test | Unresolved | No verified canonical function/service/interface or test-system identity | Approved test contract, safety envelope, constrained credential, result provenance and recovery | Blocked |
| W-05 | Diagnose likely fault | Agent-assisted | Interpretation can support the engineer but cannot replace accountable diagnosis in ambiguous/high-impact cases | Evidence-linked explanation, uncertainty, independent checks and escalation | Proposed |
| W-06 | Select repair action | Human-owned / agent-assisted | Repair choice may have material service and safety consequences; source action semantics are incomplete | Named authority, approved decision criteria, action impact and alternatives | Proposed |
| W-07 | Execute fault resolution | Unresolved | No verified realization or complete skill/tool binding | Operation contract, preconditions, idempotency, compensation, authorization and independent verification | Blocked |
| W-08 | Decide field dispatch | Human-owned approval; agent-assisted preparation | Source contains conflicting dispatch authority rules; conservative interpretation preserves approval requirement | AOP owner resolves precedence; named supervisor role; external approval enforcement | Blocked pending AOP resolution |
| W-09 | Invoke field dispatch | Deterministic automation after approval | Service invocation should be a controlled, repeatable operation | Approved deployed service, exact-action approval binding, identity, idempotency, acknowledgement and audit | Conditional |
| W-10 | Notify planning | Unresolved; target deterministic delivery after contract resolution | No verified planning destination or service contract | Planning owner, canonical mapping, payload, acknowledgement, retry and escalation semantics | Blocked |
| W-11 | Reconcile inventory | Unresolved; human-supervised until scope is known | Source lists permission but lacks explicit skill binding and read/write distinction | System-of-record decision, scope, governed skill/tool, conflict handling and audit | Blocked |
| W-12 | Verify restoration | Deterministic verification with human exception handling | Outcome must be checked against authoritative network/service state | Defined restoration condition, authoritative telemetry, independent check and exception route | Conditional |
| W-13 | Update and close case record | Deterministic persistence; agent-assisted summary | Case history must be durable and auditable; generated summary is not the system of record | Verified ticket contract, provenance, actor/run correlation, concurrency and audit | Conditional |
| W-14 | Handle exceptions and escalation | Human-owned authority; agent-assisted evidence preparation | Exception judgment and reserved operational authority remain accountable human responsibilities | Named on-call/supervisor roles, unambiguous policy, pause/terminate and escalation paths | Required |

## Explicit non-delegation rules

Until the source AOP defects are resolved and controls are tested:

1. Do not permit autonomous field dispatch.
2. Do not permit agent execution of fault-resolution actions.
3. Do not permit agent write access to inventory.
4. Do not permit loopback test execution through an unverified system binding.
5. Do not permit planning notification through an assumed endpoint.
6. Do not allow the agent to approve its own proposed action or infer approval from silence.
7. Do not treat generated text, a tool success response or ticket closure as proof of restoration.

## Conditions for agent-executed work

No work unit is currently approved for consequential agent execution by this assessment. A future proposal must establish, at minimum:

- a bounded and owned work unit with explicit trigger and completion condition;
- authoritative, current and permitted context;
- a verified service/tool contract and least-privilege workload identity;
- an external policy enforcement point;
- preconditions, postconditions, idempotency and failure/recovery behaviour;
- human approval and intervention paths where consequence requires them;
- independent verification of the intended operational outcome;
- correlated, tamper-evident execution and evidence records;
- negative tests proving that prohibited and out-of-scope actions are denied.

Approval of an AOP artefact or successful conformance test alone does not establish enterprise authority to perform the work.
