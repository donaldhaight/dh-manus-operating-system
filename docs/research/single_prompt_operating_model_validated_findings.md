# Validated Research Findings

## MetaGPT

The MetaGPT paper describes a multi-agent collaboration framework that encodes **standardized operating procedures** into prompt sequences, assigns distinct roles through an assembly-line paradigm, and uses intermediate verification to reduce errors arising from naive agent chaining. The transferable lesson is not that a single prompt can autonomously complete every enterprise function; it is that a launch instruction can activate a bounded workflow with explicit roles, handoffs, and tangible artifacts. Source: [MetaGPT paper](https://arxiv.org/abs/2308.00352).

## AI Governance

NIST presents the AI Risk Management Framework as voluntary guidance intended to improve the trustworthiness of AI while mitigating risk. The NIST page currently notes that AI RMF 1.0 is being revised, so this operating model will use it as a governance orientation rather than claiming compliance with a static standard. Source: [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework).

## Design Implication

The Human Blockchain one-prompt model should launch a governed **work graph**: it selects an approved mission and context pack, initializes named artifacts and bounded agent roles, and stops at human decision gates. It should not be a monolithic context dump or an unbounded authority grant.

## Knowledge Architecture

The current GraphRAG architecture describes a GraphRAG Knowledge Model, a core indexing pipeline, and LLM caching that returns cached results for the same input set and parameters. It also exposes configurable providers for models, input readers, caches, logs, storage, vector stores, and workflow steps. This supports using a governed, modular knowledge pipeline with reproducible processing rather than treating the entire Human Blockchain corpus as prompt text. Source: [GraphRAG architecture](https://microsoft.github.io/graphrag/index/architecture/).

## Living Decisions

AWS explains that Architecture Decision Records document the context, alternatives, and rationale behind important decisions, and recommends linking superseding decisions to the records they replace. The operating model should apply this principle beyond software architecture: material market, product, finance, policy, automation, and delivery decisions should have an owner, evidence basis, decision state, and successor link. Source: [AWS ADR practices](https://aws.amazon.com/blogs/architecture/master-architecture-decision-records-adrs-best-practices-for-effective-decision-making/).
