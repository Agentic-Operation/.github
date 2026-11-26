# Traditional-to-Agentic Architecture Transformation Patterns

Patterns describe recurring design approaches. They are not prescriptions, reference implementations or claims of production validation. Select a pattern only after establishing the outcome, work boundary, service contracts, authority and operational constraints.

## Pattern structure

Each pattern records context, problem, forces, intent, applicability, preconditions, design, work-model implications, authority and controls, implementation considerations, failure modes, trade-offs, verification and related patterns.

## Pattern P-01 — Legacy Service Agent Enablement

**Status:** Initial practitioner pattern.

### Context
An existing information-system service or deterministic capability remains useful, but a bounded agent use case requires controlled access to it.

### Problem
Directly exposing a legacy endpoint or credential to an agent can create excessive authority, ambiguous contracts, weak auditability and unsafe side effects. Replacing the service may be unnecessary and disproportionately risky.

### Forces
- Preserve proven deterministic behaviour and existing investment.
- Provide a stable, consumer-appropriate contract.
- Restrict identity, scope, data and action authority.
- Make invocation, result, error and side effect observable.
- Avoid coupling agent behaviour to undocumented implementation details.

### Intent
Enable an agent to consume a capability through a governed interface while retaining service ownership and independent enforcement of authorization.

### Preconditions
- Service owner and system of record are known.
- Contract, consumers, side effects and failure semantics are understood.
- Identity and least-privilege access can be enforced externally.
- Rate, scope, idempotency and audit requirements are defined.
- Human approval and recovery paths are specified where required.

### Design
1. Preserve the service and its authoritative contract.
2. Introduce or validate a narrow adapter/interface appropriate to the agent use case.
3. Bind a workload identity and narrowly scoped permissions.
4. Enforce policy and authorization outside the model context.
5. Validate input, output, schema, idempotency and side effects.
6. Record caller, AOP/run identity, policy decision, request, response, correlation ID and outcome.
7. Provide timeout, retry, denial, escalation and revocation behaviour.
8. Keep the service owner accountable for service availability and contract evolution.

### Work-model implications
The agent may prepare or invoke an approved operation only within the delegated work scope. Invocation does not transfer business accountability or service ownership to the agent.

### Failure modes
Credential leakage; broad tool permissions; hidden side effects; replay or duplicate actions; stale context; contract drift; missing audit linkage; agent treating a successful HTTP response as proof of business outcome.

### Trade-offs
Adds adapter, policy and observability work. It can preserve legacy investment but does not resolve poor internal quality or unsuitable service semantics.

### Verification
Contract and schema tests; negative authorization tests; duplicate/replay tests; timeout and recovery tests; audit correlation; human intervention tests; outcome verification independent of transport success.

### Inappropriate when
The service is unsafe, ownerless, semantically unknown, or cannot be bounded and monitored. In those cases remediate, redesign or do not expose it.

## Pattern P-02 — Human Approval Boundary

**Status:** Initial practitioner pattern.

### Context
An agent can analyse a case and prepare an action, but the action has material consequence, requires accountable judgment, or is subject to policy/regulation.

### Problem
A human-in-the-loop label is insufficient if approval is a cosmetic confirmation, can be bypassed, or does not bind to the exact action and context reviewed.

### Forces
- Preserve accountable human decision rights.
- Avoid unnecessary human review of low-risk deterministic work.
- Ensure the approver sees sufficient evidence and consequences.
- Prevent approval reuse, substitution or time-of-check/time-of-use drift.
- Support rejection, modification, escalation and pause.

### Intent
Make the human authorization point explicit, informed, enforceable and auditable.

### Preconditions
A named authority role, approval criteria, decision evidence, action identity and enforcement point exist.

### Design
1. Define which actions require approval and why.
2. Have the agent prepare a structured proposal with evidence, uncertainty, impact and alternatives.
3. Bind approval to a unique action proposal, context/version and expiry.
4. Authenticate the approver and verify role/authority externally.
5. Enforce approval at the execution boundary; do not rely on agent compliance.
6. Reject stale, modified, duplicated or out-of-scope approvals.
7. Record approval, rejection, abstention, escalation and execution outcome.
8. Provide pause, revoke and terminate controls.

### Work-model implications
The agent may investigate and recommend; the authorized human decides. Execution may be performed by a deterministic service or agent only after the external control confirms valid authorization.

### Failure modes
Rubber-stamping; approval fatigue; unclear accountability; approval bound to a summary rather than the executable action; stale context; unauthorized substitution; no intervention path.

