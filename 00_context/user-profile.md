# User Profile

## Identity

- GitHub username: `MasayaSakata9`

## Preferences

- Use a dedicated Obsidian vault as persistent working memory for Cosmos-Transfer work.
- Keep the vault separate from active source code repositories.
- Preserve only high-signal summaries, not full raw conversations.
- Never store secrets, PATs, SSH keys, passwords, or credential-like strings in the vault.

## Structure Preference

Preferred top-level layout:

- `00_inbox/`
- `00_context/`
- `10_projects/`
- `20_references/`
- `30_findings/`
- `40_decisions/`
- `90_logs/`
- `templates/`

## Collaboration Pattern

- Codex should read vault context before meaningful work.
- Codex should write back results, judgments, blockers, and next actions after meaningful work.
- Durable knowledge belongs in findings and decisions, while session-level summaries belong in logs.
