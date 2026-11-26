# AO-WE-001 — Architecture Disposition Decision Register

| Field | Value |
|---|---|
| Identifier | AO-WE-001-REG-ARCH |
| Status | Proposed dispositions for owner review; no upstream decision approved |
| Method | AO-ATP-003 Architecture Disposition Decision |
| Assessment | [AO-WE-001 / AO-ATP-003 application](./AO-WE-001-AO-ATP-003-application.md) |
| Date | 2026-11-26 |

These records are assessment-level recommendations. They are not formal ADRs for OpenDEA, AOP or an enterprise implementation. A material implementation decision must be transferred to the governance process and authority that owns the affected system or contract.

## Decision summary

| ID | Responsibility | Proposed disposition | Status | Decision authority |
|---|---|---|---|---|
| AD-01 | Alarm collection and correlation | Retain; verify implementation and contract | Proposed | OSS/service owner with OpenDEA ISF/ISS owners |
| AD-02 | Agent consumption of alarm services | Wrap / agent-enable conditionally | Proposed | Enterprise architecture, service owner, security |
| AD-03 | Loopback-test integration | Unresolved; verify then integrate or introduce | Open | Line-test system owner and OpenDEA catalogue owner |
| AD-04 | Fault-resolution realization | Unresolved; preserve deterministic execution where verified | Open | Fault-management process and system owners |
| AD-05 | Field dispatch service | Retain boundary; agent-enable only behind enforced approval | Proposed | Dispatch owner, operations authority, AOP owner |
| AD-06 | Planning notification | Unresolved; integrate after contract and ownership resolution | Open | Planning service owner |
| AD-07 | Resource inventory service | Retain boundary; defer agent write authority | Proposed | Inventory owner, OpenDEA ISS/interface owner, AOP owner |
| AD-08 | Trouble-ticket record | Retain candidate system-of-record boundary; verify | Proposed | Ticketing service owner |
| AD-09 | End-to-end coordination | Agentic overlay over deterministic services, conditional | Proposed | Enterprise architecture, process owner, AOP owner |
| AD-10 | Event and metric evidence pipeline | Remediate data and semantic contract before use | Required prerequisite | AOP Toolkit/Context Graph and OpenDEA Metrics owners |

## AD-01 — Retain alarm collection and correlation responsibilities

- **Outcome:** provide timely, trustworthy alarm context for fault diagnosis.
- **Evidence:** AO-WE-001 identifies Alarm Collection and Alarm Correlation Services and interfaces, and corresponding catalogue components/functions.
- **Constraint:** Information System Function records are planned/proposed; service/interface records are active/proposed. Runtime deployment and approval are unverified.
- **Alternatives:** replace; extract; introduce a new event platform.
- **Proposed decision:** retain the existing responsibility and service boundary pending verification. Do not replace or extract based on the present evidence.
- **Rationale:** there is no evidence of inadequate implementation quality, unacceptable coupling or scaling constraints. The unresolved issue is approval/runtime binding, not demonstrated architectural obsolescence.
- **Verification:** approved catalogue state, provider/consumer identity, contract and schema checks, runtime trace, failure semantics, ownership and SLO.
- **Residual risk:** the named records may not correspond to the actual deployed system.

## AD-02 — Wrap and agent-enable alarm service access conditionally

- **Outcome:** permit bounded agent context retrieval without transferring broad OSS authority.
- **Evidence:** alarm services/interfaces are identified in AO-WE-001; AO-ATP-003 P-01 and P-03 provide applicable patterns.
- **Alternatives:** direct database access; direct broad OSS credentials; replace the service; do not agent-enable.
- **Proposed decision:** if the provider contract and deployment are verified, expose a narrow read-only agent-facing contract or adapter. Enforce workload identity, case scope, rate limits, data filtering, audit and revocation outside the model.
- **Verification:** schema/contract tests, negative authorization tests, case isolation, replay, audit correlation, timeout and failure tests.
- **Residual risk:** a wrapper cannot correct poor source semantics or unreliable provider behaviour.

## AD-03 — Keep loopback-test integration unresolved

- **Outcome:** perform bounded diagnostics without unsafe or untraceable network actions.
- **Evidence:** no matching canonical Information System Function, Service or Interface was verified in AO-WE-001 §5.
- **Alternatives:** infer a mapping from the fixture label; create a local interface; bind directly to an assumed system.
- **Proposed decision:** none until system owner, actual implementation, test semantics, side effects, safe operating envelope and canonical mapping are established.
- **Verification:** approved test contract, test-environment evidence, authorization denial tests, safety interlocks, result provenance and recovery.
- **Residual risk:** diagnosis remains incomplete or manual until this gap is resolved.

## AD-04 — Keep fault-resolution realization unresolved

- **Outcome:** restore service using authorized, verifiable interventions.
- **Evidence:** AO-WE-001 records no direct matching function and incomplete AOP skill binding for resolve-fault.
- **Alternatives:** allow agent-generated commands; infer resolution through a generic tool; preserve all resolution as manual.
- **Proposed decision:** do not authorize agent execution. First identify the actual repair operations and their deterministic controls. Preserve existing verified mechanisms; introduce or refactor only where a justified responsibility gap is demonstrated.
- **Verification:** operation contract, pre/postconditions, side-effect analysis, idempotency, compensation/recovery, human authority and independent restoration check.
- **Residual risk:** the source procedure may not yet distinguish diagnosis, repair selection and repair execution sufficiently.

