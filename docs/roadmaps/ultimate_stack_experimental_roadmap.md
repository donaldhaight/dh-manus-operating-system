# Ultimate Stack Experimental Roadmap

**Branch:** `experiment/ultimate-stack`  
**Baseline preserved:** `v0.1.0-session-baseline` on `main`  
**Objective:** Prove one safe, source-grounded RRCA operating loop while building reusable identity, evidence, workflow, agent, automation, and control-plane foundations.

## Operating Rule

This roadmap builds the **smallest coherent operating system** before it builds the largest possible infrastructure. Every increment must be reversible, source-controlled, observable, and independently testable. No increment may authorize an agent or automation to perform a binding, regulated, financial, external-communication, production-access, or destructive action.

## G0 — Hosting and Control-Plane Decision

Select one of the following implementation paths before provisioning anything beyond the existing private repository and experiment branch.

| Option | What is built first | Benefits | Constraints and cost posture | Decision needed |
|---|---|---|---|---|
| **Managed pilot** | A managed internal application with sign-in, database, storage, and a simple scheduled/background job capability. | Lowest operations burden; fastest validation of the Mission Control experience. | May not satisfy the commissioning brief’s PostgreSQL preference without an additional data-plane decision; custom runtime and Docker needs remain constrained. | Is fast product validation more important than immediate database/runtime sovereignty? |
| **Hybrid control plane** | A TypeScript application with PostgreSQL/object storage as the durable data plane and a separate persistent worker environment only for agent/orchestration needs that cannot run in the managed layer. | Best alignment with the data/evidence model while preventing agent experimentation from becoming the transactional source of truth. | Requires explicit service contracts and some integration engineering. A cloud computer should be sized only after a measured workload; current plans start at $10/month. | Is the team ready to maintain a small persistent worker environment in exchange for PostgreSQL, Docker/runtime flexibility, and a cleaner long-term boundary? |
| **Sovereign testbed** | One persistent server runs all components in Docker. | Maximum control and fastest experimentation with self-hosted frameworks. | Highest security, patching, backup, and recovery responsibility; risk of premature complexity. Cloud-computer plans begin at $10/month, with larger tiers at $30 and $50 per month. | Is full infrastructure control required before the first RRCA loop is proven? |

**Gate condition:** The founder chooses one option, names the data owner and operations owner, and accepts the initial cost/maintenance envelope. The recommended **design target** in the architecture is the hybrid control plane, but no infrastructure purchase or deployment proceeds until this gate is approved.

**Rollback:** No external resources are provisioned before the decision. The baseline tag remains untouched.

## G1 — Repository, Contracts, and Local Clean-Clone Foundation

Create a TypeScript monorepo in a dedicated project repository or, if approved, within a clearly separated application directory. Do not place application runtime code in the knowledge-bundle repository. Keep the knowledge bundle and the operating-system repository as source/protocol layers, with the application repository importing approved contracts or consuming the knowledge bundle through a controlled retrieval service.

| Deliverable | Acceptance test | Rollback/control |
|---|---|---|
| Repository and branch model | A clean clone can install dependencies, run tests, and load a minimal local configuration without secrets. | Delete experimental application repository; retained docs and tags remain unchanged. |
| Core domain glossary | Every first-slice object has a stable name, ID convention, owner, state, and evidence/authorization fields. | Changes require an ADR or linked delta specification. |
| Event schema package | Sample Lead, Task, evidence, decision, and agent-work events validate against versioned schemas. | Version messages; do not mutate prior event meanings. |
| ADR and decision templates | A material architecture choice can be created, reviewed, superseded, and found by ID. | Documentation-only change; source control history remains. |
| CI baseline | Lint/type/test/document-link checks run on pull requests. | CI may be disabled/changed through a reviewed commit; no production deployment is connected. |

**Gate condition:** A second clean environment completes a clone/test rehearsal and the founder can review the first system map without relying on private chat context.

## G2 — Identity, Context, and Synthetic Data Boundary

Implement only the identity and authorization needed for an internal pilot. The immediate proof is a user acting through an explicit organization, entity, stakeholder group, and role context—not a finished public onboarding system.

| Deliverable | Acceptance test | Prohibited action |
|---|---|---|
| Sign-in | An internal authorized user can sign in via the selected identity provider. | Public invitations or external onboarding without a reviewed process. |
| Active-context switch | The user must select active organization/entity/group/role context; the selection is visible in each protected view. | Inferred context based on UI location or a user’s default role. |
| Server-side permission checks | A test suite proves permitted and denied access across at least three synthetic roles. | Client-only authorization checks. |
| Database isolation | RLS/policy tests show one entity cannot retrieve another entity’s protected synthetic records. | Application use of table owner or `BYPASSRLS` roles for routine requests. |
| Audit event | A protected action records actor, active context, authorization version, target, correlation ID, and result. | Recording secrets, tokens, or unnecessary personal data in logs. |

