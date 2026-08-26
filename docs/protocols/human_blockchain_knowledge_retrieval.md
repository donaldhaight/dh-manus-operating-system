# Human Blockchain Knowledge Retrieval Protocol

## Purpose

Use the private `donaldhaight/human-blockchain-operating-system` repository as a **source-grounded knowledge library** for Human Blockchain-specific work. Retrieve only the documents relevant to the current mission or question; do not treat the repository as a monolithic prompt, a source of unrestricted authority, or immutable doctrine.

## Governing Rule

The knowledge bundle states that the founder’s current narrated intention, approved decisions, and observed operating results control current execution; historical corpus material is retrievable evidence and creative supply. Apply this precedence whenever the library conflicts with a current user message or a newer approved record.

## Retrieval Order

| Priority | Source class | Typical repository paths | How to use it |
|---:|---|---|---|
| 1 | Current user instruction and approved current state | Current conversation; `docs/00-start-here/current-state.md` | Controls the immediate task and overrides older working assumptions. |
| 2 | Constitution, definitions, and active decision/risk registers | `okf.yaml`; `docs/00-start-here/shared-definitions.md`; `docs/90-registers/` | Establishes terminology, authority, active decisions, assumptions, and review gates. |
| 3 | Mission/product/business working artifacts | `docs/10-business/`; `docs/20-product/`; `docs/30-evidence/`; `docs/40-market/`; `docs/50-execution/` | Supplies task-specific context, requirements, models, plans, and implementation detail. |
| 4 | Operational narrative and milestone records | `docs/00-start-here/operational-narrative.md`; `docs/60-history/` | Supplies evolving context and history; label clearly as active-working or historical. |
| 5 | Preserved source corpus | `sources/` | Use for provenance, recovery, creative context, or source reconciliation; do not elevate it above current approved decisions without review. |

## Retrieval Routine

1. Identify the current question, mission, stakeholder, and decision requested.
2. Search the manifest and file headings for candidate documents; retrieve the minimum necessary context.
3. Read the relevant current-state, decision, assumption, and risk records before relying on a working draft.
4. State whether a material assertion is **sourced**, **working draft**, **historical context**, **inference**, **assumption**, or **new proposal**.
5. Cite the repository-relative path and the repository commit or retrieval date in internal/technical artifacts. In messages, cite the path when the source materially influences the recommendation.
6. If sources conflict, surface the conflict and recommend the relevant human decision gate; do not silently select a convenient version.
7. Do not modify the Human Blockchain repository as part of retrieval. Propose a versioned update separately when new work reveals a correction, gap, or decision candidate.

## Citation Format

Use this form in internal operating artifacts:

```text
[HBO:docs/20-product/phase1-product-requirements.md @ <commit>] — <status>; retrieved YYYY-MM-DD
```

Use this form in conversational summaries when path-level transparency is useful:

```text
Source: `human-blockchain-operating-system/docs/90-registers/decisions.md` (active register; retrieved YYYY-MM-DD).
```

## Quality Checks

Before using a Human Blockchain source as the basis for a material recommendation, verify:

- The document’s manifest status and source ID, if applicable.
- Whether a newer current-state, decision, assumption, or risk record supersedes it.
- Whether the content is narrative/creative supply, a working draft, an active register, or accepted history.
- Whether the current user has given a more recent instruction.
- Whether the proposed use stays within the repository’s evidence and access boundaries.

## Current Retrieval Anchor

- Repository: `donaldhaight/human-blockchain-operating-system`
- Branch: `main`
- Initial session retrieval anchor: `be1725e` — `Deploy Docusaurus knowledge site with GitHub Pages (#11)`
- Bundle version: `human-blockchain-okf-001` / `0.2`

## Non-Goals

This protocol does not create a production RAG service, embed a vector database, grant any agent persistent external authority, or replace the founder’s direct instructions. It establishes a repeatable **retrieve, ground, cite, and escalate** discipline for messages and mission work in this environment.
