# CR-AO-ORG-001 — Organization Purpose and Authority

| Field | Value |
|---|---|
| Change ID | CR-AO-ORG-001 |
| Title | Establish the Agentic-Operation organization as the enterprise-facing authority for Agentic Operations |
| Version | 0.1.0 |
| Status | Proposed |
| Change class | Organization profile and documentation governance |
| Owning organization | Agentic-Operation |
| Target repository | `.github` |
| Controlling baseline | [AO-CBC-001 — Conceptual Baseline and Cross-Programme Boundary Contract](../architecture/AO-CBC-001-conceptual-baseline.md) |
| Related programme | [agentic-operating-procedure](https://github.com/agentic-operating-procedure) |
| Target artefact | `profile/README.md` |

## 1. Change summary

This change establishes the Agentic-Operation GitHub organization as the authoritative enterprise-facing home for **Agentic Operations as an enterprise operating model**.

The organization profile will be evolved from a strong agent-management standards overview into an integrated enterprise-facing entry point that explains:

- what Agentic Operations is and why it matters to an enterprise;
- how the enterprise operating model relates to the broader agentic operating mode;
- how the organization manages AI Agents through its existing standards and services;
- how Agentic Operations integrates with Agentic Operating Procedure (AOP);
- how organizations progress from labs and proofs of concept to operational integration, value-stream transformation and enterprise-scale adoption;
- where each persona should go for authoritative guidance, standards, architecture, implementation and assurance.

This is an additive and organizational change to the profile. It does not authorize the deletion, weakening, silent rewriting or loss of any substantive content currently present in `profile/README.md`.

## 2. Problem and rationale

The current organization profile is a substantive and useful description of the Agentic AI Management Standards and their reference services. It explains the agent lifecycle, Spec-443, Spec-444, Spec-445, Model Management Authority, runtime services, conformance, scenarios, personas and AI-agent consumption.

However, its framing is predominantly centered on the management of AI Agents. That is an essential part of the organization's remit, but it does not yet sufficiently establish the broader enterprise subject: Agentic Operations as an operating model.

This leaves several important questions insufficiently answered for enterprise readers:

1. What changes in the enterprise operating model when work is performed by a coordinated human and non-human workforce?
2. How do business outcomes, value streams, organizational accountability, operating capabilities and governance relate to agent management?
3. What is the relationship between Agentic Operations and the Agentic Operating Procedure programme?
4. Where do AI Agent standards fit relative to operational procedures, skills, harnesses, agents and enterprise governance?
5. How does an organization move from isolated labs and POCs to safe, measurable, enterprise-scale transformation?
6. Where should executives, business owners, architects, engineers, risk teams, consultants and AI agents start?

The organization profile should answer these questions while retaining the existing technical depth and practical utility.

## 3. Authority and semantic baseline

This change is governed by AO-CBC-001.

### 3.1 Agentic Operations

Use the following enterprise operating model definition:

> Agentic Operations is the enterprise operating model through which an organization organizes, governs, executes, measures and continuously improves its work using coordinated human and non-human agents operating within defined intent, context, authority, constraints and accountability.

The profile should explain the enterprise implications: outcomes, value streams, capabilities, organization, workforce, decision rights, bounded autonomy, governance, assurance, performance and continuous improvement.

### 3.2 Operating model and operating mode

The profile must distinguish:

- **Enterprise operating model:** how the enterprise intentionally designs, organizes, governs, operates, measures and evolves its agentic way of working to achieve business outcomes.
- **Broader operating mode:** the resulting regime of operational work and participation by human and non-human actors.

The AOP Foundations six-level hierarchy remains intact. In particular, the profile must not imply that Agentic-Operation has changed AOP's level-6 concept or assumed authority over the AOP conceptual hierarchy.

### 3.3 Relationship with Agentic Operating Procedure

The profile must identify the AOP programme as the engineering and specification authority for Agentic Operating Engineering and Agentic Operating Procedure.

The relationship should be stated clearly:

- Agentic Operations defines the enterprise operating model and the conditions, outcomes and governance under which agentic work takes place.
- Agentic Operating Engineering provides the discipline for engineering agentic operational work.
- Agentic Operating Procedure provides the structured operational specification governing that work.
- Agent Skills provide reusable capabilities.
- Domain Agent Harnesses provide controlled execution environments.
- Agents are execution actors operating within declared authority and constraints.

The profile must link to the AOP organization and relevant authoritative repositories. It must not copy AOP normative requirements or present Agentic-Operation repositories as the authority for AOP schemas, dimensions, conformance or programme governance.

### 3.4 Agent management standards

The existing Agentic-Operation standards remain central to the organization's remit:

- Spec-443 — AI Agent Profile.
- Spec-444 — AI Agent Bootstrap.
- Spec-445 — AI Agent Card.
- Model Management Authority.

The profile must preserve their established purposes and their relationships to the management services, conformance controls and runtime environment. They are a core management foundation within the broader enterprise operating model, not a substitute for the operating model or AOP.

## 4. Objectives

The change has the following objectives:

1. Establish the organization's enterprise-facing purpose and authority.
2. Present Agentic Operations as an enterprise operating model, not merely an AI Agent management lifecycle.
3. Preserve and make more discoverable the existing agent management standards, reference services and technical guidance.
4. Explain the complementary relationship with the AOP programme and preserve programme boundaries.
5. Explain the enterprise adoption journey from experimentation to value-stream transformation and enterprise-scale operation.
6. Improve navigation for enterprise personas and consulting/advisory use.
7. Provide reliable navigation for AI agents and automated tools, with clear precedence for normative sources.
8. Establish the organization profile as the entry point to a growing, coherent documentation and repository estate.

## 5. Scope

### 5.1 In scope

- Rework the information architecture and narrative flow of `profile/README.md`.
- Add an authoritative Agentic Operations purpose and definition section.
- Add the operating model versus operating mode distinction.
- Add a conceptual relationship section for Agentic Operations, AOP, Agent Skills, Domain Agent Harnesses and Agents.
- Add explicit AOP programme boundary and repository links.
- Add an enterprise transformation progression, clearly labelled conceptual and non-normative.
- Add persona-oriented navigation for executive, business, architecture, engineering, operations, risk, consulting and AI-agent audiences.
- Add a documentation and repository authority map, distinguishing normative standards, reference services, guidance and external references.
- Add a machine-readable/AI-agent consumption guidance section that establishes authoritative-source precedence.
- Add cross-links to AO-CBC-001 and other approved Agentic-Operation documentation as it becomes available.
- Add or improve diagrams where they clarify the model, lifecycle, boundaries or transformation progression.
- Verify all links, repository names and claims against the live organization estate.

### 5.2 Out of scope

- Renaming the GitHub organization or any repository.
- Changing Spec-443, Spec-444 or Spec-445 semantics, schemas or conformance requirements.
- Changing Model Management Authority contracts or model approval policy.
- Changing the AOP conceptual hierarchy, AOP metamodel, eight dimensions, schemas, conformance clauses, architecture or governance.
- Creating an alternative AOP implementation or duplicating AOP normative material.
- Declaring the five-stage transformation progression to be a maturity model, scoring system or certification scheme.
- Claiming that a particular enterprise has achieved a maturity stage without evidence.
- Prescribing a single vendor, model provider, agent framework or orchestration platform.
- Removing existing technical scenarios, diagrams, standards mappings, runtime details, repository descriptions, persona guidance or AI-agent instructions.

## 6. Normative change requirements

### ORG-001 — Organization purpose

The opening of the profile MUST establish Agentic Operations as the enterprise operating model and state the organization's role in advancing it.

### ORG-002 — Enterprise relevance

The profile MUST explain the implications for business outcomes, value streams, operating capabilities, organizational accountability, workforce, governance and performance.

### ORG-003 — Agent management continuity

The profile MUST retain and clearly position the existing Agentic AI Management Standards and reference management services as foundational components of the organization.

### ORG-004 — AOP boundary

The profile MUST explicitly link to the Agentic Operating Procedure programme and explain its distinct engineering/specification authority. It MUST NOT imply that Agentic-Operation owns or may redefine AOP normative artefacts.

### ORG-005 — Conceptual consistency

The profile MUST conform to AO-CBC-001, including the distinction between enterprise operating model and broader operating mode and the preserved AOP six-level hierarchy.

### ORG-006 — Adoption progression

The profile MUST explain the progression from experimentation to controlled adoption, operational integration, value-stream transformation and agentic enterprise. It MUST label this as a conceptual progression until a separate maturity model is approved.

### ORG-007 — Persona navigation

The profile MUST provide meaningful entry points for at least:
- enterprise executives and transformation leaders;
- business leaders, process owners and business analysts;
- enterprise, business and solution architects;
- AI, platform and software engineers;
- operations and service management;
- risk, security, compliance and assurance;
- consultants and transformation practitioners;
- AI agents and automated tooling.

### ORG-008 — Source authority

The profile MUST distinguish normative specifications, schemas and conformance requirements from reference implementations, explanatory documentation, examples and external industry references.

### ORG-009 — AI-agent consumption

The profile MUST instruct AI agents and automated tools to follow the normative source for the task, verify versions and dependencies, respect authority boundaries, and distinguish requirements from examples and claims.

### ORG-010 — Preservation

All substantive content in the existing profile MUST be retained in the revised profile or relocated to a clearly linked, maintained authoritative document. No content may be silently dropped.

### ORG-011 — Repository accuracy

All repository links, names, claims about implementation status, service ports, standards references and external references MUST be checked against their current authoritative sources before publication.

### ORG-012 — Maintainability

The profile MUST serve as an orientation and navigation layer, not become the sole repository for detailed normative specifications or long-form technical documentation.

## 7. Existing profile content preservation register

The current `profile/README.md` on the baseline commit contains 290 lines. The following register identifies the substantive content that must remain available after the change. The implementation PR MUST include a completed mapping from each item to its location in the revised profile or its new canonical document.

| ID | Existing content | Preservation requirement |
|---|---|---|
| P-01 | Agentic AI Management Standards positioning and organizational problem statement | Retain and integrate into the broader enterprise operating model narrative |
| P-02 | Organizational objective: know which agents exist, accountability, authority, dependencies, deployment and evidence | Retain substantively |
| P-03 | Why agent management needs an operating model and illustrative failure cases | Retain substantively |
| P-04 | Five-activity agent lifecycle and lifecycle feedback loop | Retain diagram and explanation |
| P-05 | Spec-443, Spec-444 and Spec-445 triad, repositories, contract forms and questions answered | Retain all rows and descriptions |
| P-06 | Model Management Authority as fourth pillar and model assignment chain | Retain |
| P-07 | Standards mappings: TMF443/444/445, IG1412, A2A, WoA, MCP, ODP-EL, NIST AI RMF, Sigstore/Rekor | Retain with current-source verification and precise qualification |
| P-08 | Four illustrative business scenarios: customer service, finance operations, IT incident response, partner-facing service | Retain all four |
| P-09 | Reference architecture diagram and explanation | Retain or replace only with an equivalent/better diagram preserving all relationships |
| P-10 | Repository map for normative standards | Retain all repositories and descriptions, after verification |
| P-11 | Runtime service map and descriptions | Retain all services and technical details, after verification |
| P-12 | Assurance pipeline diagram and lifecycle controls | Retain |
| P-13 | Autonomy, authority and accountability explanation and diagram | Retain |
| P-14 | Governance details: L1-L5, impact radius, ODP-EL, cryptographic integrity, model governance and conformance gates | Retain, with source and version verification |
| P-15 | Persona table and starting points | Retain all personas and improve navigation as required |
| P-16 | AI-agent consumption guidance, seven-step instructions and machine interfaces | Retain |
| P-17 | Get-started paths, quickstarts, reference stack and conformance command | Retain after verification |
| P-18 | Contribution guidance and Apache-2.0 licensing statement | Retain after verification |

Preservation is semantic and functional, not merely a requirement to keep identical wording. However, any substantive rewrite must preserve the original intent, technical relationships and useful operational detail.

## 8. Required target profile information architecture

The implementation SHOULD organize the profile in the following reader-oriented sequence. Headings may be refined if all required content and navigation remain clear.

1. **Agentic Operations** — concise enterprise definition, purpose and proposition.
2. **Why the enterprise operating model is changing** — business and operational rationale.
3. **The Agentic Operations model** — outcomes, value streams, people and agents, capabilities, governance and performance.
4. **How the model is realized** — explicit relationship with AOP and its six-level hierarchy, without redefining it.
5. **AI Agent management standards** — existing triad and Model Management Authority.
6. **Enterprise reference architecture** — relationship between operating model, procedures, agents, management services and runtime.
7. **From experimentation to enterprise transformation** — five-stage conceptual progression.
8. **Use cases and business scenarios** — preserve all four current scenarios and add cross-references where useful.
9. **Governance, authority and assurance** — preserve current material and clarify enterprise-level accountability.
10. **Standards, repositories and documentation map** — authority-aware navigation.
11. **Who this organization serves** — persona navigation.
12. **Guidance for AI agents and automated tooling** — preserve and strengthen current instructions.
13. **Get started and contribute** — preserve practical onboarding guidance.

The implementation MAY keep the current diagrams in their existing locations or reorganize them. Diagram changes MUST preserve the relationships and claims they currently convey.

## 9. Required cross-programme references

The revised profile MUST link to:

- The [Agentic Operating Procedure organization](https://github.com/agentic-operating-procedure).
- AOP Foundations, for the discipline, conceptual hierarchy and definition of AOP.
- AOP Specification, for normative AOP dimensions, model, schemas and conformance.
- AOP Architecture, for the AOP architecture and trust boundaries.
- AOP Governance, for AOP programme change authority.

Links SHOULD also be provided to relevant AOP context, tooling, harness, registry and conformance repositories where they are confirmed in the current AOP estate.

The profile MUST describe these as external programme authorities and MUST NOT imply that Agentic-Operation maintains or controls them.

## 10. Implementation constraints

1. The implementation MUST begin from the merged AO-CBC-001 baseline on `main`.
2. The existing profile MUST be fetched from the target branch immediately before implementation.
3. The implementation MUST use a separate feature branch and pull request.
4. The implementation MUST NOT replace the profile with a shortened summary that drops existing material.
5. If material is moved into separate documentation, the destination MUST be created, linked from the profile and included in the preservation register.
6. Existing normative specifications and implementation repositories MUST NOT be modified as part of this change unless a separate, explicitly approved CR authorizes the change.
7. External standards references and live service claims MUST be verified before retaining them as current facts.
8. The PR MUST include the completed preservation mapping and a summary of any wording or diagram changes.
9. The PR MUST be reviewed for broken links, Mermaid validity, heading anchors, duplicate explanations and contradictory terminology.
10. No claim of implementation, conformance or production readiness may be added without evidence from the relevant repository or system.

## 11. Acceptance criteria

CR-AO-ORG-001 is complete when:

- [ ] The organization profile clearly establishes Agentic Operations as the enterprise operating model.
- [ ] The profile distinguishes the enterprise operating model from the broader operating mode.
- [ ] The AOP six-level hierarchy and programme authority are preserved.
- [ ] The relationship with AOP is explicit, accurate and linked to authoritative sources.
- [ ] Spec-443, Spec-444, Spec-445 and Model Management Authority remain clearly presented and accessible.
- [ ] Existing lifecycle, architecture, assurance, autonomy and governance explanations remain available.
- [ ] All four existing business scenarios remain available.
- [ ] All existing repository and runtime service descriptions remain available and verified.
- [ ] Persona navigation supports the audiences listed in ORG-007.
- [ ] The transformation progression is present and explicitly non-normative.
- [ ] AI-agent consumption guidance retains its substantive instructions and authoritative-source precedence.
- [ ] The get-started and contribution guidance remains available.
- [ ] The preservation register is completed with exact destinations for P-01 through P-18.
- [ ] All links, diagrams, references and implementation claims have been checked.
- [ ] The change is additive or traceably reorganizational, with no unexplained loss of existing content.
- [ ] CI and repository-required checks pass.

## 12. Verification plan

The implementation PR should provide evidence for:

1. **Content preservation:** completed P-01 through P-18 mapping; compare the pre-change and post-change profile content.
2. **Conceptual conformance:** review against AO-CBC-001, especially the operating model/operating mode distinction and programme boundaries.
3. **AOP source verification:** verify linked AOP repositories and cited concepts against their current default-branch content.
4. **Repository accuracy:** validate all Agentic-Operation repository links and service descriptions.
5. **Navigation:** check internal anchors and external links.
6. **Rendering:** validate Mermaid diagrams and Markdown rendering.
7. **Governance:** confirm that no normative standards or external programme-owned files were changed.

## 13. Dependencies and related changes

| Dependency | Relationship |
|---|---|
| AO-CBC-001 | Controlling conceptual and authority baseline |
| Agentic-Operation standards repositories | Existing normative agent management contracts; must remain consistent |
| Agentic-Operation runtime repositories | Existing reference services; profile claims must be verified |
| agentic-operating-procedure | External programme authority for AOP; integration is by explicit boundary and reference |
| TM Forum IG1579 | External industry context for Agentic Operations as an operating model; not a substitute for internal programme authority |

## 14. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Existing agent-management content is lost during reframing | Mandatory preservation register and before/after review |
| Agentic-Operation appears to take ownership of AOP | Explicit boundary language and authoritative links |
| Operating mode and operating model are conflated | Apply AO-CBC-001 definitions consistently |
| Transformation stages are mistaken for a maturity assessment | Label progression conceptual and defer scoring/assessment to a separate CR |
| Profile becomes too long and difficult to navigate | Use clear sections, persona paths and linked canonical documentation without deleting useful content |
| Repository or service descriptions become stale | Verify claims against current repositories and identify canonical sources |
| External standards are overstated as normative dependencies | Distinguish external references from organization-owned contracts |

## 15. Proposed implementation sequence

1. Re-fetch and freeze the current `profile/README.md` baseline from `main`.
2. Verify the merged AO-CBC-001 document and the current AOP reference repositories.
3. Prepare the revised profile using the target information architecture in Section 8.
4. Complete the P-01 through P-18 preservation mapping.
5. Validate all repository links, service claims, diagrams and references.
6. Open a separate pull request containing the profile change and preservation evidence.
7. Review the PR against every acceptance criterion before merge.

---

**End of change request.**