### Trade-offs
Introduces latency and human capacity requirements. Risk-based approval design is necessary; indiscriminate approval gates can make operations ineffective.

### Verification
Exercise approval, rejection, expiry, revocation, altered payload, wrong role, duplicate request, escalation, pause and termination through real enforcement paths.

### Inappropriate when
No accountable authority exists, the human cannot meaningfully assess the proposal, or the control cannot be enforced. Redesign the authority model before delegation.

## Pattern P-03 — Deterministic Core with Agentic Coordination

**Status:** Initial practitioner pattern.

### Context
Existing deterministic services perform reliable, testable operations, while the work requires contextual interpretation, dynamic sequencing or coordination across services and people.

### Problem
A fixed workflow may be too brittle for variable cases, but replacing deterministic functions with probabilistic agent behaviour would reduce predictability and assurance.

### Forces
- Preserve deterministic guarantees where they matter.
- Enable adaptive coordination where justified.
- Keep service contracts and system ownership clear.
- Control agent decisions, tool use and side effects.
- Verify end-to-end outcomes, not merely orchestration completion.

### Intent
Retain deterministic execution for well-defined operations while assigning bounded interpretation and coordination to governed agents.

### Design
1. Identify stable functions and preserve them as deterministic services.
2. Define the agent's coordination scope, context and allowed decision space.
3. Expose services through typed, versioned contracts.
4. Enforce action permissions and policy outside the agent.
5. Require preconditions and postconditions for consequential operations.
6. Define conflict resolution, retry, timeout, compensation and human escalation.
7. Correlate agent decisions with service invocations and verified outcomes.
8. Keep deterministic safety interlocks and invariants authoritative.

### Work-model implications
Agents may select and sequence permitted operations based on context; deterministic services execute defined functions. Humans retain reserved decisions and intervention rights.

### Failure modes
Agent bypasses deterministic invariants; orchestration hides service failure; uncontrolled loops; ambiguous responsibility; non-repeatable decisions without evidence; coordination state diverges from system-of-record state.

### Trade-offs
Combines the adaptability of agentic coordination with the operational discipline of deterministic services, at the cost of additional orchestration, state, policy and observability complexity.

### Verification
Service contract tests; invariant/property tests; scenario and adversarial tests; bounded-loop tests; replay and traceability; failure injection; outcome checks against authoritative systems.

### Inappropriate when
The work is fully stable and deterministic with no material coordination benefit, or required context and enforcement cannot be provided.

## Pattern P-04 — Exception-Driven Agentic Operations

**Status:** Initial practitioner pattern.

### Context
Most cases follow a stable, well-understood path, but exceptions require interpretation, investigation, cross-system context or coordination.

### Problem
Automating the normal path alone leaves expensive exception queues; delegating all cases to agents adds unnecessary uncertainty and cost.

### Forces
- Preserve predictable normal-case execution.
- Improve exception diagnosis and resolution.
- Avoid allowing an exception classifier to silently redefine policy.
- Maintain clear routing, ownership and escalation.
- Learn from recurring exceptions through controlled process change.

### Intent
Use deterministic handling for validated normal cases and governed agentic support or execution for bounded exception classes.

### Design
1. Define normal-case conditions and exception taxonomy with process owners.
2. Route using deterministic rules where reliable.
3. Capture evidence and context for each exception.
4. Assign agents only to exception classes with explicit scope and authority.
5. Require human escalation for unresolved, high-consequence or out-of-policy cases.
6. Verify resolution against authoritative state and outcome conditions.
7. Track recurrence, false classification, unresolved cases and policy drift.
8. Feed recurring patterns into governed process, service or rule redesign.

### Work-model implications
Normal work may remain deterministic. Agents assist or execute selected exception work. Process owners retain authority over changes to the exception taxonomy and operating rules.

### Failure modes
Normal cases misclassified as exceptions; exceptions hidden by over-broad rules; agents normalize workarounds; escalation queues grow; no learning loop; resolution recorded without verifying actual state.

### Trade-offs
Can focus agent capability where it adds value, but requires good case classification, exception ownership and measurement.

### Verification
Classification precision/recall where labels are valid; false-route scenarios; exception coverage; escalation and recovery tests; recurrence analysis; outcome verification and review of policy changes.

### Inappropriate when
There is no reliable distinction between normal and exceptional work, or the exception evidence is too weak to define bounded responsibilities.

## Pattern selection

Patterns may be combined, but do not combine them by default. Record the context, alternatives, selected pattern(s), rejected alternatives, assumptions, controls, verification and limitations. A pattern application is not evidence of production readiness.
