# Architecture Transformation Decision Frameworks

These frameworks support explicit, evidence-grounded decisions. They are not automated decision engines and do not prescribe universal scores or weights.

## 1. Keep two decision dimensions separate

A work disposition describes how work should be performed. An architecture realization disposition describes how a technical responsibility should be realized. They are related but not interchangeable.

## 2. Work disposition

| Disposition | Meaning | Conditions to examine |
|---|---|---|
| Human-owned | Human retains responsibility for judgment, authorization or execution | Accountability, expertise, consequence, regulation and ambiguity |
| Human-assisted | Software or AI supports a human who remains responsible | Explainability, usability, evidence quality and decision support |
| Agent-assisted | Agent analyses, prepares or recommends without independently completing authority-bearing action | Context quality, recommendation verification and clear human decision boundary |
| Agent-executed | Agent performs bounded work under externally enforced delegated authority | Explicit scope, least privilege, reversibility, monitoring, limits, escalation and independent verification |
| Deterministic automation | Stable, explicit rules are executed by deterministic software | Rule stability, testability, predictable outcomes and exception handling |
| Redesigned | Work is changed before or instead of automating its current form | Unnecessary steps, poor boundaries, duplicate work and outcome alignment |
| Eliminated | Work is removed after confirming it is not required for outcome, obligation or control | Downstream dependencies, regulatory obligations and hidden control purpose |
| Unresolved | Evidence, authority or controls are insufficient for a safe disposition | Missing owner, uncertain rules, weak evidence or unacceptable residual risk |

### Work disposition procedure

1. Define a bounded work unit and its outcome contribution.
2. Identify performer, decision-maker, accountable owner and affected stakeholders.
3. Establish inputs, context, rules, exceptions, dependencies and current evidence.
4. Determine whether behaviour is deterministic, interpretive, judgment-intensive or mixed.
5. Assess consequence, reversibility, detectability and recovery.
6. Identify legal, privacy, security, safety, regulatory and policy constraints.
7. Assess whether required context and tools are trustworthy, current and appropriately scoped.
8. Identify approval, escalation, intervention and independent verification requirements.
9. Compare feasible dispositions and document why rejected alternatives are unsuitable.
10. Record the decision, owner, evidence, controls, review trigger and unresolved issues.

An agent-executed disposition requires an enforceable authority boundary outside the agent's own instructions. If that boundary or the verification path is absent, do not describe the work as safely delegable.

## 3. Architecture realization disposition

| Disposition | Meaning | Typical rationale |
|---|---|---|
| Retain | Preserve current implementation and responsibility | Satisfies outcome, contract, quality and operational requirements |
| Wrap | Place a controlled interface or facade around an existing realization | Improve access, isolation or contract stability without internal change |
| Refactor | Change internal structure while preserving externally required behaviour | Reduce complexity or improve maintainability |
| Modularize | Establish clearer internal responsibility and dependency boundaries | Improve cohesion and control change impact |
| Extract | Move a cohesive responsibility into an independently governed component or service | Distinct ownership, lifecycle, scaling or deployment need |
| Integrate | Establish or redesign interaction with another responsibility | Required capability or contract connection is absent or brittle |
| Agent-enable | Make an existing capability safely consumable by an agent | A bounded agent use case exists and interface, context and controls are adequate |
| Replace | Substitute the implementation | Current implementation cannot meet justified target requirements |
| Retire | Remove a no-longer-required realization | Consumers, obligations, data retention and dependencies have been resolved |
| Introduce | Add a new realization for a verified gap | Existing capabilities cannot meet the outcome and a new responsibility is justified |

These are alternatives, not a maturity sequence. Wrapping is not automatically a precursor to extraction; agent enablement does not imply internal refactoring; replacement is not justified solely by technology age.

## 4. Architecture alternative evaluation

Evaluate alternatives against relevant considerations. Do not assign numerical weights by default.

- Outcome contribution and capability coverage.
- Process and work alignment.
- Business and information-system service contract impact.
- Responsibility ownership and lifecycle.
- Cohesion, coupling and change frequency.
- Information ownership, provenance and freshness.
- Runtime dependencies, latency and availability.
- Security, identity, trust and data boundaries.
- Agent authority, risk and deterministic constraints.
- Failure propagation, recovery and reversibility.
- Observability, auditability and evidence quality.
- Maintainability, skills and operational support.
- Delivery, migration and ongoing cost.
- Transition risk, coexistence and rollback.
- Adaptability to foreseeable change.

For each alternative, record:
- requirements satisfied and not satisfied;
- assumptions and evidence;
- trade-offs and failure modes;
- dependencies and prerequisites;
- residual risks;
- reversibility and exit strategy;
- accountable decision authority.

If a quantitative model is useful, define the scale, data source, calibration, weights, sensitivity and limitations explicitly. Do not present uncalibrated scores as objective truth.

## 5. Agent suitability considerations

Assess the characteristics of the work, not merely whether an LLM can produce a plausible response.

| Consideration | Questions |
|---|---|
| Work nature | Is the task interpretive, deterministic, physical, relational or mixed? |
| Context | Is relevant context available, authoritative, current and permitted? |
| Variability | Are cases highly variable or governed by stable rules? |
| Consequence | What harm follows from an incorrect or delayed action? |
| Reversibility | Can an action be safely undone or contained? |
| Detectability | Can errors be detected before harm or outcome failure? |
| Authority | Who owns the decision and what may be delegated? |
| Human judgment | Is professional, ethical or accountable judgment required? |
| Tool/service access | Are tools reliable, scoped, authenticated and observable? |
| Verification | Can outputs and side effects be independently checked? |
| Recovery | Are timeout, retry, duplicate, escalation and fallback paths defined? |
| Economics | Does the proposed approach improve total cost, latency or capacity after control costs? |

The assessment should produce a reasoned disposition and conditions, not a universal agent-readiness score.

## 6. Transition strategy selection

| Strategy | Consider when | Watch for |
|---|---|---|
| Incremental enhancement | Existing architecture is viable and localized improvements address the gap | Accumulation of local fixes without target coherence |
| Modularization first | Internal responsibilities are tangled and extraction would amplify risk | Over-engineering boundaries without ownership need |
| Service wrapping | Legacy capability must remain available behind a stable contract | Wrapper becomes a permanent uncontrolled integration layer |
| Strangler transition | A responsibility can be progressively redirected to a replacement | Routing, data consistency, rollback and dual-running complexity |
| Parallel operation | Critical work requires comparison or controlled migration | Divergent state, duplicated actions and unclear system of record |
| Selective extraction | Responsibility has independent ownership or lifecycle needs | Distributed-systems overhead and data ownership ambiguity |
| Targeted replacement | Existing realization cannot satisfy justified requirements | Migration risk, contract loss and underestimated hidden dependencies |
| Process redesign first | Current work is inefficient or unsuitable for direct automation | Removing controls or local knowledge without understanding purpose |
| Agentic overlay | Existing deterministic services remain useful but coordination or interpretation needs change | Agent becomes an ungoverned control plane or obscures service accountability |
| Hybrid transition | Different work units require different approaches | Inconsistent controls and fragmented operating ownership |

## 7. Decision record requirements

For a material decision, record:
- decision ID, title, status and date;
- scope and affected entities/work units;
- outcome and requirements;
- current-state evidence and assumptions;
- alternatives considered;
- selected disposition and rationale;
- consequences, trade-offs and residual risks;
- authority and accountable owner;
- dependencies and implementation implications;
- verification and acceptance criteria;
- review trigger and superseding decision, if any.

Use the organization's ADR/CR governance where applicable. This template does not establish a replacement governance process.
