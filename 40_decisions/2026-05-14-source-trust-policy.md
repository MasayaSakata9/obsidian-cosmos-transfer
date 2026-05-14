# Decision: Source Trust Policy For Cosmos-Transfer Research

## Decision

Use a graded source hierarchy for Cosmos-Transfer claims:

- `A`: NVIDIA docs, local code, official GitHub, official Hugging Face model card.
- `B`: NVIDIA Newsroom, NVIDIA Blog, official partner/company press releases.
- `C`: NVIDIA Research pages and arXiv papers.
- `D`: third-party summaries and community discussions.

Durable operational claims should rely on `A` evidence whenever possible. `B` and `C` can support context and research direction, but should not be treated as deployment guarantees.

## Context

The user wants reliable information for autonomous-driving training-data decisions. This requires separating implementation facts from marketing, ecosystem adoption, and research evaluation.

## Alternatives Considered

- Treat all public web sources equally.
- Exclude ecosystem and research sources entirely.
- Use only local code.

## Consequences

- The vault can include broader ecosystem knowledge without overstating it.
- Future decisions about Japanese dashcam data remain anchored to verified model behavior and official constraints.
