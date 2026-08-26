---
name: clone-to-platform-pipeline
description: Researches a reference web application and evolves its publicly observable product behavior into a differentiated, independently implemented platform. Use when the user wants to study an app, create a lawful feature inventory, write an evidence-linked business and technical specification, conduct risk review, build an original implementation, audit later changes, or produce a cross-session handoff.
---

# Clone-to-Platform Pipeline

Use this skill to convert **publicly observable product behavior** into an independently designed platform. Preserve customer problems and functional lessons; do not reproduce protected expression, source code, proprietary data, credentials, assets, or access-controlled behavior.

## Operating Principles

1. Treat the reference application as evidence, not as the design authority. Identify the user outcome behind each observed feature before proposing an original solution.
2. Maintain an **evidence ledger**. Mark every claim as `OBSERVED`, `REPORTED`, `INFERRED`, `ASSUMED`, or `DECIDED`; record the public source, access date, confidence, and permitted use.
3. Observe only through authorized, ordinary access. Do not bypass authentication, rate limits, paywalls, technical controls, or terms of service. Do not use deception, pretexting, or unauthorized accounts.
4. Convert observations into functional requirements and independently written UX, architecture, copy, code, and visual design. Attribute external market facts in user-facing research deliverables.
5. Use a clean-room boundary when the source is technically sensitive or the project has elevated IP risk: pass a sanitized functional brief—not raw code, copied assets, or protected expression—to implementation.
6. Define non-functional requirements proportionately. Include accessibility, privacy, authorization, security, reliability, performance, and data-retention decisions when the platform’s risk profile makes them relevant.
7. Keep specifications modular. A change must state its evidence, rationale, scope, acceptance criteria, and downstream impact.

## Workflow

### 1. Constitution, Scope, and Rights Check

Before exploration, capture the product’s intended user, business outcome, differentiation thesis, constraints, and non-negotiables in `constitution.md`.

Record the reference URL, authorized access level, applicable user-provided permissions, and known restrictions in `research_scope.md`. Stop and ask the user if a necessary activity would require access-control bypassing, personal data collection, or ambiguous rights.

Define success in outcomes, not feature count. Identify the one or more customer problems the new platform will solve better, differently, or for a different segment.

### 2. Evidence-Led Discovery

Create `evidence_ledger.md` before collecting detailed observations. Use the fields in `references/evidence_ledger_template.md`.

Document visible navigation, workflows, user roles, inputs, outputs, error states, integration surfaces, pricing signals, and accessible public documentation. Capture screenshots only when necessary and never include sensitive user data.

Separate three artifacts:

| Artifact | Purpose | Prohibited Content |
|---|---|---|
| `discovery_inventory.md` | Publicly observable features and behavior | Copied source code, secrets, credentials, private data |
| `evidence_ledger.md` | Provenance, confidence, permitted use, and interpretation status | Unsupported conclusions represented as facts |
| `opportunity_map.md` | Customer outcomes, problems, opportunities, solution hypotheses, and key assumptions | A feature-for-feature copying mandate |

Use the bundled `references/bundle_analysis_patterns.md` only after confirming that the target and terms permit the activity. Never use it to defeat controls, enumerate private endpoints, obtain secrets, or copy proprietary implementation.

### 3. Opportunity and Market Framing

Map observed solutions to the underlying customer outcome. For each high-value opportunity, state the desirability, viability, feasibility, usability, ethical, and legal assumptions; prioritize assumptions that are both important and weakly evidenced.

Research three to four relevant alternatives where practical, including open-source and commercial options. Describe differentiation in terms of target segment, workflow, trust model, interoperability, economics, or user outcome—not imitation.

Produce `business_plan.md` only when the user needs a business case. Use transparent assumptions, cite market facts, and distinguish estimates from verified data.

### 4. Platform Specification

Write `platform_specification.md` as the source of truth for independent implementation. Include the following sections when applicable:

