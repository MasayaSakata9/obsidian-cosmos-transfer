# AGENTS

## Purpose

This vault is the persistent working memory for Cosmos-Transfer work. It is separate from active source repositories and should hold durable summaries, not raw conversation dumps.

## Required Read Order Before Work

Read these files before starting meaningful work:

1. `AGENTS.md`
2. `00_context/index.md`
3. `00_context/current-context.md`
4. `00_context/user-profile.md`
5. `10_projects/cosmos-transfer/index.md`
6. `90_logs/index.md`

## Writeback Rules After Work

- Update `00_context/current-context.md` before ending the session.
- Write durable knowledge to `30_findings/`.
- Write explicit decisions and tradeoffs to `40_decisions/`.
- Write a session summary to `90_logs/`.
- Prefer short summaries that let a future Codex reconstruct context quickly.
- Do not paste full chat transcripts.

## Safety Rules

- Never write secrets to this vault.
- Never write PATs, SSH keys, passwords, tokens, cookies, credential-like strings, private URLs with embedded auth, or copied environment dumps.
- If a secret appears in the working conversation, summarize the fact that auth exists without preserving the secret itself.
- When in doubt, omit the sensitive value and describe only the operational consequence.

## Note Style

- Keep notes compact and scannable.
- Record facts, decisions, blockers, next actions, and evidence locations.
- Prefer linking to repos, file paths, commands, and outputs by description rather than copying large blobs.
