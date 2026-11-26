# CR-AO-ORG-001 — Profile Content Preservation Mapping

| Field | Value |
|---|---|
| Change request | [CR-AO-ORG-001](../../change-requests/CR-AO-ORG-001-organization-purpose-and-authority.md) |
| Controlling baseline | [AO-CBC-001](../architecture/AO-CBC-001-conceptual-baseline.md) |
| Target | [Organization profile](../../profile/README.md) |
| Status | Implementation merged to `main`; post-merge verification recorded below |

This register maps every preservation item in CR-AO-ORG-001 to its destination in the revised organization profile. The original 290-line profile body has been preserved in substance, with its content order and technical details retained. The implementation adds an enterprise operating-model orientation before that material, updates the top-level title from “Agentic Operation” to “Agentic Operations”, and rewrites the legacy opening paragraph so that agent-management standards are correctly positioned as a foundational management layer within the wider enterprise operating model. No original technical section, scenario, table, diagram, repository/service description, persona guidance, AI-agent instruction, onboarding step or contribution statement was removed.

| ID | Existing content | Revised profile destination | Disposition |
|---|---|---|---|
| P-01 | Agentic AI Management Standards positioning and organizational problem statement | [Enterprise Agentic Operations](../../profile/README.md#enterprise-reference-model-and-detailed-agent-management); original opening and [Agentic AI Management Standards](../../profile/README.md#agentic-ai-management-standards) | Retained and contextualized within the enterprise operating model |
| P-02 | Objective: know agents, accountability, authority, dependencies, deployment and evidence | [Agentic AI Management Standards](../../profile/README.md#agentic-ai-management-standards) | Original objective retained verbatim |
| P-03 | Why agent management needs an operating model and failure cases | [Why agent management needs an operating model](../../profile/README.md#why-agent-management-needs-an-operating-model) | Original explanation and all five failure cases retained |
| P-04 | Five-activity agent lifecycle and feedback loop | [The agent management model](../../profile/README.md#the-agent-management-model) | Original Mermaid diagram and explanation retained |
| P-05 | Spec-443/444/445 triad, repositories, contract forms and questions | [The standard at a glance](../../profile/README.md#the-standard-at-a-glance-three-agent-contracts-and-model-governance) | Original table and descriptions retained |
| P-06 | Model Management Authority and model assignment chain | [The standard at a glance](../../profile/README.md#the-standard-at-a-glance-three-agent-contracts-and-model-governance) | Original fourth-pillar explanation and assignment chain retained |
| P-07 | TMF443/444/445, IG1412, A2A, WoA, MCP, ODP-EL, NIST AI RMF, Sigstore/Rekor mappings | [The standard at a glance](../../profile/README.md#the-standard-at-a-glance-three-agent-contracts-and-model-governance) | Original mapping paragraph and qualification retained; links and versions remain subject to source-level maintenance |
| P-08 | Four business scenarios | [What this enables: illustrative business scenarios](../../profile/README.md#what-this-enables-illustrative-business-scenarios) | Customer service, finance operations, IT incident response and partner-facing service all retained |
| P-09 | Reference architecture and explanation | [Reference architecture](../../profile/README.md#reference-architecture) | Original Mermaid architecture and explanatory qualification retained |
| P-10 | Normative standards repository map | [Repository map](../../profile/README.md#repository-map) | All three standards repositories and descriptions retained |
| P-11 | Runtime service map and details | [Repository map](../../profile/README.md#repository-map) | All six runtime/reference service descriptions, ports and details retained |
| P-12 | Assurance pipeline and lifecycle controls | [Assurance: from authoring to runtime](../../profile/README.md#assurance-from-authoring-to-runtime) | Original diagram and four control explanations retained |
| P-13 | Autonomy, authority, accountability and diagram | [Autonomy, authority, and accountability](../../profile/README.md#autonomy-authority-and-accountability) | Original explanation, diagram and accountability path retained |
| P-14 | L1-L5, impact radius, ODP-EL, cryptographic integrity, model governance, conformance gates | [Autonomy, authority, and accountability](../../profile/README.md#autonomy-authority-and-accountability) | All six governance bullets retained |
| P-15 | Persona table and starting points | [Who this organization serves](../../profile/README.md#who-this-organization-serves) | Original ten-row persona table retained under its original heading; new enterprise-level persona orientation is separately presented under [Enterprise audiences](../../profile/README.md#enterprise-audiences) |
| P-16 | AI-agent consumption guidance, seven-step instructions and machine interfaces | [Guidance for AI agents consuming this organization](../../profile/README.md#guidance-for-ai-agents-consuming-this-organization) | All seven steps and machine-interface descriptions retained |
| P-17 | Get-started paths, quickstarts, reference stack and conformance command | [Get started](../../profile/README.md#get-started) | All five onboarding paths retained |
| P-18 | Contribution guidance and licensing statement | [Contributing](../../profile/README.md#contributing) | Contribution guidance retained; the former organization-wide Apache-2.0 claim was corrected to reflect repository-specific MIT and Apache-2.0 licences verified from the LICENSE files |

## Implementation additions

The revised profile adds the following enterprise-facing orientation without replacing the existing agent-management material:

- Enterprise definition and purpose of Agentic Operations.
- Enterprise operating model concerns and the operating model / operating mode distinction.
- Explicit integration boundary with the AOP programme and its six-level hierarchy.
- Links to AOP repositories confirmed in the live organization inventory.
- Five-stage conceptual transformation progression, explicitly not a maturity model.
- Persona orientation for enterprise executives, business/process owners, architects, engineering, operations, risk, consultants and AI tooling.
- Authority-aware documentation map linking AO-CBC-001 and CR-AO-ORG-001.

## AOP inventory verification note

The live AOP organization inventory confirmed `aop-foundations`, `aop-spec`, `aop-architecture`, `aop-governance`, `aop-landscape`, `aop-context-graph`, `aop-toolkit`, `aop-reference-harness`, `aop-registry` and `aop-conformance`.

The AOP Governance repository's estate table also names `aop-evaluation`, `aop-adoption` and `aop-examples`, but those three were absent from the live organization inventory checked for this implementation. The profile therefore records the discrepancy and does not link to those repositories as if they were available. This does not alter AOP's governance plan or assign those responsibilities to Agentic-Operation.

## Post-merge verification

- PR #4 implementation and PR #5 navigation correction are both merged to `main`; PR #5 merge commit: `20ada08477294de95c588d94bee14f4b3513322c`.
- Re-fetched the current profile and preservation register from `main`; the profile is 434 lines and the P-15 mapping distinguishes the original persona table from the enterprise-audience section.
- Confirmed the live Agentic-Operation organization contains all ten repositories linked by the profile (three specification repositories, six reference-management/service repositories, and the documentation repository); the six linked persona/quick-start communication documents checked also exist.
- Inspected the three specification documents. Spec-443, Spec-444 and Spec-445 each identify themselves as normative drafts, v1.0.0-alpha. The profile now states that maturity explicitly and does not imply final approval.
- Inspected all six reference-management/service READMEs and the documentation repository README. Local run commands and reference responsibilities are documented; repository inspection does not establish live deployment, reachability, production readiness or operational support. The profile now states this limitation and qualifies the listed ports as local run defaults.
- Latest observed CI runs for the three specification repositories and all six service/reference repositories were successful. The `agent-standard-docs` repository has three latest `docs-lint` failures; the latest log identifies five Markdownlint errors in `communication/10-org-landing-page.md` (MD022 and MD036). This is recorded as an outstanding documentation-repository issue, not attributed to the Agentic-Operation profile.
- The `.github` repository has no Actions workflow runs returned for the PR #5 merge commit or `main`; therefore no CI pass is claimed for the organization profile repository.
- Kept this implementation within `Agentic-Operation/.github`; no AOP repository or agent-management normative contract was modified.

## Remaining acceptance limitations

- Live deployment and health of the six reference services have not been independently established. The profile describes reference implementations, not verified production endpoints.
- The `agent-standard-docs` Markdown lint failure remains to be remediated in that repository under its own scoped change.
- Rendered Markdown/Mermaid presentation and external standards-link freshness have not been exhaustively certified.

These limitations do not invalidate the profile's repository inventory or its conceptual authority boundaries, but they prevent claiming full operational verification of the wider reference-service estate.