- Target users, jobs, outcomes, and success measures.
- Role and permission matrix, including API-level authorization expectations.
- Functional requirements, each linked to an evidence-led opportunity or an explicit product decision.
- Data model, data classification, retention, external interfaces, and integration assumptions.
- Original experience and content direction; never reuse reference-brand expression.
- Non-functional requirements with measurable acceptance criteria appropriate to the platform. Select an accessibility target, security controls, privacy decisions, service objectives, and recovery expectations proportionate to risk.
- Open questions, assumption tests, and Architectural Decision Records (ADRs) for consequential choices.

For systems that process sensitive data, money, privileged actions, or untrusted input, add data-flow diagrams that identify trust boundaries, data stores, external entities, and entry points. Include misuse/abuse cases alongside ordinary user stories.

### 5. Adversarial and Quality Review

Do not implement before reviewing the specification against the constitution, evidence ledger, and applicable risk profile.

Review the following lenses and log substantiated findings in `adversarial_review_notes.md`:

| Lens | Review Question |
|---|---|
| Evidence and IP | Is each key requirement traceable, and is the implementation genuinely independent? |
| Product | Does the opportunity map justify the feature, outcome, and differentiation? |
| Security and privacy | Are access, data flows, abuse cases, and mitigations adequate for the risk? |
| Accessibility and usability | Are testable inclusion and interaction criteria specified? |
| Reliability and performance | Are meaningful service objectives, failure behavior, and recovery expectations defined? |
| Delivery | Are dependencies, data migrations, integration contracts, and acceptance criteria implementable? |

Assign severity only when supported by likelihood, impact, and evidence. It is acceptable to find no critical issue; never invent a finding to satisfy a quota. Resolve or explicitly accept material risks before implementation.

### 6. Original Implementation

Build from the validated specification, never from copied reference code or design files.

1. Select the project scaffold and technology only after documenting the decision and constraints.
2. Generate an original information architecture, visual identity, content, component structure, and data model.
3. Implement each requirement with its acceptance criteria and traceability link.
4. Validate core flows, responsive behavior, authorization, accessibility criteria, error states, and relevant non-functional requirements.
5. Run a convergence review: compare implementation, specification, ADRs, and acceptance criteria; log gaps as work items.
6. Save a checkpoint and record test evidence.

Use specialist skills conditionally: `read-special-images` for dense visual evidence, `imagegen` for original visual assets, `automation-and-scheduling` for recurring monitoring, `persistent-computing` for long-lived services, and the appropriate web-development guide after project initialization.

### 7. Delta Audit and Sync

Use this phase when the user asks to audit the reference application or revisit the platform.

1. Re-read the baseline evidence ledger and specification.
2. Re-observe only authorized public behavior and record new evidence separately.
3. Classify each change as `[NEW]`, `[MODIFIED]`, `[REMOVED]`, or `[INVALIDATED]`.
4. Assess product, legal/IP, security, data, UX, and implementation implications.
5. Write `delta_spec_YYYY-MM-DD.md`. Do not silently overwrite the baseline.
6. Decide whether the original platform should adopt, reject, or test the learning; reference-platform changes never automatically become build requirements.

### 8. Master Handoff

Create `MASTER_HANDOFF_<project_name>.md` using `templates/master_handoff_template.md`. Include an artifact index, evidence status, product decisions, ADR index, role/data model, risk decisions, implementation status, unresolved questions, and a Mermaid dependency graph linking evidence to opportunity, specification, implementation, validation, and delta specifications.

End with: **“Read this document and the current Delta Specs before changing the platform.”**

## Completion Criteria

The workflow is complete only when the requested artifacts are traceable, the independent-design boundary is documented, material risk reviews are resolved or accepted, and the next action is explicit. If the reference platform has not been supplied, complete only the preparation and ask for the URL, approved access level, and intended differentiation before discovery.
