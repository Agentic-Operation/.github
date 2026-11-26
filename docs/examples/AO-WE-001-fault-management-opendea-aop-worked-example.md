# AO-WE-001 — Fault Management: OpenDEA–AOP Worked Example

| Field | Value |
|---|---|
| Identifier | AO-WE-001 |
| Title | Fault Management: OpenDEA–AOP Worked Example |
| Version | 0.1.0 |
| Status | Proposed reference example; architecture crosswalk complete, execution not yet validated |
| Authority | Agentic-Operation |
| Classification | Non-normative implementation artefact |
| Parent guidance | [AO-ATP-001](../transformation/AO-ATP-001-enterprise-architecture-and-service-delivery-transformation-playbook.md) |
| Integration register | [AO-ATP-002](../transformation/AO-ATP-002-cross-programme-integration-and-dependency-register.md) |
| Reconciliation date | 2026-11-26 |

## 1. Purpose and scope

This worked example takes the line fault-management SOP and reference AOP fixture maintained by the Agentic Operating Procedure (AOP) programme and maps it to existing OpenDEA enterprise and Information Systems catalogue records.

It is the first concrete integration artefact for demonstrating how an enterprise operating model, business architecture, information-systems architecture, operational procedure, agent skills, human authority and outcome evidence fit together.

This is an architecture and evidence crosswalk. It does not modify or replace:
- OpenDEA's normative metamodel, root architecture model or catalogue records;
- AOP's normative specification, toolkit, manifest, skills, harness, registry or conformance contracts;
- the enterprise's actual operational procedures, authority delegations or service contracts.

The source fixture is a reference scenario, not an attested production deployment. The case corpus has material data-quality defects (Section 8), and the AOP reference execution gate was not run as part of this work. Consequently, this document does not claim a validated runtime integration or measured enterprise improvement.

## 2. Scenario and intended business outcome

The source SOP is `RB-LINE-001: Line Fault Management Procedure`. Its objective is to restore affected service for a reported line fault within the maintenance window while minimizing customer impact. Its stated outcome is that the fault is correlated, diagnosed and either resolved or dispatched to a field crew, with the resolution recorded against the fault ticket.

The operational sequence in the SOP and observed-case fixture is:

1. Correlate alarms.
2. Perform a loopback test.
3. Resolve the fault where possible.
4. Dispatch a field crew where required.
5. Notify planning.
6. Reconcile inventory where the case requires it.
7. Verify restoration and preserve the case record.

The enterprise outcome should be expressed independently of the software actions:

> Restore the affected network service within the applicable service window, minimize customer and operational impact, and preserve a verifiable record of diagnosis, authorization, intervention and restoration.

This statement is a scenario-level outcome formulation for the worked example. It is not a new OpenDEA catalogue record.

## 3. Source artefacts and identity

