# AO-OAR-001 — Agentic Operations Operational Assurance Review

| Field | Value |
|---|---|
| Review ID | AO-OAR-001 |
| Title | Operational assurance review of the Agentic-Operation reference estate and enterprise operating model |
| Version | 0.1.0 |
| Status | Initial evidence-based review |
| Review date | 2026-11-26 |
| Classification | Non-normative assessment and internal planning guidance |
| Owning organization | Agentic-Operation |
| Repository | `.github` |
| Controlling baseline | [AO-CBC-001 — Conceptual Baseline and Cross-Programme Boundary Contract](../architecture/AO-CBC-001-conceptual-baseline.md) |
| Related organization change | [CR-AO-ORG-001 — Organization Purpose and Authority](../../change-requests/CR-AO-ORG-001-organization-purpose-and-authority.md) |
| Related programme | [Agentic Operating Procedure](https://github.com/agentic-operating-procedure) |

## 1. Purpose

This review establishes an evidence-based view of the distance between the current Agentic-Operation reference estate and the operational capabilities an enterprise would need to establish before relying on an agentic operating model at scale.

It is not a production-readiness declaration, certification, security assessment, or claim that the reference stack is deployed. It is a guiding review to shape the organization's internal engineering, governance, assurance, adoption and value-realization plans.

The review addresses five questions:

1. Which components are present and demonstrably executable from source?
2. Which controls are specified, implemented, tested, integrated, deployed and continuously evidenced?
3. How does Agentic Operating Procedure (AOP) underpin the transition from SOP-governed work to governed agentic execution?
4. What trust model is required for human-agent and agent-agent collaboration, coordination and co-opetition?
5. What evidence is required to demonstrate operational effectiveness and enterprise outcomes?

The assessment deliberately separates repository presence, executable source, automated test evidence, integrated behaviour, deployed availability and enterprise outcome evidence. These are different assurance claims and must not be conflated.

## 2. Executive assessment

### 2.1 Overall position

The Agentic-Operation organization has a coherent initial portfolio of AI Agent management specifications, reference service implementations and conformance tooling. The five service repositories contain runnable Python HTTP service entry points and local test suites. The latest observed CI runs for these services completed successfully on 2026-11-25. The three specification repositories also have successful recent conformance/CI runs.

This establishes useful source-level and automated-test evidence. It does not establish that the services are deployed, reachable, secured for enterprise use, resilient, monitored, supported or producing business outcomes.

The current estate should therefore be represented as a **reference implementation and engineering foundation**, not a production service platform.

### 2.2 Assurance position by evidence level

| Evidence level | Meaning | Current position |
|---|---|---|
| E0 — Assertion | README, diagram, roadmap or capability claim | Present across the organization |
| E1 — Source evidence | Inspectable implementation, schema, configuration or executable entry point | Present for the five reference services and conformance tooling |
| E2 — Component verification | Repeatable automated tests and CI results for the component | Present; latest observed service CI runs succeeded |
| E3 — Integrated verification | Repeatable end-to-end execution across dependent services and operational controls | Partial at best; individual service smoke tests exist, but no Agentic-Operation integrated multi-service acceptance gate was identified |
| E4 — Operational evidence | Deployed environment, authenticated endpoints, health telemetry, SLOs, incident/recovery records and accountable support | Not established by the reviewed repository evidence |
| E5 — Enterprise outcome evidence | Measured business outcomes, baselines, risk-adjusted value and sustained benefits | Not established by the reviewed repository evidence |

A higher level includes the evidence obligations of the lower levels. A successful CI run is not an E4 availability claim; an operationally available endpoint is not an E5 business-value claim.

### 2.3 Principal conclusions

- The three AI Agent specifications are identified by their repositories as normative drafts, version 1.0.0-alpha. They should be treated as draft standards until their governance and release process establishes otherwise.
- The five runtime/service repositories contain executable source and local smoke tests. Their current implementation patterns are reference-grade and require substantial security, deployment, resilience and operations hardening before enterprise deployment.
- The conformance repository is an executable validation toolchain, not a runtime service. Its default integrity check includes structural checks; cryptographic `cosign` verification is optional and must not be inferred from a passing default run.
- Several health and lifecycle behaviours are stubs or illustrative state transitions. In particular, the MCP manager's health endpoint records a fixed healthy result rather than proving that a target server is reachable.
- The AOP programme has a more developed normative trust and execution model than the current Agentic-Operation runtime estate. Its normative authority remains in the AOP programme.
- The enterprise operating model requires a trust framework that spans people, agents, procedures, models, tools, data, runtime controls, organizational authority and outcome evidence. Agent identity and discovery alone do not establish trust or authority.
- Outcome assurance must focus on business and stakeholder outcomes and value-stream performance, not agent counts, model counts, task volume or automation rates alone.

## 3. Scope and method

### 3.1 Repositories reviewed

The live Agentic-Operation organization inventory returned eleven repositories:

| Repository | Portfolio role |
|---|---|
| `agent-profile-management` | Spec-443 — AI Agent Profile |
| `agent-bootstrap-management` | Spec-444 — AI Agent Bootstrap |
| `agent-discovery-card` | Spec-445 — AI Agent Card |
| `agent-registry` | Agent Card Registry reference service |
| `model-authority` | Model Management Authority reference service |
| `agent-rollout-controller` | Rollout, deployment and inventory reference service |
| `tool-mcp-manager` | Tool and MCP management reference service |
| `agent-orchestrator` | Agent topology and coordination reference service |
| `agent-conformance` | Validation and conformance tooling |
| `agent-standard-docs` | Communication and documentation |
| `.github` | Organization profile and governance documentation |

The review inspected repository READMEs, selected source files, tests, workflow definitions, recent GitHub Actions results, and the AOP programme's foundations, specification, architecture, harness, conformance, registry and governance documentation.

### 3.2 Limits of the review

This is a repository and documentation evidence review. It did not:
- access a deployed Agentic-Operation environment or private infrastructure;
- execute penetration testing, threat modelling workshops or a formal security audit;
- independently deploy the reference services;
- validate production DNS, TLS certificates, authentication providers, secrets stores or network policies;
- inspect enterprise customer data or production execution records;
- validate realized business benefits or causal attribution;
- certify AOP or Agentic-Operation conformance.

Absence of evidence in the inspected repositories is reported as **not established**, not proof that a control cannot exist in an external environment.

## 4. Component execution and availability assessment

### 4.1 Classification

| Component | Source-level executable evidence | Automated test evidence | What the current evidence demonstrates | What it does not demonstrate |
|---|---|---|---|---|
| Agent Registry | Python HTTP service entry point | Local smoke test and recent successful CI | Card registration, search, version retrieval, environment-instance handling and discovery endpoint paths can be exercised locally | Production deployment, durable/high-availability storage, authenticated access, TLS, external trust anchoring or service availability |
| Model Management Authority | Python HTTP service entry point | Local smoke test and recent successful CI | Model record registration, resolution, version lookup and deprecation path can be exercised locally | Enterprise model approval governance, secured webhook delivery, identity enforcement, high availability or production operation |
| Agent Rollout Controller | Python HTTP service entry point | Local smoke test and recent successful CI | Bootstrap validation and inventory-oriented behaviour can be exercised locally | Real deployment orchestration across enterprise platforms, secret injection, rollback safety, signed deployment attestations or production change control |
| Tool/MCP Manager | Python HTTP service entry point | Local smoke test and recent successful CI | Tool and server metadata can be loaded and queried | Effective credential brokering, enforcement of tool scopes at invocation, non-bypassable egress control or real health probing |
| Agent Orchestrator | Python HTTP service entry point | Local smoke test and recent successful CI | Topology loading, registry lookup path, coordination variables and signal interfaces can be exercised | Complete multi-agent task execution, conflict arbitration, robust distributed coordination, safe concurrency or measured business outcomes |
| Agent Conformance | Executable validators and shell pipeline | Recent successful conformance workflow | Artifact validation, cross-triad checks and default integrity-structure checks can be run | Production signature verification unless the cryptographic verification option is enabled; runtime enforcement in a deployed harness |
| Three specification repositories | Normative draft documents, schemas and test assets | Recent successful CI/conformance workflows | Draft contracts and machine-readable validation assets are maintained and checked | Final standard maturity, implementation interoperability across independent vendors or operational effectiveness |
| Agent Standard Docs | Documentation and communication pack | Recent successful documentation lint | Documentation lint and publication source are maintained | Completeness of operational procedures, enterprise adoption or outcome evidence |

### 4.2 Important implementation observations

The following observations materially affect the assurance position:

1. The inspected runtime services use Python's standard-library `HTTPServer` and bind to `0.0.0.0`. The inspected service entry points do not demonstrate application-level authentication, authorization enforcement or TLS termination. A deployment must not expose these development/reference listeners directly to an untrusted network.
2. The MCP manager documents its health operation as a stub. Its current implementation records a fixed `healthy` state and timestamp rather than establishing reachability and functional readiness of the target server.
3. The rollout controller's inventory path also contains fixed illustrative health state. This is not equivalent to a live readiness probe or observed service health.
4. The orchestrator provides topology and coordination-variable interfaces. Its current component tests do not establish a complete governed work execution across multiple live agents and external systems.
5. The service repositories contain source and tests but the reviewed repository trees did not show Dockerfiles, Compose definitions, Kubernetes/Helm manifests, Terraform or comparable deployment artefacts. This is a repository-evidence observation, not a claim that no external deployment exists.
6. The service tests are primarily component-level smoke tests. Some tests retrieve worked examples from other public repositories at test time, so reproducibility and dependency pinning should be strengthened for controlled build pipelines.
7. The conformance pipeline invokes the integrity verifier without the optional `--cosign` flag. A successful default run must not be described as cryptographic signature verification against a live transparency log.
8. The Agentic-Operation organization profile now correctly distinguishes reference implementations from deployed services. However, the Agent Registry README calls the implementation a “Production Agent Card Registry”; that wording should be reconciled with the organization's evidence-based reference status.
9. PR #7 corrected the organization profile's repository-specific licence summary. Several service README files still state Apache-2.0 while their repository LICENSE files are MIT. The README claims should be reconciled with the authoritative LICENSE files.

### 4.3 Current CI evidence

The latest observed successful workflow runs at the time of review include:

- [Agent Registry CI](https://github.com/Agentic-Operation/agent-registry/actions/runs/45561076659)
- [Model Authority CI](https://github.com/Agentic-Operation/model-authority/actions/runs/45561132505)
- [Rollout Controller CI](https://github.com/Agentic-Operation/agent-rollout-controller/actions/runs/45561175314)
- [Tool/MCP Manager CI](https://github.com/Agentic-Operation/tool-mcp-manager/actions/runs/45561235836)
- [Agent Orchestrator CI](https://github.com/Agentic-Operation/agent-orchestrator/actions/runs/45561272872)
- [Agent Conformance](https://github.com/Agentic-Operation/agent-conformance/actions/runs/45560535237)
- [Agent Standard Docs lint](https://github.com/Agentic-Operation/agent-standard-docs/actions/runs/45761767069)

These links evidence successful workflow executions at the time observed. They do not certify deployment, security, service availability or business outcomes.

## 5. SOP-to-AOP transformation: the operational engineering foundation

### 5.1 The role of the SOP

A Standard Operating Procedure remains an important source of approved operational knowledge. It can preserve purpose, scope, roles, responsibilities, controls, known decision points, exceptions and expected outputs.

The transition to AOP is not a wholesale replacement of SOP libraries, nor a mechanical conversion of each SOP step into an agent prompt. Existing SOPs remain controlled source material and may continue to govern human-only, regulated, safety-critical or otherwise unsuitable work.

The transformation question is: which operational work is suitable for agentic execution, what must remain human-controlled, and what new specification and assurance mechanisms are required?

### 5.2 The role of AOP

The AOP Foundations authority defines an AOP as a structured operational specification that governs how agents may interpret intent, make decisions, coordinate capabilities and execute actions within explicitly governed operational boundaries to achieve verifiable outcomes.

The eight AOP dimensions are mandatory:

1. **Intent** — operational objective and desired outcome.
2. **Context** — relevant information and environmental state.
3. **Constraints** — policies, rules, boundaries and prohibited actions.
4. **Authority** — decisions an agent may make and those requiring approval.
5. **Capabilities** — skills, tools and operational capabilities available.
6. **Coordination** — interaction among agents, humans and external systems.
7. **Control** — monitoring, validation, intervention and exception handling.
8. **Assurance** — evidence required to establish correctness and outcomes.

The AOP is therefore not an agent instruction set. It is the governed operational specification against which the harness and execution are designed, constrained and assured.

### 5.3 Transformation lifecycle

The following is a practical enterprise transformation sequence aligned with the AOP Foundations concepts. It is a planning view, not a new normative AOP process.

| Step | Transformation activity | Principal output | Assurance question |
|---|---|---|---|
| 1 | Select and qualify the source SOP and operational scope | Controlled SOP baseline, owner, outcome and risk scope | Is the source current, approved, owned and suitable for analysis? |
| 2 | Observe actual work and collect representative cases | Evidence-backed case corpus, variants, exceptions and operational context | Does the source reflect real work, including workarounds and exceptions? |
| 3 | Model operational context and semantics | Context model, relevant entities, relationships, states and provenance | Is the information complete, trustworthy, current and sufficiently scoped? |
| 4 | Analyse decisions, responsibilities and authority | Decision inventory, human/agent role allocation, approval and escalation rules | Which decisions may be delegated, to whom, under what limits and evidence? |
| 5 | Engineer the AOP | Versioned AOP with all eight dimensions, variants, decision points and assurance obligations | Is the AOP complete, unambiguous, conformant and traceable to its source? |
| 6 | Engineer the domain harness and bind capabilities | Harness specification, skills, tools, interfaces, identities and enforcement controls | Can the environment enforce the AOP independently of the agent? |
| 7 | Verify, simulate and evaluate | Conformance result, scenario tests, failure tests, baseline comparison and approver evidence | Does the design behave safely across normal, exceptional and adversarial cases? |
| 8 | Deploy under controlled operational governance | Approved release, workload identity, monitoring, support and rollback arrangements | Can the enterprise operate, observe, stop, recover and audit the system? |
| 9 | Measure and improve | Outcome evidence, procedure updates, risk review and value-realization record | Did the changed operating method achieve its intended outcomes sustainably? |

The lineage must remain traceable: source SOP and observed cases → context and decision model → AOP version → skills and harness version → agent/model/tool versions → run and action records → verified operational outcome → enterprise outcome assessment.

The AOP programme owns the normative AOP model, its schema, security clauses, conformance and runtime semantics. Agentic-Operation owns the enterprise adoption context, organizational accountability, agent management integration and business outcome model. AOP adoption repositories named in AOP programme planning were not present in the live AOP inventory checked for this review; their status and ownership should be resolved by that programme rather than assumed here.

## 6. Enterprise trust model for human and non-human work

### 6.1 Trust is a system property

Trust in Agentic Operations must not be reduced to confidence in a model, a provider, an agent profile, an Agent Card, a benchmark score or a successful demonstration.

Trust is a set of verifiable relationships among principals, capabilities, authority, context, execution, controls, evidence and outcomes. It is established for a particular actor, procedure, action, resource, context and time. It can be limited, withdrawn or invalidated when dependencies or conditions change.

The enterprise remains accountable for the outcomes of work. Delegating execution to an agent does not transfer institutional accountability to that agent.

### 6.2 Trust dimensions

| Trust dimension | What must be established | Relevant mechanisms and evidence |
|---|---|---|
| Identity and provenance trust | Which human, organization, agent, model, tool, workload and version are involved; who issued and changed them | Spec-443 identity/profile, Spec-444 bootstrap bindings, Spec-445 discovery card, model authority records, authenticated workload identity, signed artefact provenance |
| Capability and competence trust | What the actor can do, what it has been tested to do, and under which conditions its capability claim is valid | Declared capabilities and skills, schema/conformance tests, observed performance, evaluation evidence, version and environment bindings |
| Authority and delegation trust | Who owns the outcome, who may decide, what is delegated, the scope, expiry, limits and revocation conditions | AOP Authority dimension, organizational decision-rights model, external policy decision/enforcement points, action-bound approvals, short-lived scoped credentials |
| Context and information trust | Whether context is relevant, sufficiently complete, current, authorized, privacy-preserving and traceable to reliable sources | Context snapshots, source provenance, data quality/freshness checks, access policy, minimization, semantic/context graph controls |
| Execution integrity trust | Whether the approved procedure, model, agent, skill, tool and runtime are the ones actually used, and whether enforcement is bypass-resistant | Pinned versions and digests, signature verification, isolated harness, non-bypassable guardrails, controlled egress, deployment attestations |
| Interaction and coordination trust | Whether humans and agents can collaborate, coordinate, challenge, negotiate hand-offs and resolve conflicts without exceeding authority | AOP Coordination and Control dimensions, explicit protocols, role/authority maps, escalation, conflict handling, shared-resource safeguards and traceable hand-offs |
| Outcome and accountability trust | Whether actions were appropriate, results verified, responsibility retained and affected parties able to challenge or seek remedy | Independent verification, append-only records, replay, human oversight, emergency stop, incident and recovery records, outcome measures and audit |

Trust must be evaluated across the complete chain. A trustworthy agent identity cannot compensate for an untrusted context; a conformant AOP cannot compensate for an insecure harness; a secure execution cannot establish business value without outcome evidence.

### 6.3 Human-agent collaboration

The enterprise relationship should be designed around accountable delegation, not anthropomorphic equivalence or unrestricted autonomy.

- A human or accountable organizational role owns the business outcome and the decision rights.
- An agent receives a bounded, explicit delegation for a defined purpose, context, action class and period.
- The agent may interpret context, propose actions, use approved capabilities and report uncertainty within that delegation.
- The agent cannot create, expand or self-authorize its own permissions.
- Human approval is required where the AOP, policy, risk class or organizational authority model requires it.
- Approval must be informed by an evidence bundle and bound to the action, context, procedure version and expiry. Silence or non-response is not approval.
- Humans must be able to reject, request changes, defer, escalate, suspend or revoke delegation through governed mechanisms.
- The enterprise must preserve named accountability even where execution is highly automated.

Human oversight must be meaningful and risk-proportionate. A human approval step that lacks context, authority, time, competence or the ability to reject is not an effective control.

### 6.4 Agent-agent coordination

Agents must not be assumed trustworthy merely because they are registered, discoverable or members of the same orchestration topology.

Coordination requires:
- independently verifiable identity and version for each participating agent;
- declared capability, skill, model and tool dependencies;
- explicit purpose, role, task boundary and delegated authority;
- trusted, scoped and provenance-aware context exchange;
- protocol and message validation;
- conflict detection and arbitration for shared state and resources;
- concurrency controls, idempotency, reconciliation and compensation for side-effecting work;
- traceable delegation, hand-off, decision and result records;
- independent outcome verification and escalation where participants disagree.

The orchestrator may coordinate work, but it must not become an unbounded authority source. Coordination metadata or topology membership does not itself grant permission to perform an action.

### 6.5 Co-opetition: collaboration and competition under governance

Co-opetition can be useful where agents cooperate toward an enterprise outcome while independently exploring, comparing or challenging alternative hypotheses, plans, recommendations or optimizations.

It must be designed as governed competition, not as a contest for permissions or uncontrolled access to shared resources.

The enterprise should define:
- the objective and evaluation criteria against which competing proposals are assessed;
- which agents may propose, critique, verify or execute;
- separation between proposal generation and authorization;
- provenance and disclosure of the evidence used by each proposal;
- conflict-of-interest, collusion, manipulation and reward-hacking controls;
- limits on access to shared data, tools, budgets and operational resources;
- deterministic arbitration or accountable human resolution where proposals conflict;
- safeguards against duplicate or mutually inconsistent side effects;
- a record of the alternatives considered, decision rationale, selected course and outcome.

Agents may compete in analysis or proposal quality while cooperating in execution under a single governed operational objective. No agent may use competition as a reason to bypass another agent's authority, conceal evidence, interfere with another workload or seize shared resources.

### 6.6 AOP trust architecture and its authority

The AOP programme's architecture establishes four assurance mechanisms:

1. **Prevent** — the authority check and enforcement point operate outside the model context; an agent proposes actions but cannot decide whether they are permitted.
2. **Verify** — actions and outcomes are independently checked against the AOP's declared intent and observed paths.
3. **Oversee** — human escalations carry evidence bundles sufficient for an accountable approver to rule on the case.
4. **Audit** — decisions and actions are recorded in append-only, tamper-evident records with defined replay guarantees.

The AOP normative security clauses further specify fail-closed enforcement, scoped credentials, context minimization, approval-gated high-risk actions, emergency stop, workload identity and declared egress. Run/action semantics bind authorization to action digests and context, address retries and duplicate delivery, and require explicit handling of concurrency, partial success and compensation.

These AOP mechanisms are the engineering and execution foundation for the enterprise trust model. Their normative source remains the AOP programme:
- [AOP Foundations](https://github.com/agentic-operating-procedure/aop-foundations)
- [AOP Specification](https://github.com/agentic-operating-procedure/aop-spec)
- [AOP Architecture — Trust Architecture](https://github.com/agentic-operating-procedure/aop-architecture/blob/main/docs/aop-trust-architecture-architecture-scope.md)
- [AOP Reference Harness](https://github.com/agentic-operating-procedure/aop-reference-harness)
- [AOP Conformance](https://github.com/agentic-operating-procedure/aop-conformance)

Agentic-Operation should integrate with these controls and establish the enterprise roles, policies, agent-management bindings and outcome obligations around them. It must not copy or redefine AOP normative clauses.

## 7. Governance controls required across the operating model

The enterprise governance model must connect organizational policy to enforceable runtime controls and evidence.

| Governance concern | Required enterprise control | Evidence expected |
|---|---|---|
| Outcome ownership | Named accountable business owner for each value stream and material agentic work scope | Ownership register, outcome charter, RACI/decision-rights record |
| Procedure authority | Approved, versioned SOP/AOP source with named author, approver and owner | Source lineage, approval record, version and digest |
| Agent identity | Unique identity and lifecycle status for each managed agent | Spec-443 profile, registry entry, environment instance |
| Agent provisioning | Controlled initialization and environment-specific configuration | Spec-444 bootstrap, deployment record, approved dependency set |
| Discovery and capability claims | Published and validated discovery metadata | Spec-445 card, registry verification and conformance result |
| Model governance | Approved model, version, provenance, risk class, permitted use and environment | Model authority record, evaluation evidence, deprecation/re-certification event |
| Tool and data access | Least privilege, scoped credentials, approved tools and context | Access policy, authorization decision, credential issuance/revocation logs |
| Delegated authority | Action-level decision rights, thresholds, approvals, expiry and revocation | AOP authority rules, approval object, enforcement decision and action digest |
| Human oversight | Competent and independent approvers, escalation SLAs and override rights | Approver eligibility, approval/rejection/defer records, oversight quality metrics |
| Runtime security | Workload identity, isolation, egress restrictions, secrets management and protected enforcement | Deployment profile, security tests, runtime attestations and policy logs |
| Coordination | Conflict, concurrency, shared-resource, hand-off and compensation controls | Coordination plan, run/action graph, lock/conflict/reconciliation records |
| Change and release | Controlled changes to AOPs, agents, models, skills, tools and runtime | Change approval, compatibility assessment, conformance and rollback evidence |
| Incident and recovery | Detect, hold, stop, investigate, recover and authorize resumption | Incident records, emergency-stop event, recovery evidence, owner decision |
| Audit and retention | Immutable or tamper-evident records, access control, retention and lawful erasure | Audit trail, chain verification, external anchoring and retention record |
| Supplier and partner trust | Contractual, identity, security and interoperability controls across organizational boundaries | Supplier assurance, trust agreements, interface and identity verification |
| Value realization | Baselines, benefit owners, cost/risk measures and post-deployment evaluation | KPI baseline, realized-benefit record, risk-adjusted value assessment |

The governance model must operate across the lifecycle, not solely at design-time approval or CI. Controls must be observable, testable and attributable to accountable owners.

## 8. Evidence of operational and enterprise outcomes

### 8.1 Evidence chain

The minimum traceable evidence chain should connect:

**Enterprise outcome → value stream → work scope → source SOP and observed cases → AOP version → harness and skill versions → agent/model/tool versions → run and action records → authority and approval decisions → verified operational result → enterprise outcome assessment.**

Each link must carry stable identifiers, version information, provenance and timestamps sufficient to reconstruct which approved operating design produced the observed result.

### 8.2 Outcome hierarchy

| Level | Measurement focus | Illustrative evidence |
|---|---|---|
| Stakeholder outcome | Customer, employee, partner, citizen or other stakeholder result | Resolution quality, experience, accessibility, trust, satisfaction |
| Business outcome | Business result attributable to the changed operating method | Revenue, retention, cost-to-serve, working capital, risk-adjusted margin |
| Value-stream performance | End-to-end flow and effectiveness | Lead time, throughput, first-time-right, rework, exception rate |
| Operational performance | Reliability and service execution | Availability, latency, incident rate, recovery time, service quality |
| Control and trust effectiveness | Whether the system remains within authority and risk limits | Unauthorized-action rate, policy violations, escalation quality, approval quality, audit completeness |
| Workforce and collaboration | Quality of human-agent work allocation and interaction | Human workload, cognitive burden, override rate, hand-off quality, employee experience |
| Economic and environmental efficiency | Net cost and resource use of the operating model | Total cost per outcome, inference/tool cost, energy/resource intensity |

Measures must have a defined owner, baseline, target, measurement method, scope, reporting interval and evidence source. Risk and quality guardrails must be measured alongside efficiency and throughput.

### 8.3 Distinguish activity, output, outcome and value

- **Activity:** agents invoked, tasks attempted, tokens consumed, decisions generated.
- **Output:** cases processed, reports produced, actions completed.
- **Operational outcome:** work completed correctly, safely and within the required service conditions.
- **Business outcome:** the stakeholder or enterprise result improved.
- **Realized value:** the net benefit after implementation, operating, assurance, human oversight, risk and change costs.

Higher activity or output does not necessarily produce better outcomes. Automation rate is not a substitute for quality, control effectiveness or value realization.

### 8.4 Evaluation design

Enterprise outcome claims should use:
- a documented pre-change baseline and comparable post-change observation window;
- a defined comparison or counterfactual where feasible;
- segmentation by case complexity, risk, channel, geography and operating context;
- explicit treatment of exceptions, human intervention and rework;
- total cost of the agentic operating model, including model, infrastructure, integration, assurance and human oversight costs;
- safety, security, compliance and customer-experience guardrails;
- independent validation for material claims;
- attribution limits and uncertainty statements.

A benefit should not be attributed to agentic execution merely because it occurred after deployment. The enterprise must assess whether the change in operating method plausibly caused the observed result and whether the benefit is sustainable.

## 9. Priority gaps and internal planning actions

The following priorities are guidance for internal planning. They are not declarations that the reference stack is production-ready or that all work must be implemented in a single release.

| Priority | Gap / planning need | Internal action direction | Intended evidence |
|---|---|---|---|
| P0 | Runtime security boundary is not demonstrated in the reference services | Establish an enterprise deployment security profile covering authentication, authorization, TLS/mTLS, workload identity, network segmentation, secrets, egress and administrative access | Threat model, deployment profile, security test suite, verified enforcement logs |
| P0 | Reference health signals are not reliable operational health evidence | Replace fixed/stub health state with real liveness, readiness, dependency and functional checks; define service ownership and failure semantics | Probe implementation, health telemetry, failure injection and recovery results |
| P0 | No deployed availability or support evidence | Define target deployment topology, environments, operators, SLOs, monitoring, alerting, backup, recovery, incident response and support ownership | Deployment records, SLO dashboards, incident/recovery exercises, service ownership |
| P1 | Cross-service integration is not established by component smoke tests | Build a repeatable end-to-end reference scenario across registry, model authority, rollout, tool manager, orchestrator and conformance | Version-pinned integration pipeline, test report, traceable run evidence |
| P1 | AOP and Agentic-Operation integration needs an explicit enterprise reference path | Define the handshakes among enterprise outcomes, SOP lineage, AOP, skills, harness, agent standards, model authority and enterprise evidence | Cross-programme interface contract, reference workflow and traceability record |
| P1 | Agent authority and human oversight need enterprise role and policy binding | Define accountable owner, delegating authority, approver eligibility, separation of duties, approval object, revocation and emergency-stop responsibilities | Authority matrix, policy records, approval evidence and oversight metrics |
| P1 | Trust claims need independent verification | Establish identity, provenance, capability, context, execution-integrity and evidence verification across the full actor chain | Trust profile, independent verifier, security and conformance results |
| P2 | Co-opetition and multi-agent conflict controls need explicit design | Specify proposal/decision separation, arbitration, shared-resource safeguards, conflict detection, anti-collusion controls and outcome attribution | Coordination policy, adversarial scenarios, conflict and reconciliation records |
| P2 | Enterprise outcomes are not yet evidenced | Define outcome baselines, KPIs, benefit owners, cost/risk model and evaluation method for selected value streams | Baseline and post-change evaluation, benefit realization and assurance report |
| P2 | Repository documentation and evidence claims need consistency | Correct README production claims and stale licence declarations; pin test dependencies and document known limitations | Repository documentation checks and evidence register |
| P3 | Lifecycle assurance must be continuous | Add drift detection, re-certification triggers, model/tool/AOP change impact analysis, audit sampling and periodic authority review | Change events, reassessment records, audit results and trend measures |

### 9.1 Recommended sequence

1. **Establish the assurance baseline.** Maintain this review as the initial evidence register and agree that repository/CI evidence is not equivalent to operational availability.
2. **Harden the reference services.** Address authentication, authorization, workload identity, TLS, secrets, egress, health checks, persistence, failure handling and deployment packaging before exposing services beyond a controlled development environment.
3. **Build an integrated reference execution.** Use a bounded business scenario with source SOP, observed cases, engineered AOP, skills, harness, agent profile/bootstrap/card, model authority, tool access, orchestration, approvals and evidence.
4. **Connect enterprise governance to AOP enforcement.** Establish organizational roles, risk policies, decision rights, human approval and recovery responsibilities while preserving AOP's normative authority.
5. **Establish operational management.** Define service ownership, deployment, SLOs, monitoring, incident management, backup, recovery, change and release controls.
6. **Prove outcomes.** Select a value stream, establish its baseline, run a controlled transformation and evaluate stakeholder, business, operational, trust and economic results.
7. **Scale by evidence.** Expand only where the operating model, AOP, harness, agent management, trust controls and outcome evidence are demonstrably sufficient for the risk and context.

## 10. Programme responsibilities and change boundaries

| Subject | Authority | Required treatment |
|---|---|---|
| Enterprise Agentic Operations operating model | Agentic-Operation | Own enterprise design, adoption, roles, capabilities, governance and performance |
| AI Agent Profile, Bootstrap and Card | Agentic-Operation | Maintain the agent management contracts and their conformance |
| Model Management Authority | Agentic-Operation | Govern enterprise model records, approvals, provenance and lifecycle integration |
| AOP concept and six-level hierarchy | AOP Foundations | Do not redefine in this organization |
| AOP eight-dimension model, schema and normative clauses | AOP Specification | Integrate by reference and versioned contract |
| AOP trust architecture and harness execution | AOP Architecture and Reference Harness | Preserve AOP programme ownership; map enterprise requirements to the architecture |
| AOP conformance and certification | AOP Conformance | Do not substitute Agentic-Operation CI for AOP conformance |
| Cross-programme integration | Jointly governed | Agree versioned contracts and change impacts with both authorities |
| Enterprise outcome and value realization | Agentic-Operation, with business owners | Define measures and evidence; do not confuse AOP conformance with business value |

Any change to AOP definitions, normative clauses, schemas, harness semantics or AOP conformance must be raised and approved through the AOP programme's governance. This review creates no such change.

## 11. Review findings register

| Finding | Severity | Finding statement | Disposition |
|---|---|---|---|
| OAR-01 | Critical planning gap | Application-level authentication, authorization and TLS are not demonstrated in the inspected reference service implementations | Define and implement a secure deployment profile before external exposure |
| OAR-02 | High | No repository evidence of deployed services, availability SLOs, monitoring or accountable operational support | Treat all services as reference implementations until E4 evidence exists |
| OAR-03 | High | Health reporting includes stubbed or fixed healthy states | Replace with observed health and readiness evidence |
| OAR-04 | High | No Agentic-Operation integrated end-to-end execution gate was identified | Establish a version-pinned multi-service reference acceptance scenario |
| OAR-05 | High | Enterprise trust and human-agent authority need a coherent organizational policy layer around the AOP enforcement model | Develop enterprise governance and trust model without duplicating AOP normative clauses |
| OAR-06 | High | Enterprise outcome and value evidence is not established | Develop outcome measurement and evaluation approach for selected value streams |
| OAR-07 | Medium | Cryptographic verification is optional in the default Agent Conformance run | Make the evidence claim explicit and define profiles where cryptographic verification is mandatory |
| OAR-08 | Medium | Agent Registry README uses production wording inconsistent with the organization's reference-implementation status | Correct the claim or provide E4 evidence |
| OAR-09 | Medium | Several service README licence labels conflict with repository LICENSE files | Reconcile documentation with authoritative licence files |
| OAR-10 | Medium | SOP-to-AOP adoption path is conceptually described but not yet represented as a complete enterprise integration and evidence workflow in this organization | Develop the enterprise transformation reference path with AOP programme participation |

Severity here indicates planning urgency, not a formal risk rating or an assertion of a confirmed production incident.

## 12. Acceptance conditions for a future enterprise operational claim

The organization should not describe the reference stack or a deployment as enterprise-operational until the relevant scope has evidence for, at minimum:

- named service and business owners;
- approved architecture and threat model;
- authenticated and authorized access for users, agents, services and workloads;
- encrypted and controlled service communication;
- protected secrets, credentials and signing keys;
- enforceable tool, data and egress restrictions;
- version-pinned AOP, agent, model, skill, tool and harness dependencies;
- independent authority enforcement and fail-closed behaviour;
- tested approval, escalation, stop, recovery and revocation paths;
- meaningful health, readiness, telemetry, monitoring and alerting;
- repeatable integration and conformance tests;
- backup, recovery, incident and change-management procedures;
- defined SLOs and evidence of performance against them;
- audit records with integrity and appropriate retention;
- an accountable business owner and outcome baseline;
- independently reviewable evidence of operational and business outcomes.

These conditions must be tailored to the deployment's risk, regulatory context and business criticality. They are a planning checklist, not a claim that one universal deployment profile is suitable for every use case.

## 13. Conclusion

Agentic-Operation has the beginnings of an enterprise-facing management and reference implementation estate. The AOP programme supplies a complementary and more detailed engineering foundation for specifying, constraining, executing and assuring agentic work.

The enterprise transformation is not simply from human execution to agent execution, or from SOP documents to AI-generated procedures. It is a shift from procedure-led work with predominantly predetermined execution paths toward semantically grounded, explicitly authorized, coordinated and evidence-assured operational work in which humans and non-human agents participate.

AOP provides the operational specification and execution discipline. AI Agent Standards provide identity, provisioning, discovery and management contracts. The enterprise trust model binds identity, capability, authority, context, execution, oversight and accountability. Operational assurance demonstrates that controls work. Outcome assurance demonstrates that the enterprise is better off.

The immediate objective should be to make the reference estate secure, integrated, observable and testable in a controlled environment, then use it to demonstrate one complete SOP-to-AOP value-stream transformation with traceable execution and independently assessed outcomes. Production readiness and enterprise-scale claims should follow evidence, not precede it.

---

## Evidence sources

### Agentic-Operation

- [Organization profile](https://github.com/Agentic-Operation/.github/blob/main/profile/README.md)
- [Agent Profile Management / Spec-443](https://github.com/Agentic-Operation/agent-profile-management)
- [Agent Bootstrap Management / Spec-444](https://github.com/Agentic-Operation/agent-bootstrap-management)
- [Agent Discovery Card / Spec-445](https://github.com/Agentic-Operation/agent-discovery-card)
- [Agent Registry source](https://github.com/Agentic-Operation/agent-registry/tree/main/src)
- [Model Authority source](https://github.com/Agentic-Operation/model-authority/tree/main/src)
- [Rollout Controller source](https://github.com/Agentic-Operation/agent-rollout-controller/tree/main/src)
- [Tool/MCP Manager source](https://github.com/Agentic-Operation/tool-mcp-manager/tree/main/src)
- [Agent Orchestrator source](https://github.com/Agentic-Operation/agent-orchestrator/tree/main/src)
- [Agent Conformance](https://github.com/Agentic-Operation/agent-conformance)
- [Agent Standard Docs](https://github.com/Agentic-Operation/agent-standard-docs)

### Agentic Operating Procedure

- [AOP Foundations](https://github.com/agentic-operating-procedure/aop-foundations)
- [AOP Founding Paper](https://github.com/agentic-operating-procedure/aop-foundations/blob/main/docs/aop-founding-paper-concept-scope.md)
- [AOP Specification](https://github.com/agentic-operating-procedure/aop-spec)
- [AOP Normative Security Clauses](https://github.com/agentic-operating-procedure/aop-spec/blob/main/docs/aop-normative-security-clauses-specification-scope.md)
- [AOP Run and Action Semantics](https://github.com/agentic-operating-procedure/aop-spec/blob/main/docs/aop-run-and-action-semantics-specification-scope.md)
- [AOP Evidence and Replay Semantics](https://github.com/agentic-operating-procedure/aop-spec/blob/main/docs/aop-evidence-and-replay-semantics-specification-scope.md)
- [AOP Trust Architecture](https://github.com/agentic-operating-procedure/aop-architecture/blob/main/docs/aop-trust-architecture-architecture-scope.md)
- [AOP Reference Harness](https://github.com/agentic-operating-procedure/aop-reference-harness)
- [AOP Conformance](https://github.com/agentic-operating-procedure/aop-conformance)
- [AOP Governance](https://github.com/agentic-operating-procedure/aop-governance)
