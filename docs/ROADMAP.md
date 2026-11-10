# Roadmap and Implementation Status — v5.0 (v4.1 baseline preserved)

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


## v5.0 — Two-Channel Storytelling Factory

All items are approved backlog until implemented and evidenced. See [Blueprint](TWO_CHANNEL_STUDIO_BLUEPRINT.md) and [Acceptance Tests](IMPLEMENTATION_ACCEPTANCE_TESTS.md).

### P0 — Reference intelligence
- [ ] Resolve canonical IDs for https://www.youtube.com/@hisytstory and https://www.youtube.com/@herytstory.
- [ ] Collect balanced top-performing and representative Shorts/long-form with dated public metrics.
- [ ] Produce timestamped shot records, contact sheets, camera/lighting/acting/pacing/audio fingerprints and thumbnail maps.
- [ ] Enforce analysis-only reference isolation and final-render rejection.
- [ ] Human approve original quality targets.

### P1 — Original character pilots
- [ ] Build two original protagonist candidates in Blender.
- [ ] Create turnarounds, expression/body-action sheets and playable clips.
- [ ] Test identity across five scenes, lighting/camera/wardrobe.
- [ ] Implement iteration, approval and immutable freeze/versioning.

### P2 — Voice identity
- [ ] Evaluate Voicebox, Chatterbox, IndicF5 and selected local alternatives on Windows.
- [ ] Review commercial rights for exact model/weights.
- [ ] Produce playable auditions for both channels and freeze approved profiles.

### P3 — Original brand and thumbnails
- [ ] Curate original channel-name shortlist.
- [ ] Check exact/fuzzy YouTube name/handle conflicts, web use, trademark/domain signals.
- [ ] Recheck handle immediately before user reservation.
- [ ] Create icons, banners, visual identity sheets and thumbnail templates from original assets.

### P4 — Content planning
- [ ] Generate 2–4x candidate ideas for 30–60 desired approvals.
- [ ] Implement accept/reject/revise/shortlist/defer/merge board actions.
- [ ] Lock ideas to calendar and support one/two-week user-approved batches.

### P5 — Local episode factory
- [ ] Build durable local job board and resumable state machine.
- [ ] Integrate Blender Python render jobs; MCP remains optional.
- [ ] Benchmark render ceilings and bound concurrency.
- [ ] Integrate voice, Suno import, local audio fallback, FFmpeg assembly and QA.
- [ ] Produce four pilots (one Short and one long-form per channel) before scaling.

### P6 — Publishing preparation
- [ ] Generate upload packages and suggested slots.
- [ ] Keep upload/scheduling manual.
- [ ] Track performance and production cost separately per channel.


## v5.2 — Renderer expansion and Cinetic pilot

### P0 — Remotion promotion
- [x] Document Remotion as a first-class engine alongside HyperFrames + GSAP.
- [x] Record solo-individual Free License basis and official links; flag reassessment if project ownership/team/collaboration changes.
- [ ] Pin a current Remotion version and create a clean Windows starter project.
- [ ] Build representative code-authored scenes: typography, data-driven scene, character-adjacent 2D composition and transition-heavy sequence.
- [ ] Benchmark render speed, peak RAM/VRAM, determinism, output quality and offline reproducibility.
- [ ] Define scene handoff/export contracts with HyperFrames/FFmpeg; avoid unnecessary renderer chaining.

### P1 — Cinetic controlled pilot
- [x] Record Cinetic as approved for a controlled pilot, not installed.
- [ ] Review pinned source revision, MIT code licence, bundled scene/assets licences, music rules, dependencies, scripts and network calls.
- [ ] Validate Windows/Git Bash setup and all prerequisites before installation.
- [ ] Run one 20–30s launch-film brief through Cinetic + Remotion; inspect all 34 starter scenes and select only identity-compatible scenes.
- [ ] Compare against hand-authored Remotion; measure render time, memory, editability, sync, QA and human corrections.
- [ ] Confirm stock/image discovery is excluded from final render manifests.
- [ ] Keep Cinetic music workflow separate from the approved Suno exception.
- [ ] Promote, modify or reject Cinetic based on recorded evidence; do not bulk-install to both agents before this gate.

## v5.4 — Cinematic Skill specialist pilot

- [x] Review upstream scope and record controlled-pilot decision in [Cinematic Skill Adoption Assessment](CINEMATIC_SKILL_ADOPTION.md).
- [x] Define strict code-generated-only adaptation and archive/photo/AI-still exclusions.
- [x] Specify renderer-neutral narration beat contract and update agent workflows.
- [ ] Pin upstream commit; audit scripts, dependencies, licences, filesystem scope and network calls.
- [ ] Validate isolated installation on Windows/Git Bash; record Node/Python/Skia/FFmpeg/font prerequisites.
- [ ] Demonstrate offline execution after approved dependency setup, with no archive/download/hosted-generation path.
- [ ] Produce 60–90 second original engineering/science explainer using only code-generated graphics and existing local TTS.
- [ ] Validate subtitles, SFX/audio mix, camera movement, contact sheets and full playback.
- [ ] Measure render time, peak RAM/VRAM, determinism, failures, recovery and human correction time.
- [ ] Compare with a representative Remotion or HyperFrames implementation; promote only for a proven niche advantage.

Documentation and landing-page integration are complete in this branch; installation and runtime validation are deliberately not claimed.
