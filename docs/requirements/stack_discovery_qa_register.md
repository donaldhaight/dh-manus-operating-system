---
id: stack-discovery-qa-register-001
title: DH Manus Operating System — Stack, Agent, and Automation Requirements Q&A Register
mission_id: DHMOS-ULTIMATE-STACK-001
artifact_type: requirements_register
status: active
owner: Donald Haight
created: 2026-08-26
updated: 2026-08-26
review_by: 2026-09-02
evidence_ids:
  - DHMOS-SESSION-001
  - HBO-master-continuity-brief-001
related_decisions:
  - G0-hosting-and-control-plane
confidentiality: internal
---

# DH Manus Operating System — Stack, Agent, and Automation Requirements Q&A Register

## Purpose and Use

This is the living discovery register for the **DH Manus Operating System**. It records the questions that materially affect architecture, the best current answer, source/context, decision impact, owner, and next validation action. It is deliberately designed to turn an exploratory conversation into reusable requirements rather than letting important answers disappear into chat history.

Each answer is classified as **Confirmed**, **Working assumption**, **Open decision**, **Needs evidence**, or **Out of scope for the first pilot**. A confirmed answer may still be revised by a newer founder instruction or an approved decision record. The Human Blockchain knowledge bundle is retrieved as source-grounded context; its historical working drafts and creative materials are not treated as immutable authority.

## Current Answer — Question 1

| Field | Record |
|---|---|
| ID | `INFRA-001` |
| Question | **Did we create a connection to a cloud computer and, if not, why not?** |
| Answer | **No. No cloud computer has been provisioned or attached to this session.** We created and pushed the private operating-system repository, preserved its baseline tag, created the `experiment/ultimate-stack` branch, cloned the Human Blockchain knowledge repository locally in the current session sandbox, and wrote the ultimate-stack architecture and roadmap. None of those actions creates a persistent cloud computer. |
| Status | **Confirmed** |
| Why not | We intentionally deferred provisioning because the stack had not yet passed the G0 hosting/control-plane decision. The current work was design, documentation, research, and version control—activities that did not require an always-on server, fixed IP, Docker, or resources beyond a managed application environment. Provisioning first would have introduced a paid, persistent operations burden before a defined workload, data classification, recovery owner, automation trigger, and pilot acceptance test existed. |
| What this means | There is no persistent runtime, no persistent database, no background worker, no connected deployment environment, no stored production secret, no enabled external integration, and no autonomous process currently running. The current sandbox clone is temporary session working context, not a deployed retrieval service. |
| Source/context | `docs/architecture/ultimate_stack_experimental_architecture.md`, `docs/roadmaps/ultimate_stack_experimental_roadmap.md`, session repository state, and the Human Blockchain commissioning brief’s modular-monolith / first-RRCA-loop direction. |
| Decision impact | The next infrastructure decision is G0: choose a managed pilot, a hybrid control plane, or a sovereign testbed. A cloud computer becomes appropriate only if the selected first slice has a hard need for Docker, a custom runtime, fixed IP, OS-level control, or greater compute/memory than the managed environment can provide. |
| Next validation | Define the first experiment’s 24/7 workload, trigger frequency, permitted integrations, data sensitivity, expected concurrency, required uptime, recovery objective, and operating owner. |

> **Plain-English answer:** We have the blueprint and a safe experiment branch, but not an actual always-on server. That was intentional: we are avoiding paying for and operating infrastructure until we know precisely what must run continuously and what safeguards it requires.

## How We Will Work Through These Questions

| Priority | Meaning | Treatment |
|---|---|---|
| **P0 — Architecture-changing** | The answer changes hosting, data, authorization, external-action, or regulatory boundaries. | Resolve before provisioning or building the affected component. |
| **P1 — Pilot-defining** | The answer changes the first RRCA/Mission Control slice, agent roles, or acceptance tests. | Resolve before the associated pilot increment. |
| **P2 — Optimization** | The answer improves scale, cost, UX, or automation after core boundaries are stable. | Capture now; defer implementation until evidence requires it. |

## A. Mission, Pilot, and Value Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `MISSION-001` | P0 | What exact result should the first pilot demonstrate for RRCA or the founder? | Candidate: an internal, synthetic Lead-to-Task-to-evidence-to-founder-decision loop; confirm the narrow outcome. | Defines the first data model, screens, agent work, and test cases. | Open decision |
| `MISSION-002` | P0 | Who is the named decision owner for the first pilot, and who can act as backup? | Donald is the final authority; identify the specific operational owner and escalation backup. | Determines decision gates, notifications, and approval workflows. | Needs confirmation |
| `MISSION-003` | P1 | What is the first measurable success threshold? | Examples: a traceable synthetic workflow, time saved per case, fewer missing-evidence items, or a review-ready case-study record. | Defines metrics, dashboards, and exit criteria. | Open decision |
| `MISSION-004` | P1 | Which parts of the Human Blockchain thesis must the first slice explicitly prove, and which must remain context only? | Begin with one RRCA loop; avoid trying to prove the entire 1-17-3350 model at once. | Controls scope, knowledge retrieval, and roadmap order. | Working assumption |
| `MISSION-005` | P2 | What creative/cultural layer should accompany the operator product, if any? | Keep cultural storytelling separate from transactional evidence and authority claims. | Affects content management and public experience, not initial control plane. | Deferred |

