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


## Permanent exclusions

The default production path must not introduce paid inference APIs, hosted generation credits, subscriptions, external uploads, or remote runtime dependencies. **ComfyUI remains excluded.** Internet research, reference downloads and tools such as yt-dlp are permitted when they materially improve the workflow, subject to rights, provenance, dependency and network review. Reference media is analysis-only and must never enter final renders. Final visuals remain code-authored/generated only.

## Status and evidence

This policy describes routing rules and pilot behaviour; it is not itself an installed runtime guard. The Animation Recipe Engine, code-review integration, storyboard QA, helper scripts and automated enforcement remain planned until committed, executed and validated on representative Windows hardware. Record actual token usage when available; otherwise report it as unknown.


## v5.0 reference, identity and batch controls
- Analyse representative ranked samples first; expand by evidence gaps rather than ingesting every upload.
- Batch metadata, frame extraction, contact sheets, transcription and shot metrics locally. Cache by source hash, analysis version and settings.
- Agents interpret style and original adaptation; deterministic tools handle probing, segmentation, contact sheets and manifests.
- Generate character candidates in batches with contact sheets and playable clips; never call an agent per frame.
- Voice auditions use fixed scripts and batch synthesis; user listens and chooses. Pin model, weights and settings.
- Generate idea candidates at 2–4x target; deterministic dedup/filter first, agent judgement for finalists.
- Batch independent preparation but limit GPU renders to measured capacity. Persist checkpoints and pause/resume controls.
- Never overwrite frozen character, voice or brand versions.


## v5.2 renderer and Cinetic token controls
- Remotion and HyperFrames + GSAP are co-equal renderers; select by scene needs, not habit.
- Batch scene authoring through reusable React/Remotion components or HyperFrames timelines; avoid one agent call per frame/scene.
- Cinetic is an optional pilot for launch/update films only. Use it when its brief-to-beat/QA workflow adds value; do not invoke on every episode or install duplicate wrappers.
- Cache scene outputs, contact sheets and QA reports by source/spec hash, renderer version and settings. Ask before bulk regeneration.
- Cinetic remains uninstalled until Windows preflight and the 20–30s comparative pilot pass.

## v5.4 Cinematic Skill routing
- Use Cinematic Skill only for narration-led documentary/explainer sequences where drawn 2D boards and virtual-camera movement add value; do not invoke it for every episode.
- Deterministic local code handles beat-sheet generation, VO timing, scene mapping, rendering, subtitles, contact sheets and manifests. Agent calls are reserved for story/visual intent and ambiguous editorial decisions.
- Cache rendered beats/contact sheets by script/audio hash, beat data, renderer revision, fonts and settings; rerun only invalidated beats.
- Feed a minimal renderer-neutral VO beat contract into native engine-specific scene specs. Do not force Remotion/HyperFrames/Blender to share Skia's scene representation.
- Exclude archive-photo discovery, downloads and AI raster stills from final-render paths. Preserve local TTS and offline execution.

## v5.5 Creator Generalist routing controls
- Invoke Creator Generalist only when a task needs its specific 2D/3D craft guidance; do not load the full skill pack for ordinary scripting, research or every episode.
- Load one generalist plus only the craft references needed for the current shot/task. Avoid reading all reference files or invoking one agent call per frame.
- Keep Blender/Remotion/HyperFrames/Three.js as native render targets; skill instructions map into existing engines and do not justify a new renderer by default.
- Use deterministic local scripts for mesh checks, contact/foot-slip tests, map data, frame extraction, rendering and QA. Reserve agent reasoning for creative intent and exceptions.
- Cache generated assets, playblasts, contact sheets and QA by source/spec hash, skill revision, renderer version and settings.
- First pilot is isolated to one agent workspace. Do not bulk-install into Claude Code and Codex or load excluded Watch Video/Design Sound plugins.
- Enforce the studio code-generated-only visual invariant; upstream asset-discovery and photo modes are not production routes.