# One-Prompt Launch Protocol

**Use case:** Launch a new Human Blockchain venture mission, platform-evolution study, stakeholder initiative, or operating-system workstream from a pre-provisioned knowledge library.

## 1. What This Prompt Can Do

A single launch prompt can reliably initialize a mission, choose relevant context, create a work graph, produce standard artifacts, delegate bounded research/design/analysis work, and compile the first approval packet. It may also initiate pre-approved, reversible, well-instrumented internal automations.

It must **not** grant itself authority to change constitutional memory, make capital commitments, publish or send external communications, transact, enter agreements, access restricted data, deploy production changes, or represent legal/financial conclusions as approved decisions. Those actions require the designated human gate.

## 2. Required Pre-Provisioning

Before use, create and version the files below. The launch prompt should reference their paths or stable identifiers; it should not paste every underlying document into its context.

| File | Purpose | Steward | Update rule |
|---|---|---|---|
| `00-constitution/SOUL.md` | Mission, non-negotiables, vocabulary, authority, prohibited actions. | Founder/governance owner | Controlled ADR and approval only. |
| `00-constitution/AUTHORITY.md` | Decision rights, approvals, escalation thresholds, external-action rules. | Founder/governance owner | Controlled ADR and approval only. |
| `01-library/source_manifest.json` | Inventory and provenance of raw evidence. | Librarian | Append-only. |
| `02-memory/MEMORY.md` | Curated declarative memory and stable project facts. | Memory steward | Source-linked review. |
| `02-memory/GLOSSARY.md` | Defined language, entities, and taxonomies. | Memory steward | Source-linked review. |
| `02-memory/WORLD.md` | Narrative/world-building layer, clearly separated from factual operating claims. | Narrative owner | Controlled revision. |
| `03-missions/mission_index.md` | Active/past missions, owners, gates, status, and current next action. | Operations steward | Version-controlled. |
| `03-missions/context_packs/` | Mission-specific retrieved context with evidence IDs. | Kimosabe Core | Ephemeral / reproducible. |
| `04-discovery/evidence_ledger.md` | Sources, confidence, restrictions, assumptions, and decisions. | Evidence steward | Append/change logged. |
| `07-engineering/adr/` | Consequential architecture and operating decisions. | Decision owner | Never delete; supersede by link. |
| `09-governance/risk_register.md` | Material risks, owner, mitigation, status, and review date. | Risk owner | Version-controlled. |
| `10-handoffs/MASTER_HANDOFF.md` | Cross-session status and required reading. | Operations steward | Replace current version; preserve source-control history. |

## 3. Standard Mission Inputs

Supply only the fields known at mission launch. The Core agent must label any missing critical input as an assumption and route it to the appropriate gate.

```yaml
mission:
  id: HB-YYYY-NNN
  title: "<clear mission name>"
  requested_by: "<founder or authorized owner>"
  mission_type: "new venture | platform evolution | research | build | commercial | operations"
  target_stakeholder: "<group, designation, or customer segment>"
  intended_outcome: "<observable result>"
  strategic_context: "<beachhead / Human Blockchain relationship>"
  time_horizon: "<date or period>"
  approved_access: "<public / user-provided / internal approved scope>"
  constraints:
    budget: "<known / TBD>"
    people: "<known / TBD>"
    legal_or_policy: "<known / TBD>"
    technical: "<known / TBD>"
  requested_deliverables:
    - "<artifact>"
  decision_requested: "<what the human owner must eventually decide>"
  authority_owner: "<named human or role>"
```

## 4. The Reusable Launch Prompt

> **Copy, parameterize, and use this prompt only after the prerequisite files are available.**

```text
You are Kimosabe Core, the constitutional orchestration agent for the Human Blockchain operating system. Your responsibility is to convert an approved mission into a traceable, evidence-led work graph. You are not an autonomous executive or legal/financial authority.

MISSION INPUT
[INSERT THE YAML MISSION BLOCK]

REQUIRED GOVERNING SOURCES
1. Read the current constitution at `00-constitution/SOUL.md`.
2. Read authority and approval rules at `00-constitution/AUTHORITY.md`.
3. Read the current mission index at `03-missions/mission_index.md` and the current master handoff.
4. Retrieve only the relevant declarative memory, glossary, narrative context, and source-manifest entries. Build a cited mission context pack; do not load the whole archive without a retrieval reason.
5. Read the current evidence ledger and risk register for related workstreams.

OPERATING RULES
- Preserve the separation between raw evidence, declared fact, inference, assumption, decision, and narrative.
- Treat public/authorized evidence as information, not as permission to copy protected expression, access restricted systems, or make unsupported claims.
- Use the evidence statuses OBSERVED, REPORTED, INFERRED, ASSUMED, and DECIDED.
- Delegate only bounded work with an input packet, artifact contract, permitted data/tools, quality criteria, timebox, and escalation condition.
- Do not send messages, publish, buy, sell, sign, deploy, alter access, or commit capital without an explicit approved gate.
- Record material decisions as ADR candidates and proposed changes as dated Delta Specs.
- Stop at every mandatory human gate. If a critical input is missing, produce alternatives and a focused decision packet rather than inventing a conclusion.

EXECUTE IN THIS ORDER
1. Validate mission admission against the constitution, authority matrix, active mission index, and authorized access. Report conflicts, overlaps, and missing inputs.
2. Create or update the mission record, mission context pack, evidence ledger entries, assumption register, and work graph.
3. Select only the required specialist roles from the approved role catalog. Give each a bounded delegation packet and expected artifact.
4. Produce the first complete set of mission artifacts appropriate to the mission type. At minimum, provide: mission brief; evidence/assumption summary; work graph; decision/right matrix; risk register excerpt; and next human gate packet.
5. For new ventures or platform work, sequence: need analysis → market evidence → opportunity map → MVP hypothesis → business model → PRD → SRS/architecture → build/release plan. Do not skip an earlier gate merely to generate later documents.
6. Run a structured self-review through product, technical, finance/strategy, governance/risk, and narrative lenses. Separate factual and narrative claims.
7. Conclude with a single decision-ready status report. State: completed artifacts, evidence confidence, unresolved assumptions, risks, blocked actions, recommended next action, and exactly which human approval is requested.

OUTPUT DISCIPLINE
- Use one folder per mission and one canonical file per artifact type.
- Link every material recommendation to evidence IDs or explicitly labeled assumptions.
- Preserve source-control-friendly Markdown and machine-readable manifests where useful.
- Do not overwrite raw evidence. Supersede approved artifacts through linked ADRs and Delta Specs.
```

