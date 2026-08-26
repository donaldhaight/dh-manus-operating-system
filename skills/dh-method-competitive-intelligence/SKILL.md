---
name: dh-method-competitive-intelligence
description: Benchmarks competitors, platforms, or procedural skills against credible evidence and converts validated findings into differentiated, risk-aware specifications and delta plans. Use when the user requests competitor research, platform comparison, an adversarial specification review, a change audit, or a cross-session handoff.
license: Complete terms in LICENSE.txt
---

# DH Method: Competitive Intelligence and Platform Evolution

Use this skill to learn from the market without importing another organization’s protected expression or unverified claims. Competitive research should identify **customer outcomes, operating patterns, risks, and strategic gaps** that support an independently designed product or skill.

## Governing Rules

1. Start with the decision to be made. Specify the user, market question, time horizon, and decisions the research may influence.
2. Prefer primary sources, official documentation, product experience through ordinary authorized access, reputable research, and direct citations. Label all estimates and inferences.
3. Maintain an evidence ledger with source, access date, claim type, confidence, restrictions, and linked decision. Use `OBSERVED`, `REPORTED`, `INFERRED`, `ASSUMED`, and `DECIDED` consistently.
4. Do not bypass controls, deceive sources, collect non-public data, reproduce copyrighted interface expression, or present a competitor’s implementation as independent discovery.
5. Compare competitors as solutions to customer problems. Feature matching is an input, not a strategic conclusion.
6. Frame recommendations as hypotheses where evidence is incomplete. Research does not replace user validation, legal advice, or security testing.

## Workflow

### 1. Context and Research Constitution

Create `constitution.md` with the target decision, stakeholder, desired differentiation, constraints, terminology, risk tolerance, and definition of success.

Write `research_scope.md` stating the entities, market/geography, time period, public sources permitted, user-provided materials, and excluded activity. Confirm whether the output is a market memo, a platform evolution plan, a skill upgrade, a delta audit, or a full implementation brief.

If the work is an app-to-platform transformation, invoke `clone-to-platform-pipeline` for the evidence-led discovery and implementation workflow; use this skill for market benchmarking and critical review.

### 2. Evidence-Led Competitive Discovery

Identify a deliberately small comparison set, normally three to four relevant alternatives. Include open-source, commercial, adjacent, or substitute solutions when they illuminate the decision.

For each entity, record evidence rather than impressions in `discovery_inventory.md` and `evidence_ledger.md`:

| Dimension | Capture |
|---|---|
| Customer and outcome | Target user, job/problem, value proposition, evidence strength |
| Product and workflow | Publicly observable capabilities, user journey, roles, constraints, error behavior |
| Business model | Packaging, pricing signals, distribution, partnerships, trust signals |
| Technology and operations | Publicly documented integrations, deployment model, security or compliance claims; never infer private internals as fact |
| Strengths and gaps | Evidence-linked advantage, limitation, unserved segment, or opportunity |
| Provenance | URL/artifact, access date, evidence status, confidence, restriction |

Synthesize findings into `opportunity_map.md`. Link desired business outcomes to customer opportunities, solution hypotheses, and important low-evidence assumptions. Prioritize the latter for validation.

### 3. Strategy and Platform Specification

Write `business_plan.md` only when the user needs it. Ground market claims in citations, preserve fiscal-period discipline for financial facts, and route material valuation or investment analysis through `finance-pro-playbooks`.

Write or revise `platform_specification.md` as an independent product blueprint. Require:

- A target user, intended outcome, differentiation thesis, and measurable success signals.
- Functional requirements traced to evidence IDs, opportunity IDs, or explicit product decisions.
- Role/permission matrix, data model, interface boundaries, integration assumptions, and original UX/content direction.
- Proportionate non-functional acceptance criteria for accessibility, authorization, privacy, security, reliability, and performance.
- Assumption tests, decision owner, and an ADR for material architectural or policy choices.

Do not turn every competitor feature into a requirement. Explicitly decide whether to **adopt, adapt, reject, defer, or validate** each material learning.

### 4. Adversarial Review

Use `templates/adversarial_review.md` and extend it with evidence IDs, likelihood, impact, confidence, owner, mitigation, and acceptance evidence.

Review the current specification across these lenses:

| Lens | Test |
|---|---|
| Strategic fit | Does each priority requirement advance a distinct customer outcome? |
| Evidence | Is the claim sourced, appropriately labeled, and strong enough for the decision? |
| Independent design | Does the proposal avoid copying protected expression and undue dependence on one competitor? |
| Security and privacy | Are data flows, privileges, misuse cases, trust boundaries, and mitigations adequate for the risk? |
| Accessibility and usability | Are inclusion and critical-task acceptance criteria testable? |
| Delivery | Are dependencies, transitions, integration contracts, telemetry, and rollback paths feasible? |

For meaningful attack surfaces, create or require a data-flow model with trust boundaries and abuse cases. Score risks using a documented likelihood-and-impact method. Do not manufacture critical or high findings to meet a quota; report the actual evidence and uncertainty.

### 5. Delta Specifications

Use `templates/delta_specs.md` to create modular changes rather than a wholesale rewrite. Every delta must include:

1. An identifier and `[NEW]`, `[MODIFIED]`, `[REMOVED]`, or `[INVALIDATED]` status.
2. The linked evidence, review finding, or product decision.
3. Rationale, affected users/components/data, acceptance criteria, dependencies, risks, and rollback/measurement plan where relevant.
4. A clear decision: adopt, adapt, reject, defer, or validate.

Store dated delta files or maintain a dated changelog. Do not overwrite the baseline specification without preserving the change record.

### 6. Master Handoff and Next Session

Use `templates/master_handoff.md` to produce `MASTER_HANDOFF_<project_name>.md`. Include the research question, evidence status, comparison set, strategic decisions, ADRs, risk decisions, deliverable index, open questions, and a Mermaid dependency graph that traces evidence through opportunity, specification, review, delta, and implementation.

State exactly what must be read before implementation, what remains uncertain, and the next validation or build action. Provide a short next-session prompt only after the handoff is complete.

## Skill-Upgrade Variant

When benchmarking an existing skill, keep the same workflow but compare **trigger quality, workflow completeness, context cost, resource design, safety guardrails, validation, and outcomes**. Write a revision proposal before editing. Retain useful local conventions; do not replace them merely because another framework uses different naming or metadata.

## Completion Criteria

Complete the requested research only when every material recommendation is source-linked or labeled as an assumption, proposed changes are independently designed, material risks are prioritized without fabrication, and the next decision is unambiguous.