## B. Hosting, Runtime, and Cloud-Computer Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `INFRA-002` | P0 | What must run 24/7, and what response time is actually required? | List inbound webhooks, monitoring, scheduled jobs, queues, background agents, and user-facing services. Distinguish seconds, minutes, hours, and daily cadence. | Determines managed request service versus persistent worker versus cloud computer. | Open decision |
| `INFRA-003` | P0 | Does any first-pilot component require Docker, a custom system package/runtime, a fixed IP, or more resources than a managed application offers? | Do not answer “maybe”; name the exact required component and constraint. | Establishes whether a cloud computer is justified. | Open decision |
| `INFRA-004` | P0 | Who will own patching, access reviews, monitoring, backups, and incident response if a persistent server is provisioned? | Name a human operating owner; agents may draft/run approved procedures but do not replace accountable ownership. | Determines whether self-hosted infrastructure is responsible at this stage. | Open decision |
| `INFRA-005` | P1 | What data-loss and recovery expectation applies to each data class? | Define recovery point and recovery time expectations separately for documents, synthetic pilot data, operational data, and logs. | Sets database/storage backup and restore design. | Needs evidence |
| `INFRA-006` | P1 | Do we need a separate development, test, invited-pilot, and production environment now? | At minimum, isolate development/test from any authorized case-study/production data. | Defines deployment environments and secret boundaries. | Working assumption |
| `INFRA-007` | P2 | Do we need a fixed public IP or custom domain before the pilot? | Only if a named integration, webhook allowlist, domain, or public service requires it. | Drives cloud/network/DNS decision. | Deferred |

## C. Identity, Entity Context, and Authorization Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `AUTH-001` | P0 | Which users/roles must access the first pilot? | Start with founder, Company Admin, internal operator, read-only reviewer, and bounded agent service identity; confirm exact roles. | Defines auth schema, UI, permissions, and audit tests. | Working assumption |
| `AUTH-002` | P0 | Must every action be scoped to Stakeholder Group, Legal Entity, Human Role, and jurisdiction—or can any first-slice action be global? | Use explicit organization/entity/group/role context for protected actions unless a documented exception exists. | Drives authorization context and data model. | Working assumption |
| `AUTH-003` | P0 | What decisions can the system prepare, and what decisions may only a named human execute? | Existing rule: agents may prepare, analyze, draft, test, and recommend; humans retain binding, regulated, production, money, external, and ownership actions. | Defines human-in-the-loop gate matrix. | Confirmed principle; needs action-level matrix |
| `AUTH-004` | P1 | What level of identity verification and MFA is required for each role? | Internal pilot can begin with controlled accounts; higher-risk roles require stronger verification based on actual action risk. | Affects sign-in provider, onboarding, and support workflow. | Open decision |
| `AUTH-005` | P1 | Which delegation relationships must be modeled: founder→admin, entity→employee, company→agent, reviewer→case, or other? | Enumerate real delegation paths before selecting relationship-based authorization machinery. | Determines whether simple RBAC is enough or a ReBAC policy layer is required. | Needs evidence |
| `AUTH-006` | P1 | Which audit events must be visible to whom, and for how long? | Record actor, active context, authorization basis/version, action, object, result, timestamp, and correlation ID without secrets. | Defines audit store, retention, and reviewer dashboard. | Working assumption |

