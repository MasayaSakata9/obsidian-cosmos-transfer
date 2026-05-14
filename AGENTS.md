# AGENTS

## Purpose

This vault is the persistent working memory for Cosmos-Transfer work. It is separate from active source repositories and should hold durable summaries, not raw conversation dumps.

## Operating Goal

Use this vault to simulate stable working memory across sessions. The goal is not generic note storage, but fast context restoration that feels continuous and deliberate.

## Required Read Order Before Work

Read these files before starting meaningful work:

1. `AGENTS.md`
2. `00_context/index.md`
3. `00_context/current-context.md`
4. `00_context/user-profile.md`
5. `00_context/important-memories.md`
6. `10_projects/cosmos-transfer/index.md`
7. `90_logs/index.md`

After reading the required files, read any linked notes under "Read Next" in `00_context/important-memories.md` and any open items linked from `current-context.md`.

## Writeback Rules After Work

- Update `00_context/current-context.md` before ending the session.
- Update `00_context/important-memories.md` when a conversation point, result, or research outcome is likely to matter again.
- Write durable knowledge to `30_findings/`.
- Write explicit decisions and tradeoffs to `40_decisions/`.
- Write a session summary to `90_logs/`.
- Prefer short summaries that let a future Codex reconstruct context quickly.
- Do not paste full chat transcripts.
- Convert important conversations into distilled notes: what the user wanted, what changed, what now matters.
- Convert research into concise claims with source pointers and operational implications.
- If a session changes priorities, constraints, naming, preferences, or recurring procedures, update the durable note immediately rather than leaving it only in the session log.

## Memory Selection Rules

Write something durable when at least one of these is true:

- The user stated a stable preference or naming rule.
- A result or failure will likely affect future work.
- Research changed the plan, constraints, or choice set.
- A workaround, trap, or environment limitation was discovered.
- A decision required non-obvious tradeoffs.

Do not write something durable when it is only temporary chatter, easily reproducible noise, or an unimportant intermediate output.

## Safety Rules

- Never write secrets to this vault.
- Never write PATs, SSH keys, passwords, tokens, cookies, credential-like strings, private URLs with embedded auth, or copied environment dumps.
- If a secret appears in the working conversation, summarize the fact that auth exists without preserving the secret itself.
- When in doubt, omit the sensitive value and describe only the operational consequence.

## Note Style

- Keep notes compact and scannable.
- Record facts, decisions, blockers, next actions, and evidence locations.
- Prefer linking to repos, file paths, commands, and outputs by description rather than copying large blobs.
- Write for future recovery: a later Codex should be able to read the note and understand why it matters within a minute.
