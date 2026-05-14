# Finding: Vault Bootstrap Findings

## Finding

The Cosmos-Transfer persistent memory vault works best as an isolated Git repository under `/root/.codex/memories/obsidian-cosmos-transfer`, not inside the active code workspace.

## Evidence

- `/workspace` already contained unrelated uncommitted changes during bootstrap.
- Anonymous clone attempts against the target GitHub repo returned `repository not found` until the repo was created.
- After the repo was created, push required rebasing onto the remote's README-only initial commit.

## Impact

- Future sessions should treat the vault as its own repo with its own Git lifecycle.
- GitHub repo creation order matters: remote may need fetch/rebase before first push.
- Context restoration should start from this vault, not from the active code repo.