## D. Data, Evidence, and Knowledge-Retrieval Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `DATA-001` | P0 | What data may enter the first pilot: synthetic only, founder-owned historical corpus, authorized RRCA data, or regulated/third-party data? | Start with synthetic and explicitly authorized material; do not ingest unrestricted regulated or private data by default. | Determines storage, consent, redaction, access, and agent boundaries. | Working assumption |
| `DATA-002` | P0 | Where is the canonical source of truth for each class: code, source document, registry, working model, decision log, database record, or published output? | Use an explicit source-of-truth matrix; do not allow duplicated mutable truth. | Defines data contracts and version-control boundaries. | Open decision |
| `DATA-003` | P0 | What provenance fields are mandatory for every source/evidence item? | Platform/account, original ID/path, date, hash, sensitivity, restrictions, version/relationship, parse status, source-versus-derived status, review state, and downstream use. | Defines source registry and object metadata. | Confirmed direction |
| `DATA-004` | P1 | Which Human Blockchain repository documents should be authoritative for which topics, and which are working drafts or historical creative supply? | Apply authority order: current founder instruction, approved decisions/executed agreements, observed working results, commissioning brief, then retrieved corpus. | Governs retrieval ranking and conflict handling. | Confirmed principle; needs a topic map |
| `DATA-005` | P1 | Do we need semantic/vector retrieval in the first slice, or can file/metadata/full-text retrieval meet the tests? | Do not vectorize by default. First define retrieval questions, expected sources, permissions, and failure cases. | Prevents premature RAG complexity. | Open decision |
| `DATA-006` | P1 | What correction process lets Donald revise working memory without deleting historical sources? | Preserve originals; create source-linked derived corrections and promote them through review. | Defines memory/versioning workflow. | Working assumption |
| `DATA-007` | P2 | Which media types must eventually be ingested and searched—documents, chats, source code, images, video, audio, datasets? | Inventory and prioritize by first-pilot value. | Determines parser pipeline and storage budget. | Deferred |

## E. Agent Teams and Orchestration Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `AGENT-001` | P0 | What is the smallest team-of-teams that creates useful independent review? | Start with Mission Control; Knowledge/Evidence; Product/Engineering; and Quality/Risk review. | Defines agent topology and evaluation plan. | Working assumption |
| `AGENT-002` | P0 | What exact artifact may each first-pilot agent create, and what may it never change? | Every agent requires a bounded work packet; agents do not promote their own output to consequential state. | Defines role contracts and database permissions. | Working assumption |
| `AGENT-003` | P0 | Which agent outputs require a second-agent review, a deterministic check, and/or human approval? | Evidence, requirements, risk, code, and release outputs should be independently checked according to impact. | Defines workflow steps and cost/time budgets. | Open decision |
| `AGENT-004` | P1 | What are the acceptable quality, latency, cost, and retry limits for each agent role? | Define role-specific thresholds; “best possible” is not an executable requirement. | Determines model routing, queueing, and budget controls. | Open decision |
| `AGENT-005` | P1 | Can an agent retrieve restricted sources, call external tools, write code, open a pull request, or trigger automation? | Default to least privilege; each capability needs a named policy and audit trail. | Defines service identities/tool permissions. | Open decision |
| `AGENT-006` | P1 | How will we evaluate source fidelity, correct escalation, output usefulness, recovery, and safety? | Use pre-defined fixtures plus observed pilot review results; do not score agents solely on prose volume. | Defines evaluation harness and promotion criteria. | Working assumption |
| `AGENT-007` | P2 | When is Hermes, a graph-oriented agent framework, a durable workflow system, or a simple job queue the right tool? | Decide by work type, state duration, approval latency, integration requirements, and measured complexity—not brand preference. | Sets the orchestration platform boundary. | Deferred pending G0/G5 evidence |

## F. Workflow, Automation, and Integration Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `AUTO-001` | P0 | Which first-pilot events create tasks, alerts, or review requests? | Candidate: synthetic Lead created, evidence missing, SLA approaching, agent output ready, approval requested, validation failed. | Defines event schema and initial automations. | Open decision |
| `AUTO-002` | P0 | Which actions must remain draft-only versus automatically executed? | Default outward-facing, financial, legal, access, publication, and production actions to draft/approval-only. | Defines approval policies and adapter design. | Confirmed principle; needs detailed matrix |
| `AUTO-003` | P0 | What is the idempotency key and retry policy for every state-changing/external operation? | Every event/action needs a stable ID and safe replay semantics. | Prevents duplicate tasks, notifications, or transactions. | Open decision |
| `AUTO-004` | P1 | Which inbound systems will send webhooks or require polling, and what does each provider actually support? | Name the provider before choosing a trigger method; verify webhook/API capabilities from current primary documentation. | Determines event gateway, credentials, cost, and uptime requirement. | Open decision |
| `AUTO-005` | P1 | Where should failed jobs go, who reviews them, and who may replay them? | Use a manual-review exception queue with source event, error, retry history, and role-limited replay control. | Defines DLQ UI/workflow and operational ownership. | Working assumption |
| `AUTO-006` | P1 | Which reports need AI judgment versus deterministic query/transform logic? | Use deterministic execution for rules; reserve AI for interpretation, drafting, extraction, synthesis, and uncertainty handling. | Determines cost, latency, and execution architecture. | Open decision |
| `AUTO-007` | P2 | What schedules genuinely need background execution, and at what cadence? | Avoid high-frequency full-agent runs; define observability and cost budgets before scheduling. | Determines cron/worker design. | Deferred |

