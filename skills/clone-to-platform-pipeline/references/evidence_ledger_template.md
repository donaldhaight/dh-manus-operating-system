# Evidence Ledger Template

Use one row per material observation, market fact, or design decision. Preserve the original source URL or file path; do not place secrets or personal data in this file.

| ID | Claim or observation | Status | Source and access date | Confidence | Permitted use / restriction | Interpretation and next action |
|---|---|---|---|---|---|---|
| EV-001 | `<concise factual claim>` | `OBSERVED` | `<public URL or approved artifact>; YYYY-MM-DD` | `High / Medium / Low` | `<e.g., public behavior only; no asset/code reuse>` | `<functional learning, open question, or validation step>` |

## Status Definitions

| Status | Meaning |
|---|---|
| `OBSERVED` | Directly seen through authorized access or in an approved artifact. |
| `REPORTED` | Asserted by a credible source but not independently observed. |
| `INFERRED` | Reasonable interpretation of evidence; not established fact. |
| `ASSUMED` | Planning assumption requiring validation. |
| `DECIDED` | Independent product or technical decision; cite its ADR or specification section. |

## Use Rules

1. Cite evidence IDs in the opportunity map, requirements, ADRs, review notes, and delta specifications.
2. Downgrade confidence or revise status when new evidence contradicts an entry; preserve the change history in the relevant delta specification.
3. Treat a reference platform’s visible behavior as functional evidence only. Do not record or transfer source code, non-public endpoints, credentials, private content, or distinctive visual/copy expression.
