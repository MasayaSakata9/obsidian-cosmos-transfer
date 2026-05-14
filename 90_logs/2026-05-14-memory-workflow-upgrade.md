# Session Log: 2026-05-14 Memory Workflow Upgrade

## Summary

- Evaluated the current vault as structurally sound but too thin for durable, human-like recall.
- Added an `important-memories` note as the curated auto-reread layer.
- Added one durable finding and one decision note to demonstrate how important conversation outcomes and bootstrap lessons should be preserved.

## Results

- Future sessions now have a fixed read order that includes high-value memories after the base context files.
- The vault now distinguishes between session logs and durable memory worth rereading.
- Templates now prompt future sessions to identify memory candidates and reuse triggers.

## Decisions

- Important conversation outcomes should be distilled into durable notes instead of left only in logs.
- Auto-reread should be selective and curated rather than scanning every historical note.

## Important Memory Candidates

- The separate-vault decision is durable and should stay in `40_decisions/`.
- Bootstrap findings about repo separation and initial push behavior are durable and should stay in `30_findings/`.

## Blockers

- Automatic reread is rule-driven, not a background daemon. Future Codex sessions must follow `AGENTS.md`.

## Next Actions

- As new work happens, promote repeated user preferences, research outcomes, and important failures into `important-memories`, findings, and decisions.
