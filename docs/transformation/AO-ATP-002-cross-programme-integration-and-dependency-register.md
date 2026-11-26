# AO-ATP-002 — Cross-Programme Integration and Dependency Register

| Field | Value |
|---|---|
| Identifier | AO-ATP-002 |
| Title | Cross-Programme Integration and Dependency Register |
| Version | 0.1.1 |
| Status | Proposed planning guidance |
| Authority | Agentic-Operation |
| Classification | Non-normative, evidence-led integration register |
| Parent guidance | [AO-ATP-001](./AO-ATP-001-enterprise-architecture-and-service-delivery-transformation-playbook.md) |
| Assurance baseline | [AO-OAR-001](../assurance/AO-OAR-001-operational-assurance-review.md) |
| Conceptual baseline | [AO-CBC-001](../architecture/AO-CBC-001-conceptual-baseline.md) |
| Reconciliation date | 2026-11-26 |

## 1. Purpose

This register establishes the verified dependency and integration position for the first AO-ATP-001 implementation work package: connecting the Agentic-Operation enterprise operating model, the Agentic Operating Procedure (AOP) programme and OpenDEA.

It records what is present in the relevant repositories, what is evidenced by merged changes or published conformance artefacts, what remains inconsistent, and what must be verified before the first end-to-end worked example is treated as an integrated reference.

The register is a planning and assurance artefact. It does not change the authority, semantics, schemas, implementation contracts or governance of AOP or OpenDEA.

## 2. Reconciliation method and evidence classes

The review used current default-branch repository files, GitHub repository trees, merged pull-request metadata where available, catalogue record paths, and published AOP conformance certificates.

Evidence is classified as follows:

| Class | Meaning |
|---|---|
| Verified in repository | The named artefact or record is present on the inspected default branch |
| Verified by merged PR | GitHub reports the relevant pull request as merged |
| Published conformance evidence | A versioned certificate or conformance artefact is present |
| Repository-declared | A README, CR or manifest states the position, but the claim has not been independently exercised here |
| Discrepancy | Two authoritative or operationally relevant surfaces disagree |
| Not verified | The evidence needed to close the assertion was not available in this review |

A file's presence does not prove its workflow is currently passing. A README status does not substitute for record-level evidence. A conformance certificate does not prove business value, production readiness or enterprise suitability.

## 3. Executive reconciliation

| Area | Reconciled position | Confidence |
|---|---|---|
| Agentic-Operation integration guidance | AO-ATP-001 merged as PR #9; its merged file is present on main | Verified |
| OpenDEA Information Systems semantic sequence | CR-017 through CR-022 are merged; current metamodel contains the four Information Systems entities and generated artefacts | Verified |
| OpenDEAM allocation | Current root model contains ISF, ISC, ISS and Integration Interface allocations and the associated catalogue targets | Verified |
| OpenDEA catalogue populations | Four current catalogue repositories contain substantial record populations | Verified at repository-tree level |
| OpenDEA repository naming and pins | Several canonical rename targets are not the live repository names; pointer versions and root-model version are inconsistent | Discrepancy |
| OpenDEA documentation status | ISF/ISC README content materially understates current catalogue population; some CR status headers remain Proposed after merge | Discrepancy |
| AOP normative specification | Eight-dimension AOP specification and machine-readable validation assets are present; README reports v0.6.0 Stable | Repository-declared; artefacts present |
| AOP engineering toolchain | Toolkit, context graph, registry, reference harness and conformance repositories contain the documented pipeline and implementation code | Verified in repository |
| AOP conformance | Document and harness certificates are published under AOP-CONF-1.0.0 | Published conformance evidence |
| AOP live execution | Reference end-to-end gate is implemented, but was not executed as part of this GitHub-only reconciliation | Not verified |
| End-to-end OpenDEA-to-AOP integration | No shared, reconciled architecture model currently demonstrates the complete chain from enterprise outcome to AOP run evidence | Not verified |

The foundations are sufficiently concrete to begin a controlled worked example. They are not yet a single integrated enterprise platform. The next work must demonstrate explicit identity and version resolution, map the fault-management scenario to canonical OpenDEA records, and distinguish fixture evidence from actual enterprise operational evidence.

## 4. OpenDEA semantic foundation

### 4.1 Metamodel CR sequence

