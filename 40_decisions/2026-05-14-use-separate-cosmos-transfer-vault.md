# Decision: Use Separate Cosmos-Transfer Vault

## Decision

Use `obsidian-cosmos-transfer` as a dedicated Obsidian vault and standalone Git repository for persistent Codex memory.

## Context

The active workspace already had unrelated source changes. The user wanted durable memory for future Codex sessions without mixing it into current code repositories.

## Alternatives Considered

- Store notes directly in the active source repository.
- Keep only ephemeral session context without a durable vault.
- Clone a pre-existing remote vault first.

## Consequences

- The vault can be opened independently in Obsidian and synced independently with Git.
- Future Codex sessions have a stable place to read and write summaries.
- Git auth and remote setup for the vault are now separate concerns from code repo auth.