## AD-05 — Retain dispatch service behind a human approval boundary

- **Outcome:** mobilize field resources only when justified and authorized.
- **Evidence:** Field Dispatch Service/Interface are listed active/proposed; manifest decision-rights ladder says dispatching external resources requires approval, while another authority-map rule labels dispatch autonomous at a threshold.
- **Alternatives:** fully autonomous dispatch; fully manual dispatch; replace dispatch service.
- **Proposed decision:** retain the existing service boundary. Treat dispatch as approval-required until the AOP owner resolves the conflict. The agent may prepare a proposal; an external policy gate must validate named approver, role, exact payload, case context and expiry before invoking dispatch.
- **Verification:** approval, rejection, expiry, revocation, altered payload, wrong role, duplicate request, timeout, acknowledgement and audit tests.
- **Residual risk:** approval workflow may introduce latency; approval must be risk-based and operationally staffed.

## AD-06 — Keep planning notification unresolved

- **Outcome:** provide planning with an accurate, acknowledged handoff.
- **Evidence:** AO-WE-001 does not establish a matching planning-system service or interface.
- **Alternatives:** reuse Customer Impact Notification Service; assume an endpoint; send untracked message.
- **Proposed decision:** do not substitute the external customer-notification contract. Resolve the planning owner, system identity, schema, delivery guarantee, acknowledgement, retry and escalation semantics.
- **Verification:** contract and consumer tests, delivery/acknowledgement evidence, duplicate handling and failure recovery.
- **Residual risk:** downstream planning coordination remains manual or outside the assessed boundary.

## AD-07 — Retain inventory service boundary; defer agent write access

- **Outcome:** maintain accurate resource inventory without unauthorized state mutation.
- **Evidence:** Resource Inventory Service/Interface are listed active/proposed; reconcile-inventory has no explicit skill binding in the manifest.
- **Alternatives:** agent writes directly; agent read-only access; manual reconciliation; replace inventory service.
- **Proposed decision:** retain the service boundary but defer agent write capability. First determine whether the scenario requires read, write or both; establish system of record, reconciliation rules and explicit skill/tool contract.
- **Verification:** read/write scope tests, version/conflict handling, idempotency, reconciliation and audit.
- **Residual risk:** stale inventory may constrain diagnosis until an authoritative read path is verified.

## AD-08 — Retain trouble-ticket record as candidate system-of-record boundary

- **Outcome:** preserve the authoritative case record and operational history.
- **Evidence:** Trouble Ticketing Service/Interface are identified in AO-WE-001.
- **Alternatives:** make agent memory the case record; duplicate state in a new agent store; replace ticketing.
- **Proposed decision:** retain the ticketing boundary pending verification of actual system identity, state model, ownership, approval and deployment. Agents may prepare structured updates; authoritative persistence remains with the governed system of record.
- **Verification:** lifecycle and schema contract, optimistic concurrency, audit history, correlation IDs, duplicate prevention and reconciliation.
- **Residual risk:** ticket state may not capture all evidence needed for replay unless linked to the AOP run record.

## AD-09 — Use agentic coordination as an overlay, not a replacement control plane

- **Outcome:** coordinate context-sensitive work and exceptions while preserving deterministic guarantees.
- **Evidence:** SOP/manifest describe multiple work steps and authority constraints; AO-WE-001 identifies service anchors and unresolved bindings.
- **Alternatives:** fixed workflow only; fully agentic execution; replace OSS; microservice decomposition.
- **Proposed decision:** conditionally introduce an AOP-governed coordination layer only after upstream AOP policy/skill defects and service contract gaps are resolved. Keep identity, policy, approval, safety interlocks, state persistence and audit externally enforced.
- **Verification:** bounded-loop, scenario, adversarial, service-contract, policy-denial, replay, intervention and independent outcome tests.
- **Residual risk:** coordination may increase operational complexity and obscure accountability if observability and ownership are weak.

## AD-10 — Remediate event and metric evidence before measurement

- **Outcome:** make operational performance claims reproducible and semantically valid.
- **Evidence:** AO-WE-001 §8 reports timestamp/order/cycle-time defects in 40 fixture cases; §6 identifies p50/mean mismatch and candidate metrics.
- **Alternatives:** compute metrics from current fixture; ignore malformed events; normalize data silently.
- **Proposed decision:** do not calculate or publish performance from current corpus. AOP owners must clarify field semantics or issue a corrected, versioned corpus; metric owners must approve the statistic, subject, unit, denominator and window.
- **Verification:** automated schema and chronology checks, reconciliation tests, provenance, metric contract and independent recomputation.
- **Residual risk:** no valid baseline exists until the source is repaired and approved.

## Review and change control

Each proposed decision requires a named owner, accepted evidence, alternative review, authority approval, verification plan and review trigger. If accepted, transfer it to the relevant enterprise ADR/CR or upstream OpenDEA/AOP change process. Do not treat this register as approval to change those systems.
