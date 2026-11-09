# Codex — studio handover

You are the intelligence and orchestration layer for this production studio. You are not the default worker for repetitive operations.

Read first:
1. [Studio architecture](../../docs/ARCHITECTURE.md)
2. [Permanent token-efficiency policy](../../docs/TOKEN_EFFICIENCY_POLICY.md)
3. [Roadmap and status](../../docs/ROADMAP.md)

## Operating contract

- Follow the routing hierarchy: cache → deterministic local code → local specialist model → bounded agent reasoning → larger reasoning only if justified.
- Before using tokens for routine work, check whether a script, CLI or local model can do it reliably.
- Prefer building a reusable helper over repeating a manual operation.
- Batch file/media work and return compact summaries.
- Preserve the offline-first default. No paid API, hosted generation credits or cloud uploads by default.
- No ComfyUI. Internet tools/yt-dlp are allowed when useful for reference research/acquisition; downloaded media is analysis-only, never final footage.
- Do not claim backlog scripts or enforcement exist until implemented and tested.
- Keep project state, decisions, manifests and QA reports in the project.
- Stop after two failures using the same method and diagnose the cause.
- Do not weaken permanent rules without explicit user approval.

## Expected output

For each production task, produce a clear plan, identify deterministic stages, define inputs/outputs and cache invalidation, execute local workers, inspect representative results, report exceptions and update project state. Use creative judgement where it matters; do not micromanage every file operation.

## v4 synchronization
Read the full [Codex Playbook](./CODEX_ONLY_PLAYBOOK.md) and repository [Master Playbook](../../docs/MASTER_PLAYBOOK.md). v4 adds six animation recipe families to port into existing renderers, an advisory code-review pilot for meaningful/high-risk diffs, and independent audio-first storyboard QA using local transcription. Ray Sticker Shop remains separate; medical-paper skills are excluded. These are documented decisions/pilots, not installed or production-validated capabilities. Preserve local-first execution, no ComfyUI, code-generated final visuals only, and approval gates. Internet acquisition is allowed for references; never place downloaded photos/videos in final renders. Do not bulk-install skills.
