# AO-WE-001 — Upstream Dependency Handoff and Reconciliation

| Field | Value |
|---|---|
| Identifier | AO-WE-001-UPSTREAM-HANDOFF |
| Version | 0.1.0 |
| Status | Evidence-based coordination handoff; upstream decisions remain with owners |
| Authority | Agentic-Operation |
| Reconciliation date | 2026-11-26 |
| Related assessment | [AO-WE-001 / AO-ATP-003 application](./AO-WE-001-AO-ATP-003-application.md) |
| Dependency register | [AO-ATP-002](../transformation/AO-ATP-002-cross-programme-integration-and-dependency-register.md) |
| Upstream AOP CR | [CR-041](https://github.com/agentic-operating-procedure/aop-governance/blob/main/change-requests/CR-041-fault-management-fixture-and-policy-integrity.md) |

## 1. Purpose and authority

This handoff converts the proposed AO-WE-001 transition increments I-00 and I-01 into concrete cross-programme evidence requests. It records the current inspected state and the minimum evidence required before the worked example can progress.

Agentic-Operation is the integration consumer and transformation-guidance authority. It does not approve, implement or close OpenDEA or AOP change requests. Every upstream owner retains authority over its own models, catalogues, specifications, fixtures, runtime and conformance assets.

This is not a request to create a new OpenDEA Business Process record immediately, nor does it authorize AOP runtime execution.

## 2. Current evidence position

### 2.1 AOP CR-041

The current [AOP governance register](https://github.com/agentic-operating-procedure/aop-governance/blob/main/docs/cr-register.md) records CR-041, “Restore fault-management fixture integrity and execution-policy consistency”, as **Proposed**.

The CR identifies six material work areas: case/event semantics; procedure branch semantics; authority and human escalation; permitted-action/skill coverage; deterministic validation; and reproducible conformance/replay.

The following implementation PRs are confirmed merged in `agentic-operating-procedure/aop-toolkit`:

| PR | Merged change | What it establishes | What it does not establish |
|---|---|---|---|
| [#1](https://github.com/agentic-operating-procedure/aop-toolkit/pull/1) | Cycle-time diagnostic validator and regression tests | A deterministic check for timezone-aware case boundaries, non-negative elapsed duration and declared cycle-time consistency; tests exercise the validator | It does not adjudicate event timestamp semantics, step ordering, procedure branches or fix the current source corpus |
| [#2](https://github.com/agentic-operating-procedure/aop-toolkit/pull/2) | Generated case elapsed-boundary correction | The generator now derives `ended_at` from `started_at + cycle_time`, including hour-boundary behaviour; generator regression tests are present | It does not regenerate or replace the checked-in source corpus, and it does not resolve the event chronology or authority defects |

**Source corpus remains unreconciled.** The current checked-in `fixtures/cases/fault-management-cases.jsonl` was fetched from the AOP Toolkit default branch and retains blob SHA `942587be2a79dba480208d490a9d7767911426f8`. It contains 40 cases. A direct check of that exact file revision found:
- 40/40 cases have at least one step timestamp outside the declared start/end interval;
- 36/40 cases have non-monotonic step timestamps in listed order;
- 40/40 declared `outcome.cycle_time` values differ from elapsed `ended_at - started_at` under the validator's declared elapsed-duration interpretation.

These are checks of the current fixture revision, not a claim that all events must be bounded by case start/end. CR-041 itself requires the domain owners to adjudicate event classes, capture order, procedural order, concurrency and boundary semantics before deciding which exceptions are valid.

No merged implementation evidence was found in the inspected AOP context-graph, reference-harness or conformance repositories for the remaining CR-041 requirements. This is a bounded repository inspection, not proof that no work exists outside the inspected default branches.

### 2.2 OpenDEA process alignment

The live canonical process catalogue is [technehub-labs/dea-catalog-business-processes](https://github.com/technehub-labs/dea-catalog-business-processes), not the former `dea-catalog-processes` repository name.

The current candidate records include:

| Record | Canonical ID | Current lifecycle | Scope |
|---|---|---|---|
| Operate Technology Platforms | `processes:process-eo-operate-4njp7b` | candidate | Operate installed technology platforms and meet availability targets |
| Respond to Platform Incidents | `processes:activity-eo-operate-ua7tgk` | candidate | Triage, work around and restore platform incidents within the parent process |

The L2 Process record identifies the Enablement & Operations Process Owner as confirmed through GOV-002. That owner confirmation does not promote the record from candidate to admitted/canonical status, nor does it establish that the record governs telecom network line fault management. The child Activity is also candidate and is expressly scoped to platform incidents.

These are adjacent records, not valid substitutes for the missing network line fault-management Business Process. Do not bind the AOP fixture to either record merely to close its process gap.

The OpenDEA owner request is therefore a **disposition**, not a predetermined record-creation request:
1. confirm whether the scenario represents enterprise IT/platform incident management, telecom network fault management, or a deliberately bounded interaction across both;
2. identify the accountable process owner and applicable ECF/process context;
3. determine whether an existing admitted Business Process governs the work;
4. if none does, decide through the Business Process catalogue's governance whether a new candidate record is warranted;
5. preserve the distinction between a candidate record, an admitted record and an enterprise-specific process implementation.

### 2.3 Information Systems mappings

AO-WE-001's existing Information Systems crosswalk remains a catalogue-level mapping, not runtime binding evidence. In particular:
- ISF records for alarm collection, alarm correlation, dispatch, inventory maintenance and SLA degradation are planned/proposed;
- ISS and Integration Interface records for alarm collection, alarm correlation, field dispatch, trouble ticketing and resource inventory are active but proposed for approval;
- the interface records' bound service relationship does not prove deployment, enterprise approval, reachability or runtime availability;
- no verified canonical function/service/interface mapping was established for loopback testing, fault resolution or planning notification.

The current assessment therefore does not authorize callable integrations. The relevant catalogue owners must validate the record state and the enterprise system owners must provide implementation and deployment evidence.

## 3. Upstream work packages and evidence requests

| Work package | Authority / owner | Required decision or implementation | Minimum evidence returned to integration |
|---|---|---|---|
| U-01 — AOP CR-041 acceptance and coordination | AOP programme owner; `aop-governance` | Accept, revise or reject CR-041; maintain a repository-by-repository implementation/closure ledger | Approved CR status, assigned owners, dependency order and links to scoped PRs |
| U-02 — Case and event semantics | `aop-context-graph`, consulted by `aop-evaluation` | Define timestamp timezone/boundary semantics, event classes, event order versus procedure order, concurrency and duration meaning | Normative/schema reference, decision record, examples for valid pre-run/post-run/concurrent events |
| U-03 — Fixture and validator | `aop-toolkit` | Regenerate or correct the 40-case corpus only after U-02 adjudication; extend validation for all agreed invariants; pin corpus digest | Corrected corpus, source provenance, digest, validator version, positive/negative tests and clean validator output |
| U-04 — SOP and procedure branches | `aop-toolkit`, domain process owner; `aop-spec` only if normative structure is insufficient | Resolve whether dispatch-before-resolution is a valid branch, parallel activity or defect; represent explicit branch/precedence semantics | Owner-approved branch model, revised SOP/fixture, branch-positive and branch-negative tests |
| U-05 — Authority and human escalation | `aop-toolkit`, `aop-reference-harness`; `aop-spec`/`aop-conformance` only where a contract gap exists | Reconcile dispatch minimum authority, threshold rules, priority-customer/outage conditions and human on-call handoff; fail closed on conflict | Consistent SOP/manifest, externally enforced policy, tests for approval, denial, expiry, revocation, altered payload and human handoff |
| U-06 — Permitted action and skill coverage | `aop-toolkit`; `aop-spec`/`aop-conformance` if required | Bind each executable permitted action to a governed skill/tool contract or remove it from executable permissions | Versioned skill/tool identity, input/output contract, credential class, scope, side-effect classification, authority and evidence obligations; negative tests |
| U-07 — Conformance and replay | `aop-conformance`, `aop-reference-harness`, `aop-registry` | Add missing positive/negative checks and run the documented multi-repository reference gate against pinned corrected inputs | Reproducible logs, commit/content digests, conformance report, replay evidence and explicit fixture/test/live classification |
| U-08 — Process disposition | Business Process catalogue owner and accountable process owner | Decide whether existing admitted process applies or whether a new candidate record should be proposed | Written owner disposition; canonical ID and record version if an existing process is accepted; otherwise a governed CR decision |
| U-09 — System and service realization | Relevant OpenDEA Information Systems catalogue owners and enterprise system/service owners | Validate catalogue lifecycle/approval and bind records to actual enterprise systems, providers, consumers and deployments | Canonical IDs, record versions, approved status, system/deployment identity, contract tests, operational owner and availability evidence |
| U-10 — Metric semantics | OpenDEA Metrics catalogue owner with AOP evaluation owner | Reconcile p50 versus arithmetic mean, recovery versus restoration subject, first-pass measure and case denominator/window | Approved metric identity/version or explicit unresolved gap; formula, unit, population, exclusions and reproducible calculation |

## 4. Integration-side acceptance gates

Agentic-Operation will not revise the current proposed architecture dispositions to approved decisions until the following evidence is returned:

| Gate | Required evidence | Current status |
|---|---|---|
| AO-G1 — Intent and process authority | Named scenario/service owner, affected service and service commitment, process owner and process disposition | Open |
| AO-G2 — Semantic identity | Canonical process and Information Systems references with versions, or explicit owner-approved unresolved gaps | Partial; several catalogue anchors exist, but process and runtime bindings remain unresolved |
| AO-G3 — Case integrity | Adjudicated event semantics, corrected/preserved exceptions, current corpus digest and full validator pass | Open; generator and diagnostic validator changes merged, source corpus remains unchanged and failing |
| AO-G4 — Procedure and authority | Approved SOP branch model, consistent dispatch/escalation policy and externally enforced human handoff | Open; CR-041 remains Proposed |
| AO-G5 — Executable action coverage | Every executable action has a governed skill/tool binding and negative permission tests | Open |
| AO-G6 — Runtime and replay | Pinned multi-repository reference gate, reproducible logs, conformance and replay evidence | Not demonstrated |
| AO-G7 — Outcome and measurement | Approved service restoration definition and valid metric baseline with provenance | Open; current fixture is not a performance baseline |

Passing AO-G3 to AO-G6 establishes reference-fixture integrity and reference execution only. It does not establish live service integration, production readiness or improved enterprise outcomes.

## 5. Interim operating constraints

Until the upstream evidence is accepted:
- keep AO-WE-001 classified as an architecture crosswalk and proposed assessment;
- keep all fixture values classified as reference data unless independently attested collection provenance is supplied;
- do not calculate or publish MTTR, p50, first-pass or business-value improvements from the current corpus;
- do not treat candidate OpenDEA process records as canonical substitutes;
- do not treat planned/proposed Information System Functions or proposed service/interface approval as callable authorization;
- do not authorize agent-executed dispatch, fault resolution, loopback testing, planning notification or inventory writes;
- retain human operational authority and the established operational path.

## 6. Reconciliation protocol

When upstream changes land, the integration lead must:
1. fetch the merged CR and PRs from the owning repositories;
2. verify the changed artefacts on their default branches and capture commit/blob SHAs;
3. execute or inspect the relevant deterministic checks and distinguish tests of the validator from validation of the source corpus;
4. update the evidence register with exact before/after revisions and outcomes;
5. revise only the affected architecture/work dispositions;
6. rerun relative-link, cross-reference and consistency checks;
7. retain unresolved decisions explicitly.

No status is advanced on the basis of a PR title, a planned change, a README statement or a successful unit test that does not exercise the actual fixture and contract.