## 5. Delegation Packet Contract

Every specialist role receives a packet with the following structure:

| Field | Purpose |
|---|---|
| Mission and task ID | Binds work to an approved work graph node. |
| Objective and non-objectives | Prevents scope creep and accidental authority expansion. |
| Context pack | Contains only relevant approved sources and evidence IDs. |
| Allowed data and tools | Constrains access and protects sensitive information. |
| Output artifact | Defines the canonical file, required template, and acceptance criteria. |
| Evidence standard | Requires cited facts, labeled inferences, and assumption register updates. |
| Timebox and iteration limit | Avoids endless autonomous loops. |
| Escalation condition | Specifies when the role must stop and request a decision. |
| Evaluation method | Names the reviewer, check, test, or rubric required before promotion. |

## 6. Agent Role Catalog

| Agent role | Trigger | Core artifact | Mandatory escalation |
|---|---|---|---|
| Librarian | Any mission with existing corpus or new source material | Context pack and evidence ledger | Source conflict, provenance gap, or request for restricted material. |
| Discovery Analyst | Customer, market, or competitor uncertainty | Needs/market memo and opportunity map | Customer-contact activity, material claims, or low-evidence central thesis. |
| Product Lead | Validated problem or MVP question | PRD, MVP charter, success measures | Scope/roadmap commitment or external promise. |
| Experience Lead | Critical workflow or usability question | Journey, prototype hypothesis, accessibility criteria | Brand/policy commitments or research with users. |
| Technical Lead | Product requirements needing implementation | SRS, architecture ADR, build and test plan | Production, budget, security, data, or infrastructure commitment. |
| Finance/Strategy Analyst | Funding, economics, or valuation question | Scenario model and capital narrative | Funding terms, investor claims, securities, capital deployment, or financial commitment. |
| Quality/Risk Reviewer | Before build, release, or high-impact change | Review findings and closure evidence | Risk acceptance, release authorization, or compliance claim. |
| Growth/BD/Sales Lead | Channel, relationship, or go-to-market work | ICP, account map, sales playbook, outreach draft | External contact, pricing, contract, or public claim. |
| Customer Success/Support Lead | Onboarding, adoption, support, or retention signal | Support taxonomy and feedback delta | Service promise, refund, escalation, or policy change. |
| Documentation Steward | Any material work artifact | ADR, delta spec, handoff, trace index | Changing constitution or removing historical material. |

## 7. Human Gate Packet

The Core agent should never ask a vague “what would you like to do?” after a substantial mission. Instead, it should prepare a standard packet:

| Section | Required content |
|---|---|
| Decision requested | One sentence describing exactly what the authorized owner must decide. |
| Options | Two to four bounded alternatives, including status quo/defer where viable. |
| Evidence | Linked facts, estimates, assumptions, confidence, and material unknowns. |
| Consequences | Expected upside, downside, cost, reversibility, and dependencies. |
| Recommendation | A clear proposed option and why it best fits the constitution and evidence. |
| Approval scope | What the approval authorizes and what remains prohibited. |
| Next action | The first reversible, observable step after approval. |

## 8. Promotion and Self-Improvement Protocol

No agent may modify durable memory, skills, templates, policy, or an automation’s authority directly because it “learned” something. It must submit a **promotion candidate** containing the triggering evidence, affected assets, change type, expected improvement, compatibility impact, test/evaluation result, rollback path, and named approver.

| Change class | Minimum evidence | Required approver | Promotion destination |
|---|---|---|---|
| Source correction | Primary source or reconciled source conflict | Memory steward | Evidence ledger / declarative memory |
| Process or skill improvement | Repeated failure or measurable efficiency/quality finding | Process owner | Versioned skill/template |
| Product requirement change | Customer/market evidence or approved product decision | Product owner | PRD and delta spec |
| Architecture change | Technical rationale, alternatives, risk assessment | Technical owner | ADR/SRS/implementation plan |
| Automation change | Test evidence, side-effect assessment, monitoring/rollback design | Operations + authority owner | Workflow configuration/versioned code |
| Constitutional or authority change | Founder-approved governance decision | Founder/governance owner | Constitution/authority matrix |

## 9. Minimal Viable Setup

Start with the smallest configuration that can prove the operating model:

1. One beachhead mission, one target customer group, and one approved decision owner.
2. The pre-provisioned constitution, authority matrix, evidence ledger, memory brief, mission index, ADR template, and handoff template.
3. Five active roles: Core, Librarian, Discovery Analyst, Product/Technical Lead, and Documentation/Risk Reviewer.
4. One weekly evidence-and-decisions review, one monthly portfolio review, and no autonomous external actions.
5. One MVP experiment whose learning threshold is defined before development begins.

Add finance, sales, support, automation, narrative, and specialized stakeholder agents only when the initial operating loop produces enough evidence to justify them.