| Source artefact | Repository path | Observed revision |
|---|---|---|
| Source SOP | [aop-toolkit/fixtures/sop/rb-line-001.md](https://github.com/agentic-operating-procedure/aop-toolkit/blob/main/fixtures/sop/rb-line-001.md) | Blob `c2774cb7c980cf80090a3e8937eafefb1a526bb9` |
| Governance manifest | [aop-toolkit/fixtures/manifests/fault-management.json](https://github.com/agentic-operating-procedure/aop-toolkit/blob/main/fixtures/manifests/fault-management.json) | Blob `dc6ae55243648fce3539ed2571e3e3685358dfc0` |
| Observed-case fixture | [aop-toolkit/fixtures/cases/fault-management-cases.jsonl](https://github.com/agentic-operating-procedure/aop-toolkit/blob/main/fixtures/cases/fault-management-cases.jsonl) | Blob `942587be2a79dba480208d490a9d7767911426f8` |
| Toolkit implementation | [aop-toolkit](https://github.com/agentic-operating-procedure/aop-toolkit) | README declares v0.3.0 Stable |
| Reference harness | [aop-reference-harness](https://github.com/agentic-operating-procedure/aop-reference-harness) | README declares v0.5.0 Stable |
| Conformance programme | [aop-conformance](https://github.com/agentic-operating-procedure/aop-conformance) | Published certificates reviewed in AO-ATP-002 |

The AOP artefacts must be referenced by repository, path, version and content digest in any eventual run record. A branch name or mutable `main` URL alone is not sufficient provenance for a governed execution.

## 4. Enterprise architecture context

### 4.1 Business capability

**Catalogue lifecycle:** active

**Incident and Problem Management**

- Canonical ID: `capabilities:capability-incident-and-problem-management-c2wk96`
- Version: 1.0.0
- Lifecycle: active
- Repository: [dea-catalog-business-capabilities](https://github.com/technehub-labs/dea-catalog-business-capabilities)
- Record: [capabilities-capability-incident-and-problem-management-c2wk96.yaml](https://github.com/technehub-labs/dea-catalog-business-capabilities/blob/main/entities/v1-alpha/incident-and-problem-management-c2wk96/capabilities-capability-incident-and-problem-management-c2wk96.yaml)
- Blob: `e717785afa1ea185b8743500ee5bdcf482975078`

The capability is a suitable enterprise ability anchor: it covers detecting, triaging and resolving incidents and learning from problems to minimize service disruption and address root causes. It is not a process, an ITSM tool or an agent.

### 4.2 Business service context

**Network Monitoring Service**

- Canonical ID: `services:service-network-monitoring-swe8ps`
- Version: 0.1.0
- Lifecycle: active
- Repository: [dea-catalog-business-services](https://github.com/technehub-labs/dea-catalog-business-services)
- Record: [services-service-network-monitoring-swe8ps.yaml](https://github.com/technehub-labs/dea-catalog-business-services/blob/main/entities/v1-alpha/n/network-monitoring-swe8ps/services-service-network-monitoring-swe8ps.yaml)
- Blob: `e9c6faac0d00bb9bfd9c7f48acd1cb19bb392c26`

This is a relevant supporting business service: it collects network telemetry, correlates faults against configuration data and pages on-call engineers. It references the Incident and Problem Management capability.

It must not be misrepresented as the customer-facing network service being restored. The actual affected customer service and its service-level commitment are not identified by the AOP fixture and remain unresolved in this crosswalk.

### 4.3 Business process context

The business process catalogue contains an adjacent, but not equivalent, process structure:

| Element | Canonical ID | Lifecycle | Meaning |
|---|---|---|---|
| Process: Operate Technology Platforms | `processes:process-eo-operate-4njp7b` | candidate | Broad platform operation with availability targets |
| Activity: Respond to Platform Incidents | `processes:activity-eo-operate-ua7tgk` | candidate | Groups work that triages, works around and restores platform incidents |
| Activity task: Respond to Platform Incidents Verification | `processes:task-eo-operate-verify-sfqm5w` | candidate | Verifies the incident input against the activity specification |
| Activity task: Respond to Platform Incidents Processing | `processes:task-eo-operate-transform-crz922` | candidate | Performs the response and preserves intermediate evidence |

Repository: [dea-catalog-business-processes](https://github.com/technehub-labs/dea-catalog-business-processes).

The parent process and child activity are both candidate records, and their scope is general technology-platform incidents. They are useful as a structural comparison and process-decomposition reference, but they are not an admitted, network-line-fault-management process. They must not replace the explicit process gap in the AOP fixture.

**Process conclusion:** the exact network line fault-management process remains unresolved. The owning process catalogue must determine whether to extend an existing admitted process, admit a specialization, or create a new process through its governance method. Agentic-Operation must not invent the canonical process ID.

## 5. Information Systems architecture crosswalk

### 5.1 System and component boundary

The catalogue records describe the generic **Telecom Operations Support System (OSS)** system class and its sub-systems. This review did not resolve a separate canonical `System` instance record for the OSS. The worked example therefore uses the OSS label as the system-class context and references the verified component records below; it does not manufacture a System ID.

The metamodel defines `InformationSystemComponent` as an abstract kind. `ApplicationComponent` is a concrete specialization of it. The catalogue records use `type: ApplicationComponent`, which is consistent with that metamodel specialization.

| Component | Canonical ID | Catalogue status |
|---|---|---|
| Fault Management & Service Assurance | `dea:information-system-component-telecom-operations-support-system-oss-fault-management-service-assurance` | active |
| Event Correlation Component | `dea:information-system-component-telecom-operations-support-system-oss-fault-management-service-assurance-event-correlation-component` | active |
| Network Inventory & Topology | `dea:information-system-component-telecom-operations-support-system-oss-network-inventory-topology` | Present in component catalogue; verify its detailed record before runtime binding |

Repository: [dea-catalog-application-components](https://github.com/technehub-labs/dea-catalog-application-components).

The Event Correlation Component is a child of Fault Management & Service Assurance. The Information System Function records for alarm collection, alarm correlation and field-team dispatch all currently point to the Event Correlation Component as their executing component. This is what the records declare; the functional allocation should be reviewed by the Information Systems catalogue owner before it is treated as an implementation fact, particularly for field dispatch.

### 5.2 Information System Functions

The following canonical Information System Function records provide direct functional anchors:

| AOP step or context | OpenDEA function | Canonical ID | Lifecycle / approval |
|---|---|---|---|
| Collect incoming network alarms | Collect alarms and events from network elements | `dea:information-system-function-telecom-operations-support-system-oss-fault-management-service-assurance-collect-alarms-and-events-from-network-elements` | planned / proposed |
| Correlate alarms | Correlate alarms into service incidents | `dea:information-system-function-telecom-operations-support-system-oss-fault-management-service-assurance-correlate-alarms-into-service-incidents` | planned / proposed |
| Dispatch field teams | Dispatch field teams for network repairs | `dea:information-system-function-telecom-operations-support-system-oss-fault-management-service-assurance-dispatch-field-teams-for-network-repairs` | planned / proposed |
| Reconcile inventory | Maintain network resource inventory | `dea:information-system-function-telecom-operations-support-system-oss-network-inventory-topology-maintain-network-resource-inventory` | planned / proposed |
| Assess service degradation | Track service degradation against SLAs | `dea:information-system-function-telecom-operations-support-system-oss-fault-management-service-assurance-track-service-degradation-against-slas` | planned / proposed |

Repository: [dea-catalog-system-functions](https://github.com/technehub-labs/dea-catalog-system-functions). The catalogue is still under its legacy repository name; its canonical rename target is recorded in OpenDEAM.

These records are structurally useful, but their `lifecycle_status: planned` and `governance.approval_status: proposed` mean they must not be treated as approved, deployed or callable system functions.

No directly matching Information System Function was identified in this pass for:
- loopback testing;
- the resolution action itself;
- notifying a planning system.

Those mappings remain unresolved. A similarly named action or service must not be substituted without semantic and ownership validation.

### 5.3 Information System Services and Integration Interfaces

The Information System Service records distinguish service contracts from the components that provide them. Their corresponding Integration Interface records distinguish the interaction boundary from the service contract and from any API specification.

| AOP activity | Information System Service | Service lifecycle / approval | Bound Integration Interface | Interface lifecycle / approval |
|---|---|---|---|---|
| Collect alarms | Alarm Collection Service — `dea:information-system-service-telecom-operations-support-system-oss-fault-management-service-assurance-alarm-collection` | active / proposed | `dea:integration-interface-telecom-operations-support-system-oss-fault-management-service-assurance-alarm-collection` | active / proposed |
| Correlate alarms | Alarm Correlation Service — `dea:information-system-service-telecom-operations-support-system-oss-fault-management-service-assurance-alarm-correlation` | active / proposed | `dea:integration-interface-telecom-operations-support-system-oss-fault-management-service-assurance-alarm-correlation` | active / proposed |
| Dispatch field crew | Field Dispatch Service — `dea:information-system-service-telecom-operations-support-system-oss-fault-management-service-assurance-field-dispatch` | active / proposed | `dea:integration-interface-telecom-operations-support-system-oss-fault-management-service-assurance-field-dispatch` | active / proposed |
| Open/track fault ticket | Trouble Ticketing Service — `dea:information-system-service-telecom-operations-support-system-oss-fault-management-service-assurance-trouble-ticketing` | active / proposed | `dea:integration-interface-telecom-operations-support-system-oss-fault-management-service-assurance-trouble-ticketing` | active / proposed |
| Reconcile inventory | Resource Inventory Service — `dea:information-system-service-telecom-operations-support-system-oss-network-inventory-topology-resource-inventory` | active / proposed | `dea:integration-interface-telecom-operations-support-system-oss-network-inventory-topology-resource-inventory` | active / proposed |

Repositories:
- [dea-catalog-information-system-services](https://github.com/technehub-labs/dea-catalog-information-system-services)
- [dea-catalog-integration-interfaces](https://github.com/technehub-labs/dea-catalog-integration-interfaces) (legacy repository name; canonical rename target is recorded in OpenDEAM)

The services declare published contracts and `lifecycle_status: active`; their governance records still state `approval_status: proposed`. The interfaces declare `service_binding.binding_status: bound` and REST API or streaming interaction patterns, but also retain proposed approval status. These fields must be read together. An active catalogue lifecycle or published contract is not proof that the service is deployed, approved for this enterprise, reachable or available at runtime.

The interface is not an API. The API contract, if one is used to specify an interface, is a separate entity. No API record has been bound in this worked example.

### 5.4 Application-label crosswalk and unresolved boundaries

| AOP fixture label | Proposed interpretation | Mapping status | Constraint |
|---|---|---|---|
| `network-monitoring-platform` | OSS alarm collection and correlation functions/services | Partial | The label is not itself a canonical System ID; resolve actual system and deployment identity |
| `line-test-system` | Loopback-test execution system | Unresolved | No corresponding canonical function/service/interface was verified |
| `dispatch-system` | OSS Field Dispatch Service and Field Dispatch Interface | Partial | Service contract exists; actual dispatch platform/system instance and approval remain unverified |
| `planning-system` | Planning notification endpoint | Unresolved | No matching planning-system service/interface was established |
| `customer-master` | Customer-tier source | Unresolved | No canonical source system, service or interface bound in this example |
| `inventory-system` | OSS Resource Inventory Service and Interface | Partial | Service contract exists; the specific system instance and operational availability remain unverified |

The Network Monitoring Service is a Business Service, not the system behind the `network-monitoring-platform` application label. Likewise, Customer Impact Notification Service is explicitly an external-customer notification contract; it is not a substitute for the AOP's internal `planning-system` handoff.

## 6. Metric and outcome alignment

### 6.1 Existing catalogue records

| AOP metric reference or baseline | OpenDEA record | Lifecycle | Alignment |
|---|---|---|---|
| `mttr-p50-minutes` | Mean Time to Recovery — `dea:metric-mean-time-to-recovery` | admitted | Not equivalent: OpenDEA defines arithmetic mean recovery time in minutes; AOP fixture names a p50 statistic |
| `mean-time-to-detect` | Mean Time to Detect — `dea:metric-mean-time-to-detect` | candidate | Candidate only; not an admitted canonical metric |
| `ai-incident-escalation-compliance` | AI Incident Escalation Compliance — `dea:metric-ai-incident-escalation-compliance` | candidate | Candidate only |
| `first-pass-fix-rate` | First-Pass Anomaly Resolution (RAN Operations) — `dea:metric-first-pass-anomaly-resolution-ran-operations` | candidate | Related concept, not admitted and not yet proven semantically equivalent |

Repository: [dea-catalog-metrics](https://github.com/technehub-labs/dea-catalog-metrics).

### 6.2 Metric binding rules

- Do not bind the AOP's p50 recovery-time baseline to the admitted arithmetic-mean metric. Mean and median/p50 are different statistics.
- Do not treat candidate metrics as admitted or canonical measures.
- Preserve the metric's subject, unit, statistic, denominator, observation window and directionality.
- The AOP's baseline values (84 minutes p50 and 0.91 first-pass fix rate) are fixture declarations, not values independently recalculated from the case corpus.
- The 40-case corpus must be repaired and its measurement definitions clarified before it is used to establish a baseline or calculate improvement.

The owning metric catalogue and AOP programme should decide whether to adopt an existing admitted measure with compatible semantics, submit a new metric contribution, or revise the AOP baseline definition. Agentic-Operation does not make that semantic decision on their behalf.

## 7. AOP authority and execution mapping

The AOP is the operational specification for the work. It is not a prompt and it is not the system architecture. Its governance manifest separates actions, skills, context, authority, coordination, control and assurance.

### 7.1 Intended decision model

| Activity | Proposed authority treatment from fixture | Required external enforcement |
|---|---|---|
| Read and correlate alarms | Autonomous, read-only | Monitoring-read credential scoped to one case |
| Perform loopback test | Autonomous within approved diagnostic scope | Line-test credential limited to test actions |
| Resolve fault | Not fully specified | Explicit skill, tool and authority definition required |
| Dispatch field crew | Approval-required where threshold or priority/outage conditions apply | Dispatch-write credential issued only after valid approval |
| Notify planning | Intended as permitted action | Planning-write credential and acknowledgement evidence |
| Reconcile inventory | Listed as permitted | Missing explicit skill binding; define whether this is read-only or write-capable |

The shift supervisor remains an accountable human authority for approval, pause, termination and exception handling. The agent can assemble evidence and recommend an action; it cannot confer authority on itself.

### 7.2 Source policy inconsistencies requiring AOP-owner resolution

The current SOP and manifest contain material policy conflicts:

1. **On-call escalation:** the SOP marks `engage-on-call-engineer` as prohibited under the three-failed-loopback condition, but its Exceptions section says to escalate to the on-call engineer. The manifest also marks the action prohibited while defining an on-call-engineer escalation route for unknown authority. The AOP owner must distinguish a prohibited automated action from a permitted human escalation/handoff, if that is the intended meaning.
2. **Dispatch authority:** the manifest's decision-rights ladder says dispatching external resources requires at least approval-required authority. However, the authority map labels dispatch autonomous when `mttr_estimate <= 120`. These rules conflict and need a single precedence/decision rule.
3. **Skill coverage:** `resolve-fault` and `reconcile-inventory` appear in `permitted_actions`, but no corresponding skills are listed in the manifest. Every executable action needs an explicit skill/tool binding, or must remain unavailable.
4. **Action ordering:** the SOP's sequence lists resolution before dispatch, while the fixture cases often show dispatch before resolution. The intended branch logic should explicitly model whether dispatch is a fallback after diagnosis or a parallel/alternative path.

These are upstream AOP governance and specification issues. This document records them; it does not resolve or alter the normative source artefacts.

## 8. Case-corpus quality assessment

The source corpus contains 40 JSONL case records. A direct structural check of the current file found:

| Check | Cases affected | Result |
|---|---:|---|
| At least one event timestamp later than `ended_at` | 36 / 40 | Fails basic interval consistency |
| At least one event timestamp earlier than `started_at` | 35 / 40 | Fails basic interval consistency |
| Step-array event timestamps are not monotonically ordered | 36 / 40 | Fails event-sequence consistency |
| `outcome.cycle_time` differs from `ended_at - started_at` | 40 / 40 | Fails direct cycle-time reconciliation |

For case `FM-2026-11-0001`:
- `started_at`: 09:01
- `ended_at`: 09:17
- declared interval: 16 minutes
- `outcome.cycle_time`: 76
- final listed event: 09:50
- another event later in the list: 09:55

The event list also places `resolve-fault` after `notify-planning`, while its timestamp is earlier. This is not a valid chronological event sequence under the apparent field semantics.

The checks above are mechanical comparisons of the current fields. If the AOP programme intends different semantics for case boundaries, cycle time or step-array order, those semantics must be explicitly specified and validated. Until then, the corpus is unsuitable for deriving MTTR, p50, cycle-time or first-pass performance claims.

**Disposition:** retain the 40 cases as a reference fixture only. Do not use them as evidence of live enterprise operations, baseline performance, improvement or business value. Request a corrected and versioned corpus from the AOP owner before execution results are used for measurement.

## 9. Integrated architecture and execution view

The intended architecture trace is:

```text
Enterprise outcome
  "Restore affected network service; minimize impact"
          |
          v
Business Capability
  Incident and Problem Management
          |
          +---- supporting Business Service
          |       Network Monitoring Service
          |
          v
Business Process
  Network line fault management
  [unresolved; adjacent platform incident process is candidate]
          |
          v
Observed work / context
  Case corpus + source systems + evidence provenance
  [fixture only; data-quality remediation required]
          |
          v
Agentic Operating Procedure
  RB-LINE-001 -> AP-LINE-001
  [authority and skill conflicts require resolution]
          |
          v
Agent Skills + Domain Harness + Human Authority
  Correlate / Test / Resolve / Dispatch / Notify / Reconcile
          |
          v
Information Systems realization
  OSS components -> IS Functions -> IS Services -> Interfaces
  [catalogue records exist; function approvals and runtime bindings
   remain unverified]
          |
          v
Execution evidence
  Decisions, approvals, invocations, acknowledgements,
  restoration verification, immutable case/run record
          |
          v
Outcome measures
  Recovery time, restoration quality, customer impact,
  repeat incidents, policy compliance
  [metric semantic alignment and valid source data required]
```

The chain is intentionally explicit about unresolved bindings. It is not a claim that every box is deployed or connected.

## 10. Required remediation and ownership

| ID | Finding | Owner | Required action | Closure evidence |
|---|---|---|---|---|
| WE-01 | No admitted network line fault-management Business Process resolved | OpenDEA Business Process catalogue owner | Assess process scope and admit/extend through catalogue governance | Canonical process ID, lifecycle and approved decomposition |
| WE-02 | Adjacent platform incident Process and Activity are candidate | OpenDEA Business Process catalogue owner | Decide whether they remain candidate, are admitted, or are unsuitable for this scenario | Reviewed lifecycle disposition |
| WE-03 | Function records are planned with proposed approval | OpenDEA ISF catalogue owner | Confirm functional semantics, executing component allocation and lifecycle/approval progression | Approved records and conformance evidence |
| WE-04 | Service and interface records are active but approval remains proposed | OpenDEA ISS / Integration Interface owners | Confirm governance approval and deployment-binding expectations | Approved records and verifiable implementation bindings |
| WE-05 | Line-test, planning and customer-master sources are unresolved | OpenDEA architecture/catalogue owners with scenario owner | Resolve actual system, component, function, service and interface identities; do not invent them | Versioned crosswalk with canonical IDs or explicit gaps |
| WE-06 | AOP authority rules conflict | AOP programme owner | Reconcile on-call escalation semantics and dispatch authority precedence | Updated SOP/manifest/AOP with positive and negative conformance tests |
| WE-07 | Permitted actions lack complete skill bindings | AOP programme owner | Bind `resolve-fault` and `reconcile-inventory` to governed skills or remove them from executable permissions | Manifest and skill registry consistency evidence |
| WE-08 | Case timestamps and cycle-time fields fail consistency checks | AOP Toolkit / Context Graph owners | Correct fixture or define field semantics; add deterministic corpus-quality gates | New versioned corpus with all checks passing |
| WE-09 | p50 and arithmetic-mean recovery metrics differ | AOP programme and OpenDEA Metrics catalogue owner | Resolve statistic, subject, unit and denominator before metric binding | Approved metric mapping or new admitted metric |
| WE-10 | First-pass anomaly metric is candidate, not admitted | OpenDEA Metrics catalogue owner with AOP programme | Decide whether to admit, refine or replace the candidate and establish semantic equivalence | Admitted metric and governed mapping |
| WE-11 | Reference harness has not been executed in this integration | AOP programme / Agentic-Operation integration lead | Run the documented multi-repository gate after fixture and policy corrections | Reproducible logs, content digests, certificates and replay record |
| WE-12 | No end-to-end enterprise outcome evidence | Enterprise scenario owner | Connect approved live services and measure outcomes against a validated baseline | Independently traceable operational and business outcome evidence |

Agentic-Operation owns this cross-programme integration artefact and the enterprise operating-model interpretation. It does not own the upstream changes in the AOP or OpenDEA programmes.

## 11. Acceptance criteria for a validated reference example

The worked example may progress from architecture crosswalk to executable reference only when:

1. The network line fault-management process is canonically resolved or its absence is explicitly retained as a governed gap.
2. All system, component, function, service and interface mappings have canonical IDs, versions and lifecycle/approval states.
3. Every AOP action is either bound to a governed skill/tool with explicit authority or excluded from executable permissions.
4. Dispatch and escalation policies have one unambiguous precedence model and enforceable approval checks.
5. The case corpus passes interval, event-order, cycle-time and provenance validation.
6. Metric definitions and baselines use consistent statistic, subject, unit, denominator and observation window.
7. The AOP toolkit and reference harness run successfully in a reproducible workspace, with logs and digests retained.
8. Human approval, rejection, pause, termination and escalation are exercised through an actual human authority path, not only a placeholder.
9. Service invocation and outcome evidence are traceable to the relevant OpenDEA and AOP versions.
10. Fixture, simulated and live enterprise evidence are clearly distinguished.

## 12. Current disposition

**Current status:** architecture crosswalk only

The OpenDEA catalogues contain relevant and useful records for incident management, network monitoring, fault-management functions, components, information-system services and interfaces. This is sufficient to make the worked example concrete rather than hypothetical.

However, the business-process mapping remains candidate/ unresolved, some information-system functions are planned, service/interface approval is proposed, multiple application labels remain unbound, AOP authority and skill coverage need correction, and the case corpus fails basic timestamp and cycle-time consistency checks.

The correct next step is therefore not to claim a completed end-to-end implementation. It is to resolve the upstream semantic, governance and evidence defects, then run the AOP toolchain against a validated scenario and build the replayable integration evidence chain.

The worked example demonstrates how the programmes should connect. It does not certify a production operating environment.


## 13. OpenDEA source-record pins

The following blob SHAs identify the exact catalogue records inspected for this crosswalk. They pin the content used for this analysis; they do not imply deployment or runtime availability.

| Record | Version | Lifecycle / approval | Blob SHA |
|---|---|---|---|
| Incident and Problem Management capability | 1.0.0 | active | `e717785afa1ea185b8743500ee5bdcf482975078` |
| Network Monitoring Service (Business Service) | 0.1.0 | active | `e9c6faac0d00bb9bfd9c7f48acd1cb19bb392c26` |
| Operate Technology Platforms (Business Process) | 1.0.0 | candidate | `844f9175b920ae331bf42c72cf5fca683b8f26e3` |
| Respond to Platform Incidents (Activity) | 1.0.0 | candidate | `13c152401bf16e71e6c1321d6ebff8e1e10e6a34` |
| Respond to Platform Incidents Verification (Task) | 1.0.0 | candidate | `435b95e56d0f51bd14474feb711b684687902884` |
| Respond to Platform Incidents Processing (Task) | 1.0.0 | candidate | `37fefa4b6d34e0922d190d0f94695ebc52f43302` |
| Fault Management & Service Assurance component | 1.0 | active | `644b2e1b333496ad806aa54239050574362090e7` |
| Event Correlation Component | 1.0 | active | `66ca9e3722b1333930104ba0de667f8f56e60a26` |
| Network Inventory & Topology component | 1.0 | active | `01966b880c1051478ee479557baf897e2e1b0574` |
| Collect alarms and events from network elements (ISF) | 1.0.0 | planned / proposed | `4d9bb1d4702e74538cd89409b4d34bac654a0058` |
| Correlate alarms into service incidents (ISF) | 1.0.0 | planned / proposed | `e2e0e96d2dfb7e7f6055e4178f94ff1b44a1f4bc` |
| Dispatch field teams for network repairs (ISF) | 1.0.0 | planned / proposed | `8fd364777833dad29865d5092efd6c405f796b42` |
| Maintain network resource inventory (ISF) | 1.0.0 | planned / proposed | `da4805b12f62f32cf2c27a225b085386b77c850a` |
| Track service degradation against SLAs (ISF) | 1.0.0 | planned / proposed | `9c992347a953c31c37bb64ca027f29a1dc2b03c6` |
| Alarm Collection Service (ISS) | 1.0.0 | active / proposed | `4656f26c2e6e1f94040aaed42e82790b635d4cea` |
| Alarm Correlation Service (ISS) | 1.0.0 | active / proposed | `32d82d5dc3d5c7427082b219ba3b89a960ec6223` |
| Field Dispatch Service (ISS) | 1.0.0 | active / proposed | `10448b36b51b99a538fbf875097a50be69b15ad5` |
| Trouble Ticketing Service (ISS) | 1.0.0 | active / proposed | `4edf1ad21266b382584290e5e654541307c011e6` |
| Resource Inventory Service (ISS) | 1.0.0 | active / proposed | `b44398c4c2f56943e5e3744679d70788ca2adb86` |
| Alarm Collection Interface | 1.0.0 | active / proposed | `ba426a576adeb8ce3746b81ae5cb3686cf9b3971` |
| Alarm Correlation Interface | 1.0.0 | active / proposed | `d5577d43ec951276bce797a3fa876021306389cd` |
| Field Dispatch Interface | 1.0.0 | active / proposed | `e8095b05ea6da7424424ffee403de13a124b640c` |
| Trouble Ticketing Interface | 1.0.0 | active / proposed | `1b4d7eb3db0f636dcce41e20bbdc9f6288f72668` |
| Resource Inventory Interface | 1.0.0 | active / proposed | `9b6601b49a407e9c73f765f1d7aa6e6e66265c52` |
| Mean Time to Recovery metric | 1.2.0 | admitted | `dfcc6aa3a2ba87506ebf48f256636e3a81bb787a` |
| Mean Time to Detect metric | 1.1.0 | candidate | `e0203636da241eea26ff04c2bc29f56edc64cf0a` |
| AI Incident Escalation Compliance metric | 1.1.0 | candidate | `1abaf000433c5af5b766821b4051b2b104c7ce44` |
| First-Pass Anomaly Resolution (RAN Operations) metric | 1.0.0 | candidate | `049b8b7e62ba51cd290c50cd2ea38ab1776ecdda` |

For canonical repository locations, use the catalogue links and record paths in Sections 4–6. Where a repository still has a legacy name, the current live repository path is the resolvable source; do not infer a destination URL from the OpenDEAM rename target.


## 14. Architecture transformation application

The AO-ATP-003 application of this crosswalk is maintained as a companion assessment so that the original source mapping and evidence limitations remain intact. It provides the architecture disposition register, work disposition register, discovery/evidence register, and staged transition and acceptance plan.

- [AO-WE-001 / AO-ATP-003 Architecture Transformation Application](./AO-WE-001-AO-ATP-003-application.md)
- [Discovery and Evidence Register](./AO-WE-001-discovery-and-evidence-register.md)
- [Architecture Disposition Register](./AO-WE-001-architecture-disposition-register.md)
- [Work Disposition Register](./AO-WE-001-work-disposition-register.md)
- [Transition and Acceptance Plan](./AO-WE-001-transition-and-acceptance-plan.md)

The application is a proposed assessment, not an approved implementation decision. It does not change the status of this worked example: architecture crosswalk only; execution remains unvalidated.
