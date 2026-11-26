# AO-WE-001 — Discovery and Evidence Register

| Field | Value |
|---|---|
| Identifier | AO-WE-001-REG-EVIDENCE |
| Status | Initial register populated from AO-WE-001; independent runtime discovery not performed |
| Source assessment | [AO-WE-001 / AO-ATP-003 application](./AO-WE-001-AO-ATP-003-application.md) |
| Baseline | [AO-WE-001](./AO-WE-001-fault-management-opendea-aop-worked-example.md) |
| As-of date | 2026-11-26 |

## Evidence classification

- **Repository-declared:** stated in a versioned source document or catalogue record; not independently verified as runtime fact.
- **Source-pinned:** source content is identified by a blob SHA in AO-WE-001 Section 13.
- **Mechanical check:** result of a deterministic comparison over the cited fixture fields.
- **Inference:** assessment derived from source claims; requires owner validation.
- **Proposed target:** future-state recommendation, not current implementation.
- **Unresolved:** required identity, authority, relationship or evidence is absent.

## 1. Outcome and business context

| ID | Assertion | Evidence class | Source / identity | Limitation | Status |
|---|---|---|---|---|---|
| E-001 | Scenario objective is restoration of affected service within maintenance window while minimizing customer impact | Repository-declared | AO-WE-001 §2; SOP RB-LINE-001 | Affected customer service and actual service commitment are not identified | Partially established |
| E-002 | Incident and Problem Management is an active capability record | Source-pinned | Capability v1.0.0; SHA `e717785afa1ea185b8743500ee5bdcf482975078` | Catalogue lifecycle does not prove operational capability effectiveness | Established as catalogue assertion |
| E-003 | Network Monitoring Service is a supporting Business Service | Source-pinned | Service v0.1.0; SHA `e9c6faac0d00bb9bfd9c7f48acd1cb19bb392c26` | Not the customer-facing network service being restored | Established as catalogue assertion |
| E-004 | Exact network line fault-management process has no resolved canonical record in the crosswalk | Repository-declared / unresolved | AO-WE-001 §4.3 | Requires process-catalogue owner decision | Open |

## 2. Architecture inventory and service boundaries

| ID | Assertion | Evidence class | Source / identity | Limitation | Status |
|---|---|---|---|---|---|
| E-010 | OSS is used as system-class context; no canonical System instance resolved | Repository-declared / unresolved | AO-WE-001 §5.1 | No runtime system/deployment identity established | Open |
| E-011 | Fault Management & Service Assurance and Event Correlation components are active catalogue records | Source-pinned | Component SHAs in AO-WE-001 §13 | Catalogue presence does not prove deployment or current responsibility | Catalogue assertion |
| E-012 | Relevant Information System Function records are planned / proposed | Source-pinned | Five ISF records, SHAs in AO-WE-001 §13 | Not approved or proven callable | Open |
| E-013 | Alarm Collection, Alarm Correlation, Field Dispatch, Trouble Ticketing and Resource Inventory services/interfaces are active / proposed | Source-pinned | Service and interface SHAs in AO-WE-001 §13 | Active lifecycle and bound status do not establish approval, deployment, reachability or availability | Open |
| E-014 | Loopback testing, fault resolution and planning notification have no verified function/service/interface mapping | Repository-declared / unresolved | AO-WE-001 §§5.2–5.4 | No substitution by similarly named records permitted without semantic validation | Open |
| E-015 | Fixture application labels are not canonical system identities | Repository-declared | AO-WE-001 §5.4 | Actual system instances and owners remain unknown | Open |

## 3. AOP work and authority

| ID | Assertion | Evidence class | Source / identity | Limitation | Status |
|---|---|---|---|---|---|
| E-020 | SOP sequence contains correlate, test, resolve, dispatch, notify, inventory reconcile, verify and record | Repository-declared | SOP RB-LINE-001; blob `c2774cb7c980cf80090a3e8937eafefb1a526bb9` | Actual enterprise work variants are not independently observed | Fixture scope |
| E-021 | Manifest contains conflicting dispatch authority treatments | Repository-declared | Manifest; blob `dc6ae55243648fce3539ed2571e3e3685358dfc0`; AO-WE-001 §7.2 | Resolution belongs to AOP owner | Open |
| E-022 | On-call escalation semantics conflict between prohibited action and exception route | Repository-declared | AO-WE-001 §7.2 | Human handoff vs automated action distinction not settled | Open |
| E-023 | Resolve-fault and reconcile-inventory are permitted actions without corresponding listed skills | Repository-declared | AO-WE-001 §7.2 | AOP skill registry and executable bindings require owner verification | Open |
| E-024 | Shift supervisor is identified as accountable human authority for approval, pause, termination and exception handling | Repository-declared | AO-WE-001 §7.1 | Actual enterprise delegation and identity are not attested | Proposed authority model |

