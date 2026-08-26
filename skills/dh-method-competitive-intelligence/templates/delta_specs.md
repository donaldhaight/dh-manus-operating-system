# Delta Specifications: [Project Name]

| Field | Value |
|---|---|
| Date | [YYYY-MM-DD] |
| Baseline specification | [Path / version] |
| Trigger | [Evidence change, review finding, product decision, or validation result] |
| Target state | [Concise outcome] |

> A Delta Spec records a deliberate change to the independently designed platform. Do not use it to import a reference platform’s protected expression or unverified assumptions.

## Delta Index

| ID | Status | Title | Trigger | Decision | Owner | Implementation status |
|---|---|---|---|---|---|---|
| DS-001 | [NEW/MODIFIED/REMOVED/INVALIDATED] | [Title] | [Evidence / finding / decision ID] | [Adopt/Adapt/Reject/Defer/Validate] | [Role] | [Proposed/Approved/Built/Verified] |

## DS-001 — [NEW/MODIFIED/REMOVED/INVALIDATED]: [Title]

**Trigger and evidence:** [Link the evidence ID, adversarial-review finding, assumption test, or explicit product decision.]

**Rationale and intended outcome:** [Explain why the change is being made and the user or business outcome it supports.]

**Affected scope:** [Users, roles, workflows, data, interfaces, components, documentation, and metrics.]

**Specification:**

1. [Requirement or change statement.]
2. [Requirement or change statement.]
3. **Constraint / edge case:** [Required behavior under a meaningful exception or failure.]

**Acceptance criteria:**

| ID | Criterion | Verification method |
|---|---|---|
| AC-001 | [Observable, testable condition] | [Test, review, or metric] |

**Dependencies and risk:** [Dependencies, privacy/security/accessibility considerations, migration needs, residual risk, and required approvals.]

**Measurement and rollback:** [Success signal, observation window, rollback trigger, and reversal path where relevant.]

## Change Control Summary

| Baseline section | Delta IDs | Resolution |
|---|---|---|
| [Section/path] | [DS IDs] | [Pending merge / Incorporated in vX / Rejected] |
