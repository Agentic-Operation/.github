# CR-AO-ORG-002 — Organization Licence Unification on Apache-2.0

| Field | Value |
|---|---|
| Change ID | CR-AO-ORG-002 |
| Title | Unify every repository in the Agentic-Operation organization on Apache-2.0 |
| Version | 0.1.0 |
| Status | Accepted |
| Change class | Organization profile and documentation governance |
| Owning organization | Agentic-Operation |
| Target repositories | `.github`, `agent-registry`, `model-authority`, `agent-rollout-controller`, `agent-orchestrator`, `tool-mcp-manager`, `agent-conformance`, `agent-standard-docs` |
| Controlling baseline | [AO-CBC-001 — Conceptual Baseline and Cross-Programme Boundary Contract](../architecture/AO-CBC-001-conceptual-baseline.md) |
| Related programme | [agentic-operating-procedure](https://github.com/agentic-operating-procedure) |
| Target artefacts | `LICENSE`, `README.md`, `CHANGELOG.md`, `profile/README.md` |

## 1. Change summary

This change unifies the licensing of the Agentic-Operation organization on Apache-2.0, replacing the repository-specific licence matrix recorded in the organization profile.

- The three specification repositories (`agent-profile-management`, `agent-bootstrap-management`, `agent-discovery-card`) already carry Apache-2.0 and are unchanged.
- Eight repositories switch from MIT to Apache-2.0: the organization profile repository (`.github`), the six reference/service repositories (`agent-registry`, `model-authority`, `agent-rollout-controller`, `agent-orchestrator`, `tool-mcp-manager`, `agent-conformance`) and `agent-standard-docs`. Six of these already state `License: Apache-2.0` in their READMEs while their `LICENSE` files remained MIT; this change makes the files agree with the stated intent.
- The organization profile's licensing paragraph is updated to state one licence for the organization.
- Each switched repository records the change in its `CHANGELOG.md` under `[Unreleased]`.

## 2. Problem and rationale

The profile stated that licensing is repository-specific (Apache-2.0 for the specification repositories, MIT for the rest), which leaves a licence matrix in the reader's path and a documented disagreement in six repositories whose READMEs claim Apache-2.0 over MIT `LICENSE` files. Apache-2.0 keeps the permissive character of MIT and adds an explicit patent grant, contribution terms and a notice format suited to a programme that publishes executable services and normative standards documents. The sibling programme, Agentic Operating Procedure, unified on Apache-2.0 through its CR-046 and ADR-0013; one licence across both organizations removes the matrix entirely.

## 3. Scope and target artefacts

- `LICENSE` in the eight listed repositories: the canonical Apache-2.0 text, copyright holder retained as `Agentic Operation`.
- `agent-standard-docs/README.md`: the licence statement line changes from MIT to Apache-2.0.
- `profile/README.md` in `.github`: the licensing paragraph is rewritten to state the unified licence.
- `CHANGELOG.md` in each switched repository: one `[Unreleased]` entry referencing this change request.
- Not in scope: any content beyond licence and attribution text; the historical organization records; the Agentic Operating Procedure organization's repositories (recorded there as CR-046).

## 4. Acceptance criteria

- GitHub licence detection reports Apache-2.0 for all eleven repositories in the organization.
- No `LICENSE` file in the organization contains MIT text; every README licence statement agrees with its repository's `LICENSE` file.
- The organization profile's licensing paragraph states the unified licence.
- Existing CI in the touched repositories passes.

## 5. Out of scope

- The Agentic Operating Procedure organization: its unification is recorded as CR-046 with ADR-0013 in `aop-governance`.
- Historical records that mention the earlier MIT licences: left as written.
- Any normative or implementation content: no service, schema, validator or document content changes.

## 6. Implementation record

Implemented on 2026-11-29. Each switched repository lands through its own pull request referencing this change request.