## 4. Data and outcome evidence

| ID | Assertion | Evidence class | Source / identity | Limitation | Status |
|---|---|---|---|---|---|
| E-030 | Case corpus contains 40 records | Repository-declared | Case fixture; blob `942587be2a79dba480208d490a9d7767911426f8` | Fixture only | Established as fixture size |
| E-031 | 36/40 cases contain events later than ended_at | Mechanical check | AO-WE-001 §8 | Field semantics could differ only if explicitly specified | Fails current interpretation |
| E-032 | 35/40 cases contain events earlier than started_at | Mechanical check | AO-WE-001 §8 | Same semantic qualification | Fails current interpretation |
| E-033 | 36/40 cases have non-monotonic step event timestamps | Mechanical check | AO-WE-001 §8 | Same semantic qualification | Fails current interpretation |
| E-034 | All 40 cases have outcome.cycle_time different from ended_at minus started_at | Mechanical check | AO-WE-001 §8 | Units and cycle-time semantics need explicit definition | Fails current interpretation |
| E-035 | Fixture declares p50 recovery baseline of 84 minutes and first-pass fix rate of 0.91 | Repository-declared | AO-WE-001 §6.2 | Not independently recalculated from invalid corpus | Not a validated baseline |
| E-036 | p50 recovery time is not semantically equivalent to admitted arithmetic-mean MTTR | Semantic comparison | AO-WE-001 §6.1 and metric source pin | Requires metric owner confirmation for any alternative mapping | Mismatch established |
| E-037 | Reference harness gate was not run for this integration | Repository-declared | AO-WE-001 §§1, 10–11 | No execution evidence supplied | Not run |
| E-038 | No end-to-end enterprise outcome evidence exists in this example | Repository-declared | AO-WE-001 §10 WE-12 | Requires live, traceable enterprise evidence | Absent |

## 5. Unresolved relationship register

| Gap | Missing or unverified relationship | Why it matters | Required evidence / owner |
|---|---|---|---|
| G-001 | Outcome ↔ affected customer-facing network service / service commitment | Defines restoration success and service impact | Service identity, owner and SLA/commitment; enterprise service owner |
| G-002 | Scenario ↔ admitted network line fault-management process | Establishes approved work semantics and ownership | Process disposition and canonical ID; OpenDEA process catalogue owner |
| G-003 | OSS label ↔ actual System instance and deployment | Required for operational binding and security scope | System identity, environment, owner and deployment evidence |
| G-004 | ISF ↔ approved implementation and executing component | Planned/proposed records are not callable contracts | Approved records, allocation review and implementation verification; OpenDEA ISF owner |
| G-005 | ISS/interface ↔ deployed provider, consumer and runtime contract | Catalogue binding is not runtime proof | Approval, endpoint identity, contract tests, telemetry; service/interface owners |
| G-006 | Loopback test ↔ canonical function/service/interface | Required before diagnostic tool access | Semantic and implementation crosswalk; system owner |
| G-007 | Fault resolution ↔ executable operation and skill | Consequential side effects are undefined | Action semantics, preconditions, compensation, skill/tool contract; AOP owner |
| G-008 | Planning notification ↔ target service and acknowledgement | Handoff completion cannot be inferred | Planning owner, schema, delivery and acknowledgement semantics |
| G-009 | Inventory reconciliation ↔ read/write authority and system of record | Potentially consequential data mutation | Ownership, action scope, skill binding and reconciliation rules |
| G-010 | Dispatch decision ↔ one enforceable authority rule | Prevents unauthorized dispatch | Reconciled SOP/manifest and positive/negative conformance tests; AOP owner |
| G-011 | Case event fields ↔ declared temporal semantics | Prevents invalid chronology and measurement | Corrected fixture or normative field semantics; AOP Context Graph / Toolkit owners |
| G-012 | Metric name ↔ statistic, subject, unit, denominator and window | Prevents false comparison | Metric contract and admitted mapping; OpenDEA Metrics / AOP owners |
| G-013 | Run ↔ pinned artefacts, decisions, approvals and outcomes | Establishes replay and accountability | Versioned run manifest, digests, logs and trace correlation; AOP/integration owners |

## 6. Evidence use restrictions

1. Source-pinned catalogue records establish what the reviewed source records declared at the inspected revision, not current deployment.
2. The case corpus is a reference fixture only and must not be used to calculate performance or business value until defects and field semantics are resolved.
3. The stated 84-minute p50 and 0.91 first-pass values are fixture declarations, not independently verified measurements.
4. Proposed architecture and work dispositions are assessment outputs, not approved decisions.
5. No production, pilot, live operational, safety or customer outcome evidence is asserted by this register.
