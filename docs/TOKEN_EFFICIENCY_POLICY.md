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


## v4 skill-specific token controls

The new skills do not change the permanent routing hierarchy. They are optional reasoning aids, not workers that should be invoked on every file or frame.

### Animation Recipe Engine
- Agent calls are limited to creative recipe selection, scene-spec authoring, ambiguous visual decisions and review of failed/representative output.
- A versioned JSON scene specification is the handoff contract.
- Local deterministic renderers produce scenes, contact sheets and technical QA.
- Cache by scene spec, assets, renderer/tool versions and relevant settings; rerun only invalidated stages.
- Do not make one model call per scene/frame when a batch renderer can process the scene list.

### Code review
- Invoke the four-probe review only for meaningful or high-risk diffs.
- Do not run it on every typo, formatting-only change or trivial edit.
- Keep the output advisory. Tests, CI, security checks and human review remain separate.
- Record actual invocation cost and useful findings; never infer token savings from a green report.

### Audio-first storyboard QA
- Use local transcription/timestamping to build narration-anchored shot rows.
- Deterministic code handles timeline mapping, row generation, manifests and consistency checks.
- Use an agent only for semantic alignment, visual continuity decisions and ambiguous editorial exceptions.
- Do not send narration, scripts or media to hosted providers by default.

### Pilot measurement
For each pilot, record model/tool version, calls made, approximate or actual usage where available, local execution time, cache hits, false positives/misses, and human corrections. Unknown values remain unknown. A pilot is not promoted merely because it reduces agent calls; output quality and reliability must also pass.
