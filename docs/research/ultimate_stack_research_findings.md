# Ultimate Stack Research Findings

**Status:** Research synthesis input; recommendations remain subject to the Human Blockchain commissioning brief, current approvals, and the experimental-stack design review.

## 1. Identity, Authorization, and Auditability

OpenID Connect provides a standardized identity layer over OAuth 2.0, while OAuth’s current security guidance requires PKCE for authorization-code clients. Relationship-based authorization systems can express access through user, entity, group, role, and resource relationships; PostgreSQL Row-Level Security can provide a second data-tier isolation layer. Audit logs should record actor, action, time, target/context, and result without including session tokens, credentials, or unnecessary personal data.

**Sources:**
- [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html)
- [OAuth 2.0 Security Best Current Practice](https://oauth.net/2/oauth-best-practice/)
- [OpenFGA Documentation](https://openfga.dev/docs/)
- [PostgreSQL Row Security Policies](https://www.postgresql.org/docs/current/ddl-rowsecurity.html)
- [OWASP Logging Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)

## 2. Transactional Data, Evidence, and Events

PostgreSQL RLS can enforce row access at the database layer. The Transactional Outbox pattern keeps state changes and event publication atomically related, avoiding unreliable dual writes. pgvector provides vector similarity retrieval within PostgreSQL; object storage should retain large source/evidence files while the database stores metadata, lineage, permissions, and durable domain state. Typed event schemas reduce downstream automation breakage.

**Sources:**
- [PostgreSQL Row Security Policies](https://www.postgresql.org/docs/current/ddl-rowsecurity.html)
- [Transactional Outbox Pattern](https://microservices.io/patterns/data/transactional-outbox.html)
- [pgvector](https://github.com/pgvector/pgvector)
- [pg_jsonschema](https://supabase.com/docs/guides/database/extensions/pg_jsonschema)

## 3. Durable Workflows and Agent Orchestration

Durable workflow systems persist execution state across failures and long human-review delays. Stateful agent graphs can pause at explicit human-interrupt points and resume from a checkpoint. Agent handoffs require structured state/output contracts and idempotent handling of side effects; retries must not duplicate state transitions or external operations.

**Sources:**
- [Temporal Documentation](https://docs.temporal.io/temporal)
- [Temporal Retry Policies](https://docs.temporal.io/encyclopedia/retry-policies)
- [LangGraph Human-in-the-Loop](https://langchain-ai.github.io/langgraph/concepts/human_in_the_loop/)
- [LangGraph Multi-Agent Concepts](https://langchain-ai.github.io/langgraph/concepts/multi_agent/)

## 4. Automation and Integration Reliability

CloudEvents supplies standard event metadata such as event ID, source, and type. Inbound webhook integrations should verify signed and timestamped requests, and outbound/side-effect operations should use idempotency keys. A dead-letter/manual-review queue provides a safe response to permanently failed events rather than silently dropping or repeatedly retrying them.

**Sources:**
- [CloudEvents Specification](https://github.com/cloudevents/spec/blob/v1.0.2/cloudevents/spec.md)
- [Standard Webhooks Specification](https://github.com/standard-webhooks/standard-webhooks/blob/main/spec/standard-webhooks.md)
- [Temporal Approval Pattern](https://docs.temporal.io/design-patterns/approval)
- [Dead-Letter Queue Guidance](https://hookdeck.com/webhooks/guides/dead-letter-queues-webhook-reliability)

## 5. Operations, Security, and Recovery

OpenTelemetry provides a vendor-neutral model for traces, metrics, and logs, while the Collector centralizes telemetry processing, retry/batching, and filtering. Zero-trust principles require explicit authentication and authorization between services rather than trust by network location. Secrets must remain outside source control, infrastructure should be reproducible, and recovery requires protected backups plus tested restoration.

**Sources:**
- [OpenTelemetry Concepts](https://opentelemetry.io/docs/concepts/)
- [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)
- [NIST SP 800-204](https://csrc.nist.gov/pubs/sp/800/204/final)
- [NIST SP 800-209](https://csrc.nist.gov/pubs/sp/800/209/final)

## 6. Controlled Promotion and Delivery

GitHub deployment environments can require reviewers and wait timers before protected promotion. Architecture Decision Records preserve the rationale for material choices in the repository; build provenance and security checks are useful gates, but the beta should begin with simple, proportionate CI rather than pursuing complex supply-chain maturity before the first RRCA loop works.

**Sources:**
- [GitHub Deployment Environments](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)
- [SLSA Levels](https://slsa.dev/spec/v1.0/levels)
- [Architecture Decision Records](https://adr.github.io/)
- [OpenSSF Scorecard](https://github.com/ossf/scorecard)

## Design Filter from the Human Blockchain Knowledge Bundle

The Human Blockchain commissioning brief directs the team to begin with a modular monolith, PostgreSQL, object storage, versioned APIs/events, server-side permissions, synthetic/demo versus case-study versus production data boundaries, and a single RRCA end-to-end loop. It explicitly warns against premature microservices and against agents performing binding, regulated, financial, legal, production-access, or external-communication actions without qualified providers and human authority.

**Source:** `human-blockchain-operating-system/docs/00-start-here/master-continuity-brief.md` (retrieved at commit `be1725e`).

## Direct Validation Notes — Authorization and Data Isolation

OpenFGA’s organization-context guidance confirms that an authorization model can require both a base relationship and the currently selected organization context before access is allowed. It also clarifies that contextual tuples are request-scoped rather than persisted. For this system, the active entity/group context should be part of the signed/request context and durable relationship state should remain separately versioned and auditable.

PostgreSQL’s current row-security documentation confirms that enabled row-security policies constrain normal selects and data modifications, with default-deny behavior if no policy exists. It also warns that table owners and roles with `BYPASSRLS` ordinarily bypass the mechanism. The beta should therefore avoid routine application access through owners or bypass roles and test policies against least-privilege service accounts.

**Validated sources:**
- [OpenFGA: Authorization Through Organization Context](https://openfga.dev/docs/modeling/organization-context-authorization)
- [PostgreSQL: Row Security Policies](https://www.postgresql.org/docs/current/ddl-rowsecurity.html)

**Validation date:** 2026-08-26.

## Direct Validation Notes — Durable Approvals and Delivery Gates

Temporal’s approval pattern confirms that a workflow may wait for an external signal or timeout while recording the approver, decision, comment, and timestamp in durable workflow history. This fits the Human Blockchain requirement for a decision packet and named human gate; it does not authorize unattended external action.

GitHub’s environment documentation confirms that deployment protection rules can block a job before it runs or accesses environment secrets, and can require reviewers, wait timers, branch/tag restrictions, and anti-bypass configuration where the account plan supports them. The documentation also makes clear that availability differs by repository visibility and account plan; the experimental stack must verify the actual account capability before making protected environments a required control.

**Validated sources:**
- [Temporal: Approval Pattern](https://docs.temporal.io/design-patterns/approval)
- [GitHub: Managing Environments for Deployment](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment)

**Validation date:** 2026-08-26.