The following metamodel pull requests are confirmed merged:

| CR | PR | Merge date | Merge commit |
|---|---:|---|---|
| CR-017 — Information Systems domain semantic integration | [#170](https://github.com/technehub-labs/dea-metamodel/pull/170) | 2026-10-16 | `3e00b35d7fa5fae30eac4e632ab50082dfc1f3dd` |
| CR-018 — Information System Function | [#171](https://github.com/technehub-labs/dea-metamodel/pull/171) | 2026-10-17 | `0f164418279d952ff49cc55c55415d4d572749d1` |
| CR-019 — Information System Component | [#172](https://github.com/technehub-labs/dea-metamodel/pull/172) | 2026-10-17 | `5812cfb597b027e0a474ea0429d658052449b92b` |
| CR-020 — Information System Service | [#173](https://github.com/technehub-labs/dea-metamodel/pull/173) | 2026-10-17 | `6747d84e868728e9a9f97085c5e85f9c3b33b1b6` |
| CR-021 — Integration Interface | [#174](https://github.com/technehub-labs/dea-metamodel/pull/174) | 2026-10-17 | `9e02ee5808d22aa46790f15d2ceb3c0d167aa3f5` |
| CR-022 — Metamodel artifact and conformance closure | [#175](https://github.com/technehub-labs/dea-metamodel/pull/175) | 2026-10-17 | `e1c263c3f8ab78b9197f41c2b741e455367ed143` |

The current metamodel tree contains the canonical normative source, JSON Schemas, Pydantic modules for ISF/ISC/ISS/IntegrationInterface, SQLite schema, TypeScript interfaces, Turtle ontology and closure documents.

**Status hygiene issue:** the CR-017 and CR-022 document headers still say `Proposed (this PR)`, despite the corresponding PRs being merged. CR-021 also retains unchecked acceptance criteria in its document. The merged PR state is authoritative for merge status; the CR documents should be reconciled by their owning programme.

### 4.2 Canonical semantic distinctions

| Concept | Meaning for the integration |
|---|---|
| Business Capability | Durable enterprise ability required to deliver value |
| Business Process | Purposeful enterprise work that produces an outcome |
| Business Service | Business-facing service promise to a consumer |
| InformationSystemFunction (ISF) | Behaviour performed by an information system or one of its components |
| InformationSystemComponent (ISC) | Architectural constituent encapsulating responsibility, structure or execution boundary |
| InformationSystemService (ISS) | Contract offered by an information system or software platform to a consumer |
| IntegrationInterface | Interaction boundary through which information or functionality is exchanged |
| API | Contract artefact that may specify an IntegrationInterface through `dea:specifies` |

The API is not the interface. The interface is not the service. The service is not the component that implements it. A function is not a business capability or business process.

### 4.3 OpenDEAM allocation

The current `dea-architecture-framework/model/opendeam-model.yaml` contains allocations for all four entities. The current `VERSION` file and model declaration both report version 0.9.1.

| Entity | OpenDEAM-local ID | OpenDEAM alias | Current allocation target |
|---|---|---|---|
| Information System Function | `dea:entity-information-system-function` | ISF | `dea-catalog-information-system-functions` |
| Information System Component | `dea:entity-information-system-component` | ISC | `dea-catalog-information-system-components` |
| Information System Service | `dea:entity-information-system-service` | ISS | `dea-catalog-information-system-services` |
| Integration Interface | `dea:entity-integration-interface` | IF | `dea-catalog-information-system-integration-interfaces` |

The OpenDEAM-local alias `IF` is intentional according to CR-AR-FMWK-04: the metamodel alias `II` is retained for IntegrationInterface, while OpenDEAM uses `IF` to avoid collision with an existing `II` alias. The catalogue pointer currently uses `IFI`; this third alias requires explicit reconciliation.

### 4.4 Version and pointer discrepancies

| Surface | Current value observed | Issue |
|---|---|---|
| OpenDEAM `VERSION` | 0.9.1 | Current version file |
| OpenDEAM `model/opendeam-model.yaml` | 0.9.1, status alpha | Agrees with VERSION |
| OpenDEAM README badge | v0.8.0-alpha | Stale relative to VERSION and model |
| Four Information Systems catalogue `metamodel-pointer.yaml` files | v0.7.0 | Older than current OpenDEAM version |
| Metamodel `VERSION` | 1.0.0 | Current metamodel version |
| Metamodel `metamodel/manifest.yaml` | 1.0.0, status draft | Release/status declaration needs owner confirmation |

The catalogue pointers are generated artefacts and explicitly say not to edit them manually. Their correction must follow the OpenDEAM-to-consumer synchronization and regeneration process. Agentic-Operation must not patch these files directly.

## 5. OpenDEA catalogue reality

The counts below are derived from the current GitHub default-branch trees by counting canonical record filenames, not from README assertions alone.

| Entity | Current repository name | Canonical repository name in allocation | Record files present | Observed status |
|---|---|---|---:|---|
| ISF | [dea-catalog-system-functions](https://github.com/technehub-labs/dea-catalog-system-functions) | `dea-catalog-information-system-functions` | 644 `function.yaml` | Populated; repository rename pending |
| ISC | [dea-catalog-application-components](https://github.com/technehub-labs/dea-catalog-application-components) | `dea-catalog-information-system-components` | 735 `component.yaml` | Populated; repository rename pending |
| ISS | [dea-catalog-information-system-services](https://github.com/technehub-labs/dea-catalog-information-system-services) | Same | 623 `service.yaml` | Populated; canonical repository name |
| Integration Interface | [dea-catalog-integration-interfaces](https://github.com/technehub-labs/dea-catalog-integration-interfaces) | `dea-catalog-information-system-integration-interfaces` | 627 `interface.yaml` | Populated; repository rename pending |

The ISF and ISC README files still describe the catalogues as scaffolds or state that population is planned. That is contradicted by the current record trees. The ISC README and v1-alpha README also describe only illustrative examples, while the tree contains 735 component records. The ISS and Integration Interface READMEs describe populated catalogues and their reported counts agree with the record-tree counts.

The three pending repository renames are recorded in the catalogue pointers and the Integration Interface foundation document. The repositories are addressable at their current names, and the OpenDEAM allocation names their intended canonical destinations. Direct repository lookup for the intended Information System Integration Interface target returned not found, while the current `dea-catalog-integration-interfaces` repository exists.

**Implication for agents and enterprise tooling:** discovery must resolve a canonical entity identifier through the OpenDEAM allocation and current repository reality, not infer a repository URL from the canonical target string alone.

## 6. AOP operational engineering assets

### 6.1 Normative and implementation boundaries

| Repository | Current README declaration | Integration role |
|---|---|---|
| [aop-spec](https://github.com/agentic-operating-procedure/aop-spec) | v0.6.0, Stable | Normative eight-dimension AOP model, schemas, skill contract and security/conformance clauses |
| [aop-context-graph](https://github.com/agentic-operating-procedure/aop-context-graph) | v0.3.0, Stable | Observed-work entity model, case schema, stitching, operational twin and drift obligations |
| [aop-toolkit](https://github.com/agentic-operating-procedure/aop-toolkit) | v0.3.0, Stable | SOP parsing, variant mining, decision-rule extraction, AOP compilation and linting |
| [aop-reference-harness](https://github.com/agentic-operating-procedure/aop-reference-harness) | v0.5.0, Stable | Runtime loop, external guardrail, scoped credential broker, escalation, evidence and replay |
| [aop-registry](https://github.com/agentic-operating-procedure/aop-registry) | v0.2.1, Stable | Immutable publication, resolution and provenance chain |
| [aop-conformance](https://github.com/agentic-operating-procedure/aop-conformance) | v0.5.0, Stable | Document and harness conformance profiles, must-fail fixtures and certification |

These are separate programme-owned repositories. Agentic-Operation should integrate by reference and versioned contract, not duplicate the AOP specification or implementation.

### 6.2 Executable reference path

The AOP Toolkit README documents the Python module entry point:

```bash
python3 -m aop_toolkit
```

The reference fixture includes:
- `fixtures/sop/rb-line-001.md` — line fault-management SOP;
- `fixtures/cases/fault-management-cases.jsonl` — 40 case records;
- `fixtures/manifests/fault-management.json` — governance manifest.

The reference harness provides `gate/end_to_end.py`. The code orchestrates:
1. SOP + case corpus + manifest compilation through the toolkit;
2. linting against the AOP specification;
3. immutable publication and resolution through the registry;
4. provenance-chain verification back to the case corpus;
5. execution of the corpus under the harness guardrail;
6. validation of the harness's own top-level AOP;
7. completeness and hash-chain verification of case records;
8. completeness of escalation evidence bundles.

The gate imports the toolkit and registry from sibling repository checkouts. It is therefore a coordinated multi-repository reference workspace, not evidence of a single self-contained production deployment package.

**Important gate interpretation:** the gate's execution-count assertion verifies that the runtime processed the fixture cases. It does not, by itself, prove that all business outcomes were achieved, that a real enterprise's MTTR improved, or that the fixture corpus represents a statistically valid production workload.

### 6.3 Published conformance evidence

The AOP Conformance repository contains two certificates issued on 2026-11-05 under profile `AOP-CONF-1.0.0`:

| Subject | Verdict | Tier | Checks passed |
|---|---|---|---:|
| Fault-management AOP document `AP-LINE-001@v0.47.0` | Conformant | Validated | 12 |
| Reference harness assessing the fault-management AOP | Conformant | Enforced | 23 |

These certificates are meaningful evidence that the named artefacts passed the declared conformance profiles at the time of certification. They do not certify the enterprise's complete operating model, OpenDEA mapping, live service availability, security accreditation, business outcomes or production deployment.

### 6.4 Execution status not established by this review

This review inspected repository code and published certificates; it did not execute the AOP CLI or the Phase 4 end-to-end gate in a provisioned multi-repository environment. Consequently:
- the code path is present and documented;
- the certificates are present and report conformant results;
- current local execution, dependency reproducibility and live service integrations remain to be exercised;
- the scripted reference agent is not evidence of a deployed model-driven agent;
- the human approver is represented by a policy object behind the dispatch interface; the harness README explicitly describes replacing it with a real person for deployment.

## 7. Cross-programme integration gaps

### 7.1 No canonical end-to-end architecture mapping yet

The AOP fault-management fixture uses application labels such as network monitoring platform, line-test system, dispatch system, planning system and inventory system. The fixture does not itself establish canonical OpenDEA entity IDs for each system, function, component, service and interface.

The worked example must resolve each mapping against current catalogue records and record:
- canonical entity ID and class;
- owning catalogue and repository path;
- record version and lifecycle status;
- evidence supporting the mapping;
- relationship type and direction;
- whether the mapping is canonical, provisional, unresolved or intentionally absent.

Do not manufacture canonical records to make the diagram complete. Use explicit unresolved mappings until the owning OpenDEA catalogue admits the required entity.

### 7.2 Process and metric alignment gaps

The AOP Toolkit fixture manifest carries a `process_alignment` block with one process gap and two metric gaps, alongside two metric references:
- it declares no canonical Business Process for network line fault management;
- it references Mean Time to Detect and AI Incident Escalation Compliance;
- it declares no canonical p50 mean-time-to-restore metric;
- it declares no canonical first-pass-fix-rate metric.

The follow-up catalogue inspection found an adjacent but non-equivalent Business Process: `processes:process-eo-operate-4njp7b` (Operate Technology Platforms), with the child Activity `processes:activity-eo-operate-ua7tgk` (Respond to Platform Incidents). Both records are lifecycle `candidate`, and their scope is general platform incidents rather than network line fault management. They are not valid canonical substitutes for the missing network fault-management process.

The metrics catalogue contains:
- `dea:metric-mean-time-to-recovery` (Mean Time to Recovery), version 1.2.0, lifecycle `admitted`, defined as an arithmetic mean in minutes from incident detection to service restoration;
- `dea:metric-mean-time-to-detect` (Mean Time to Detect), lifecycle `candidate`;
- `dea:metric-ai-incident-escalation-compliance` (AI Incident Escalation Compliance), lifecycle `candidate`;
- `dea:metric-first-pass-anomaly-resolution-ran-operations` (First-Pass Anomaly Resolution (RAN Operations)), lifecycle `candidate`.

The admitted Mean Time to Recovery record is not semantically equivalent to the fixture's `mttr-p50-minutes` baseline: an arithmetic mean and a 50th percentile are different statistics. The candidate first-pass anomaly metric is also not an admitted metric and must not be presented as canonical. The original metric gaps therefore need refinement, not blanket closure.

The AOP programme and catalogue owners should reconcile metric identity, statistic, unit, subject and lifecycle before replacing any fixture gap with a canonical reference.

### 7.3 Evidence semantics and trust boundary

The fixture corpus contains 40 case records and provenance fields. The repository also includes a script to generate the corpus. This review has not independently established that these cases were captured from a real operating enterprise or that the capture declarations and source systems are externally attested.

The first worked example must label the corpus as a reference fixture unless its real-world collection provenance is established. It must not present generated or illustrative cases as enterprise operational evidence.

### 7.4 Identity, version and authority binding

A reliable execution record must be able to bind together:
- OpenDEAM model version and metamodel version;
- canonical entity identifiers and catalogue record versions;
- Business Process and Business Service references;
- AOP identifier, version and content digest;
- AOP schema/conformance profile version;
- context graph and case-corpus versions;
- harness version and conformance certificate;
- agent, skill, model and tool identities where actually used;
- authority decision, approval and policy version;
- service invocation and interface contract;
- run, action and outcome evidence.

A name-only cross-reference is insufficient for a governed enterprise integration.

## 8. Dependency register and ownership

| ID | Dependency / action | Current state | Owner | Next action |
|---|---|---|---|---|
| D-01 | OpenDEA IS semantic foundation CR-017..022 | Merged | dea-metamodel | Reconcile stale CR status headers and confirm closure artefacts remain generated and conformant |
| D-02 | OpenDEAM IS entity allocations | Present in root model v0.9.1 | dea-architecture-framework | Confirm downstream consumer synchronization and published release/tag contract |
| D-03 | ISF repository rename and pointer refresh | Pending; 644 records in legacy-named repo | OpenDEA catalogue owner / org admin | Execute governed rename and regenerate pointer against current OpenDEAM release |
| D-04 | ISC repository rename and pointer refresh | Pending; 735 records in legacy-named repo | OpenDEA catalogue owner / org admin | Execute governed rename and regenerate pointer against current OpenDEAM release |
| D-05 | II repository rename and pointer refresh | Pending; 627 records in legacy-named repo | OpenDEA catalogue owner / org admin | Execute governed rename and reconcile catalogue alias IFI with OpenDEAM IF and metamodel II |
| D-06 | ISS catalogue alignment | 623 records; canonical repository name | OpenDEA catalogue owner | Refresh pointer version/status against current model and confirm eight-gate CI evidence |
| D-07 | ISF/ISC README and population status | README statements conflict with live records | ISF/ISC catalogue owners | Update documentation through scoped catalogue CRs; preserve existing records and history |
| D-08 | OpenDEAM README/version badge | README says v0.8.0-alpha; VERSION/model say 0.9.1 | dea-architecture-framework | Reconcile release and badge metadata |
| D-09 | Metamodel manifest release status | VERSION 1.0.0; manifest status draft | dea-metamodel | Confirm intended release status and align manifest/README/consumer guidance |
| D-10 | AOP toolchain execution | Reference code and certificates present; local gate not run in this review | AOP programme | Run the documented multi-repository gate in a controlled environment and retain logs/artifact digests |
| D-11 | Fault-management process alignment | Adjacent platform-incident Process and Activity exist, both candidate and not equivalent to network line fault management | Business Process catalogue owner | Keep the exact network line fault-management process gap open; assess whether a scoped contribution is required |
| D-12 | MTTR and first-pass metric alignment | Admitted arithmetic-mean recovery metric exists; p50 gap remains; first-pass anomaly metric is candidate | Metrics catalogue owner with AOP programme | Reconcile statistic and subject; do not bind candidate metrics as canonical until admitted |
| D-13 | Fixture provenance | 40 cases present; real-world provenance not established | AOP programme / scenario owner | Retain fixture classification or provide auditable collection provenance |
| D-14 | End-to-end OpenDEA ↔ AOP mapping | Not yet demonstrated | Agentic-Operation integration lead with AOP/OpenDEA owners | Build the first traceable fault-management architecture and execution evidence chain |

This register assigns ownership to the relevant programme. It does not authorize Agentic-Operation to make changes in those repositories.

## 9. First worked-example integration contract

The first worked example remains the AOP fault-management scenario. It should be built in controlled increments.

### 9.1 Required traceability chain

```text
Enterprise stakeholder and outcome
        |
        v
OpenDEA business capability
        |
        v
OpenDEA business process and business service
        |
        v
Observed work cases and context graph
        |
        v
AOP: intent, context, constraints, authority,
capabilities, coordination, control, assurance
        |
        v
Skills + domain harness + human authorities
        |
        v
OpenDEA system functions, components,
information-system services and interfaces
        |
        v
Run/action records, approvals, service results
        |
        v
Verified process, service and business outcomes
```

This is a cross-programme integration view, not a new metamodel.

### 9.2 Mapping rules

1. Resolve every OpenDEA reference from the current canonical metamodel and root model; record the model and schema versions.
2. Resolve catalogue records by canonical entity ID, not by display name alone.
3. Keep business capability, process, business service, system function, component, system service and interface separate.
4. Use `dea:specifies` for an API contract that specifies an IntegrationInterface; do not use it as a substitute for service exposure or component provision.
5. Keep the AOP as the operational specification; do not translate the SOP directly into an agent prompt.
6. Preserve the distinction between observed work, normative authority and proposed agent action.
7. Bind approvals and execution permissions to external enforcement, not to model instructions.
8. Keep unresolved catalogue mappings visible and actionable.
9. Label fixture evidence, simulated execution and live enterprise evidence distinctly.
10. Measure outcome realization; do not treat compilation, conformance or case processing as business-value proof.

### 9.3 Acceptance criteria for the worked example

The scenario is ready for wider reuse only when:
- every business and information-systems reference resolves to a canonical OpenDEA ID or is explicitly marked unresolved;
- the AOP source SOP, case corpus, manifest, compiled AOP and conformance result are version-bound;
- the harness run records authorization, action, service invocation, escalation, evidence and outcome;
- prohibited and approval-gated actions are demonstrated through positive and negative tests;
- human authority and intervention are exercised, not represented only by a placeholder;
- the end-to-end evidence chain is replayable;
- the difference between fixture results and live enterprise outcomes is explicit;
- no production-readiness or business-value claim exceeds the evidence.

## 10. Recommended execution sequence

| Order | Work package | Output |
|---:|---|---|
| 1 | Resolve OpenDEA catalogue and version metadata discrepancies with the owning programme | Confirmed upstream dependency baseline; scoped upstream CRs where required |
| 2 | Reconcile the fault-management scenario against actual OpenDEA records | Versioned entity and relationship crosswalk, with explicit gaps |
| 3 | Exercise the AOP toolkit and reference harness in a controlled workspace | Reproducible logs, compiled AOP, registry record, conformance and harness evidence |
| 4 | Build the end-to-end traceability artefact | OpenDEA model slice + AOP + service/interface bindings + evidence chain |
| 5 | Evaluate the scenario against enterprise outcome measures | Baseline and post-run measures, with evidence provenance and limitations |
| 6 | Publish the worked example in Agentic-Operation | Practitioner reference with role-specific guidance and clear authority boundaries |

Agentic-Operation may proceed with the integration method and worked example while upstream catalogue owners address the documented discrepancies. Where a mapping is unresolved, the example must show the gap rather than silently inventing a canonical record.

## 11. Explicit non-claims

This register does not claim:
- that the OpenDEA, AOP and Agentic-Operation repositories form one deployed platform;
- that all OpenDEA catalogue metadata and README files are current;
- that all referenced workflows are passing at the time this register is read;
- that the AOP reference harness has been deployed into a live enterprise environment;
- that the 40-case fixture corpus is independently verified production evidence;
- that AOP conformance proves business outcomes;
- that a populated catalogue proves that a specific enterprise service is deployed, available or operational;
- that any of the reference assets are production-ready.

## 12. Conclusion

The three programmes have complementary foundations:

- OpenDEA describes the enterprise and its systems through canonical entities, relationships, architecture allocations and catalogues.
- AOP specifies how selected work is to be performed under explicit intent, context, authority, constraints, coordination, control and assurance.
- Agentic-Operation provides the enterprise operating-model, AI Agent management, transformation and outcome-assurance context.

The immediate integration challenge is no longer to invent these foundations. It is to resolve their identities, versions, evidence and ownership boundaries, then demonstrate one complete and replayable path from enterprise outcome to governed execution and verified result.

The first fault-management example should be the proof of integration, not a claim that the integrated reference stack is already a production platform.