**Gate condition:** A Quality/Security review packet confirms that both positive and negative authorization tests pass.

**Rollback:** Disable the experimental tenant/application; delete synthetic records under the documented test-data policy. No real customer or claim data is involved.

## G3 — Evidence Registry and Knowledge Retrieval Vertical Slice

Build a source-first ingest/retrieve path for a deliberately small set of authorized Human Blockchain materials and synthetic test documents.

| Deliverable | Acceptance test | Guardrail |
|---|---|---|
| Source registry | Each source item has source path/ID, hash, sensitivity, status, origin, access rule, and derived-artifact links. | Raw sources are preserved; derived summaries are never overwritten onto originals. |
| Object storage integration | Evidence files can be uploaded/retrieved through an authorized reference; the database stores metadata rather than file bytes. | No unrestricted agent access to all files. |
| Retrieval context pack | A question retrieves the smallest relevant set of source fragments/records and returns paths, status, and citations. | The system labels unsupported inference and conflicting sources. |
| Evaluation set | At least ten retrieval questions have expected supporting sources and failure criteria. | Retrieval quality is measured rather than assumed. |
| Human correction loop | A founder correction becomes a linked working-model update without deleting historical source. | No automatic rewrite of constitutional or historical material. |

**Gate condition:** A clean-session reviewer can answer an RRCA workflow question from the retrieval pack, cite the supporting sources, and identify at least one unresolved assumption.

## G4 — Mission Control, Work Graph, and Human Decision Gates

Build the internal Mission Control screen before deploying an agent army. It should show mission status, objective, source context, assumptions, risks, work items, owners, cost/time data, artifacts, gates, decisions, and the exact next action.

| Deliverable | Acceptance test | Guardrail |
|---|---|---|
| Mission record | A mission has one named owner, decision owner, scope/non-goals, success measure, and review date. | No mission is marked active without an accountable human owner. |
| Work graph | Dependencies and role assignments are visible; each work item has a work packet. | A work item cannot change consequential domain state directly. |
| Decision packet | It includes decision, options, evidence, assumptions, consequences, recommendation, approval scope, and next reversible action. | Avoid vague approval prompts. |
| Gate UI | Founder can approve, reject, request revision, or defer; the decision is immutable/audited and resumes or closes the work. | No silent approval by an agent or timeout default for high-impact actions. |
| Risk register integration | Material risks, thresholds, mitigation, owner, and review date are linked to work/decision records. | No release with unresolved risk beyond the accepted threshold. |

**Gate condition:** One internal mission completes from admission to a documented G1 or G2 decision without a side channel or manual spreadsheet becoming the system of record.

## G5 — First Multi-Agent Team-of-Teams Experiment

Start with two complementary teams, not every possible role. The first team creates a source-grounded output; the second team independently reviews it against a contract. Mission Control remains the coordinator.

| Team | Initial test | Evaluation |
|---|---|---|
| **Knowledge and Evidence Team** | Retrieve a context pack and produce an evidence/assumption brief for an RRCA synthetic Lead-to-Task scenario. | Citation correctness, source-status labeling, scope fidelity, and escalation of conflict/uncertainty. |
| **Product and Engineering Team** | Convert the approved scenario into a small PRD/SRS delta, acceptance tests, and implementation plan. | Traceability from need to test, non-goals, permission/evidence requirements, and implementation feasibility. |
| **Quality/Risk Review Team** | Independently check the artifacts for authorization, data-boundary, state-transition, and evidence gaps. | True positive/false positive rates, actionable remediation, and correct escalation. |

**Agent contract:** Every invocation receives a mission/work ID, context-pack version, permitted tools/data, output schema, evaluation rule, token/time budget, and human escalation trigger. Every output carries source IDs, claim labels, and a correlation ID.

**Gate condition:** The two-team experiment produces a useful reviewed artifact, and the review identifies either a meaningful issue or explicit evidence that the artifact meets its stated criteria. A single agent may not review and approve its own consequential output.

**Rollback:** Disable the agent runner and preserve input/output traces for evaluation. No agent writes to the protected domain tables; promotion occurs through a human-reviewed command.

## G6 — Deterministic Automation and Durable Workflow

Only after Mission Control and the agent contracts work should the system add automation. Begin with deterministic, reversible, low-risk functions.

