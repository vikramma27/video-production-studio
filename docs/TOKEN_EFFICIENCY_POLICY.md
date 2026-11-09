# Permanent Token-Efficiency Policy
**Status: non-negotiable default.** Claude Code and Codex are the intelligence/orchestration layer, not repetitive workers. Change only with explicit user approval.

## Routing gate
1. Reuse an existing output or valid cache.
2. Use deterministic local code or CLI.
3. Use a suitable local specialist model.
4. Make a bounded agent call for judgement or ambiguity.
5. Use a larger reasoning call only when justified.

## Agent responsibilities
Creative direction, planning, architecture, trade-offs, ambiguous reasoning, reusable automation design, exception diagnosis and quality review.

## Local worker responsibilities
File discovery, hashing, copying, media probing, batch conversion, trimming, muxing, encoding, subtitle conversion, deterministic timeline mapping, contact sheets, thumbnails, metadata reports, template-driven scene rendering, preflight, validation, cache management and manifests.

## Execution standards
- Batch operations; do not drip-feed files.
- Cache using stable inputs, tool versions and relevant settings.
- Make stages independently rerunnable; invalidate only affected downstream stages.
- Prefer event-driven triggers; avoid wasteful polling.
- Persist decisions and project state in files.
- Send compact summaries, diffs and exception reports to agents.
- Never fabricate token counts or claimed savings.
- Stop after two same-method failures and diagnose.
- Ask before unplanned paid/cloud work or bulk regeneration.

See [Master Playbook](MASTER_PLAYBOOK.md). Helpers and runtime enforcement remain backlog until implemented and tested.
