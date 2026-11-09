# Roadmap and Implementation Status — v4.1

## Documented baseline
- [x] Two-plane intelligence/orchestration and local-execution architecture.
- [x] Permanent token-efficiency routing hierarchy.
- [x] HyperFrames + GSAP primary motion direction.
- [x] Remotion as selective specialist renderer.
- [x] Blender / Three.js for 3D and technical visuals.
- [x] FFmpeg / ffprobe for media operations and delivery.
- [x] Local-first transcription and TTS evaluation direction.
- [x] Explicit exclusion: no ComfyUI.
- [x] Final-video invariant: code-generated visuals only; no stock/static photos, downloaded footage, generic B-roll or still-image slides.
- [x] Internet tools and yt-dlp may be used for research/reference acquisition when useful; reference media cannot enter final renders.
- [x] v4 skill decisions and pilot acceptance gates documented.
- [x] ReelMimic selectively assessed; adoption boundary documented (not installed).

## Implementation backlog

### P0 — Reference Intelligence foundation
- [ ] Define reference input contract for local files and intentionally acquired online sources, with workspace containment and explicit provenance.
- [ ] Build ffprobe preflight, source hashing, proxy generation and contact sheets.
- [ ] Implement deterministic shot segmentation and per-shot duration/pacing summaries.
- [ ] Add camera-motion and visual-look summaries; document confidence/known failure modes.
- [ ] Add optional local audio/beat analysis from supplied media only.
- [ ] Write versioned `reference_report.json` and fingerprint schema; cache by source hash + analysis version + settings.
- [ ] Add tests for local and acquired references, malformed media, interrupted analysis, cache hit/invalidation and paths containing spaces/non-ASCII.
- [ ] Audit reference-ingestion dependencies, network calls, source provenance and rights; allow yt-dlp where useful but keep acquisition separate from final-render assets.
- [ ] Add a final-render asset validator that rejects photographic/video source assets and verifies that visual scene inputs are code-authored/generated.

### P1 — Reference-aware pre-production
- [ ] Map each planned shot to a reference shot and record the technique being adapted.
- [ ] Produce narration-anchored storyboard rows, style frames and continuity notes.
- [ ] Add required-input tracking and a human approval gate before rendering.
- [ ] Validate timing remapping after editorial cuts.

### P2 — Animation Recipe Engine
- [ ] Define versioned JSON scene-spec schema.
- [ ] Pilot graph + breakdown/map-route recipes on existing HyperFrames/GSAP/Blender/Three.js renderers.
- [ ] Validate deterministic output, cache keys, Windows setup, offline operation and human-reviewed contact sheets.

### P3 — Shot production and evidence-based QA
- [ ] Add isolated per-shot workspaces and bounded parallelism.
- [ ] Add fresh-context shot review and explicit review/fix round limits.
- [ ] Require before/after frame evidence for claimed fixes.
- [ ] Add final reference-vs-output diagnostic report; validate scores against human review before using thresholds.

### P4 — Other v4 pilots
- [ ] Code-review skill: pin revision; test small diff, multi-file refactor and seeded defect; measure misses, false positives, host support and cost.
- [ ] Storyboard QA: narration-anchored shot rows, local timing and semantic script-to-shot checks.
- [ ] Resolve Story Studio licence discrepancy before any code/corpus reuse.

### Production pilots
- [ ] Complete short-form video using local narration/transcription.
- [ ] Long-form explainer with persistent visual language.
- [ ] Compare motion approaches on the same representative scene.
- [ ] Validate local TTS quality, latency and hardware requirements.

## Final-render acceptance gate
- [ ] Inspect the final project manifest and asset graph: every visual must resolve to code-authored/generated scene content.
- [ ] Reject stock/static photos, downloaded video clips, generic B-roll and AI-generated raster-image assets from final output.
- [ ] Confirm reference downloads are used only in analysis folders and never linked by final-render scenes.

## Status discipline
A checkbox is complete only after implementation and representative tests. Documentation is not implementation. A smoke test is not editorial-quality proof. Record versions, environment, test media, outputs and limitations. No skill is active until installed, pinned and validated.