## G. Security, Operations, and Recovery Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `OPS-001` | P0 | What is the data classification for every first-pilot input/output? | At minimum: public, internal, restricted, synthetic/demo, authorized case study, production/regulated. | Defines access, retention, logging, and agent restrictions. | Open decision |
| `OPS-002` | P0 | Which secrets exist, who owns them, and how are they rotated/revoked? | Keep secrets out of Git; do not use personal accounts as assumed transferable institutional assets. | Defines secret manager and credential lifecycle. | Open decision |
| `OPS-003` | P1 | What traces/logs/metrics must be available to diagnose a failed end-to-end workflow? | Correlate source retrieval, agent work, decision, event, job, automation, and release through a common ID. | Defines telemetry schema and dashboard. | Working assumption |
| `OPS-004` | P1 | How often will backups run, where will they be stored, and when is the first restoration rehearsal? | A recovery policy is incomplete until it has a tested restore. | Determines database/storage operations. | Open decision |
| `OPS-005` | P1 | Who receives operational alerts, at what severity, and who acknowledges them? | Name the first on-call/owner even if the system is small. | Determines notification/escalation design. | Open decision |
| `OPS-006` | P2 | What availability target is appropriate for the first pilot? | Define actual service hours and user impact before seeking 24/7 uptime. | Determines hosting redundancy/cost. | Deferred |

## H. Product Delivery, Commercial Operations, and Funding Questions

| ID | Priority | Question | Current answer / discovery prompt | Architecture impact | Status |
|---|---|---|---|---|---|
| `PROD-001` | P0 | What is the first complete user journey, beginning and ending with observable evidence? | Human Blockchain direction: a narrow RRCA Lead-to-Offer-to-Claim-Request-to-Project/Job/Task/evidence loop; define what is simulated versus live. | Establishes PRD/SRS, screens, event model, and test data. | Needs confirmation |
| `PROD-002` | P1 | What is deliberately excluded from this release? | Identify money movement, coverage determination, legal/adjusting functions, unsupported role permissions, and nonessential market features. | Protects MVP boundary and compliance posture. | Open decision |
| `COMM-001` | P1 | Which early users are internal operators, invited case-study reviewers, design partners, or customers? | Keep these categories distinct; do not characterize participation as endorsement or investment. | Defines onboarding, communication, and reporting paths. | Working assumption |
| `COMM-002` | P1 | Which sales/support signals should change the product backlog, and who decides? | Normalize feedback to evidence, assumptions, opportunity map, PRD/business-model deltas, and named review gates. | Defines CRM/support/product learning loop. | Open decision |
| `FIN-001` | P1 | What milestone requires capital, what evidence will prove value, and which funding paths are in scope? | Start with scenario planning; do not create or imply a securities offering through system design. | Defines finance-support models and review controls. | Open decision |
| `FIN-002` | P2 | Which metrics belong in the Quantum Dashboard now versus later? | Begin with operational evidence and scenario assumptions; distinguish estimates from historical facts, appraisals, negotiated values, and actual transactions. | Defines analytics model and claims review. | Deferred |

## First Answer Sequence

The following sequence minimizes rework. It will be used one question at a time, with each answer added to this register and linked to any resulting architecture delta.

| Next order | Question ID | Why it comes next |
|---:|---|---|
| 1 | `MISSION-001` | Determines the smallest valuable pilot and prevents infrastructure-first drift. |
| 2 | `INFRA-002` | Establishes whether anything actually needs 24/7 persistent execution. |
| 3 | `DATA-001` | Determines what data may safely be used in the pilot. |
| 4 | `AUTH-001` and `AUTH-003` | Defines who uses the pilot and which actions must remain human-controlled. |
| 5 | `PROD-001` | Converts the pilot outcome into a complete, testable user journey. |
| 6 | `AUTO-001` and `AUTO-002` | Identifies valuable automations and their approval boundaries. |
| 7 | `AGENT-001` through `AGENT-003` | Establishes the minimum agent topology and independent review requirements. |
| 8 | `INFRA-003` and `INFRA-004` | Makes the cloud-computer/control-plane decision from actual needs rather than speculation. |

## Change-Control Rule

When an answer changes hosting, authentication, data access, external integrations, workflow authority, financial/legal boundary, or release controls, create a linked **delta specification** and, where material, an **architecture decision record**. The Q&A register records why the requirement emerged; the delta/ADR records the approved change and its implementation consequences.

## Source Context

- `human-blockchain-operating-system/docs/00-start-here/master-continuity-brief.md` at retrieval anchor `be1725e`.
- `human-blockchain-operating-system/AGENTS.md` at retrieval anchor `be1725e`.
- `docs/architecture/ultimate_stack_experimental_architecture.md` on branch `experiment/ultimate-stack`.
- `docs/roadmaps/ultimate_stack_experimental_roadmap.md` on branch `experiment/ultimate-stack`.
- Current session instructions and explicit founder direction, which take precedence over older working material.