| Automation | First behavior | Idempotency/recovery requirement | Human gate |
|---|---|---|---|
| Task generation | A synthetic Lead/Claim Request event creates a draft Task Request. | Same event ID cannot create duplicates; retry is safe. | Human reviews/activates high-impact assignments. |
| SLA monitor | Identifies approaching/overdue synthetic deadlines and creates an alert. | Alert deduplication and recorded evaluation time. | Human defines the escalation policy. |
| Missing-evidence reminder | Detects a workflow state missing required synthetic evidence and drafts a request. | Required-evidence rule is versioned; no external send by default. | Human authorizes actual outbound communications. |
| CI/documentation | Runs validation, tests, artifact-link checks, and draft release-note generation after code changes. | Failed jobs retain logs; retry does not mutate production. | Protected branch/release review. |
| Workflow approval | Pauses a long-running work item and resumes after an explicit decision or a defined low-risk timeout. | Durable state, timeout path, correlation ID, and audit history. | Named decision owner. |

All inbound webhooks must validate origin/signature/freshness where the provider supports it. All external side effects must carry idempotency keys. Permanently failed events enter a manual-review queue; they are not silently dropped or endlessly retried.

**Gate condition:** The full synthetic workflow runs through creation, review, decision, timeout handling, exception queue, and safe replay with a complete trace.

## G7 — Observability, Backup, Recovery, and Controlled Delivery

Operational controls must be added before any external beta. The first goal is to diagnose a failed workflow or agent handoff without inferring what happened from chat text.

| Control | Acceptance test | Rollback/recovery evidence |
|---|---|---|
| Traces/logs/metrics | A reviewer follows a correlation ID from retrieval through agent output, approval, event, and workflow result. | Telemetry filtering shows no credentials or prohibited data. |
| Backup | A scheduled backup completes and integrity evidence is recorded. | A restore to a non-production environment succeeds. |
| Recovery runbook | A new operator can restart workers, disable automation, rotate a test secret, and recover from a failed job. | Timed rehearsal, log, and corrective delta. |
| Deployment pipeline | A pull request runs checks; an approved change creates a preview/staging deployment. | Prior release can be restored; migrations have an explicit rollback or forward-fix plan. |
| Environment gate | The actual account/repository capability for reviewers, secrets, and deployment restrictions is verified. | If unavailable, a documented manual approval process replaces it until an appropriate control is available. |

**Gate condition:** A tabletop incident exercise and a technical restore exercise both pass. Only then may a limited invited test environment be proposed.

## G8 — RRCA Synthetic-to-Authorized Pilot Readiness

Do not call this production solely because software is online. The system must prove its narrow operational use with synthetic or explicitly authorized data before broader real-world use.

| Readiness condition | Evidence required |
|---|---|
| One RRCA loop is coherent | Synthetic/authorized Lead → Offer → request → Project/Job/Task → evidence → authorized test provider event is traceable. |
| Roles and data boundaries work | Authorization test report, audit trace, and failure-path evidence. |
| Agents are bounded and useful | Evaluation report, escalation statistics, and human reviewer feedback. |
| Automation is reversible | Kill switch, manual-review queue, replay process, and operating runbook. |
| External claims are accurate | Reviewed case-study language; no claim of regulatory approval, endorsement, financial-provider function, or completed market transformation. |
| Decision rights are operational | Named owners, decision log, approvals, and exceptions demonstrate founder/council control. |

## Change and Rollback Policy

| Change class | Allowed experimental action | Mandatory check before promotion | Rollback method |
|---|---|---|---|
| Documentation/protocol | Create versioned draft on experiment branch. | Link/readability check, owner review. | Revert commit; preserve history. |
| Agent prompt/skill | Run against evaluation fixtures only. | Measured improvement and safety/exclusion evaluation. | Restore prior version; disable invocation. |
| Schema | Apply only in a disposable/test environment first. | Migration review, isolation test, backup. | Explicit down migration or tested forward-fix. |
| Workflow/automation | Enable in dry-run/shadow mode first. | Idempotency, exception queue, monitoring, owner acceptance. | Disable worker/feature flag; preserve events for diagnosis. |
| External integration | Use sandbox/test account and signed-webhook validation. | Data map, credential plan, error/timeout behavior, human action policy. | Revoke credentials, disable endpoint, reconcile test events. |
| Production release | Stage, observe, and use a named release owner. | Security/quality evidence, risk acceptance, support/rollback readiness. | Roll back release or forward-fix under incident control. |

## Immediate Next Decision

Before any software provisioning, choose the **G0 hosting/control-plane path**. The decisive question is whether the next objective is:

1. **Validate Mission Control UX quickly** with a managed internal pilot;
2. **Prove the full data/agent control-plane pattern** with the hybrid approach; or
3. **Experiment deeply with self-hosted infrastructure** in a sovereign testbed.

All three preserve the current baseline. The hybrid approach is the closest architectural match to the Human Blockchain commissioning brief, but the founder should choose it only if the team accepts the added integration and operations responsibility.
