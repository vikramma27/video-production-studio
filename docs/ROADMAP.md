# Roadmap and Implementation Status — v4

## Documented baseline
- [x] Two-plane intelligence/orchestration and local-execution architecture.
- [x] Permanent token-efficiency routing hierarchy.
- [x] HyperFrames + GSAP primary motion direction.
- [x] Remotion as selective specialist renderer.
- [x] Blender / Three.js for 3D and technical visuals.
- [x] FFmpeg / ffprobe for media operations and delivery.
- [x] Local-first transcription and TTS evaluation direction.
- [x] Explicit exclusions: no ComfyUI and no yt-dlp.
- [x] v4 skill decisions and pilot acceptance gates documented.

## Implementation backlog
### Foundation
- [ ] Create production project template and standard directory layout.
- [ ] Implement preflight/dependency checks.
- [ ] Implement asset hashing and metadata manifests.
- [ ] Implement persistent project state and decision-log conventions.

### Execution automation
- [ ] Build batch media probe/report.
- [ ] Build contact-sheet generation.
- [ ] Build stage runner with cache keys and selective invalidation.
- [ ] Build render QA checks and compact failure summaries.

### v4 pilots
- [ ] Animation Recipe Engine: JSON scene-spec schema and graph + breakdown/map-route proof of concept.
- [ ] Validate recipe render determinism, Windows setup, offline operation and human-reviewed contact sheets.
- [ ] Code-review skill: pin revision; test small diff, multi-file refactor and seeded defect; measure misses, false positives, host support and cost.
- [ ] Storyboard QA: narration-anchored shot rows, local timing and semantic script-to-shot checks.
- [ ] Resolve Story Studio licence discrepancy before any code/corpus reuse.

### Production pilots
- [ ] Complete short-form video using local narration/transcription.
- [ ] Long-form explainer with persistent visual language.
- [ ] Compare motion approaches on the same representative scene.
- [ ] Validate local TTS quality, latency and hardware requirements.

## Status discipline
A checkbox is complete only after implementation and representative tests. Documentation is not implementation. A smoke test is not editorial-quality proof. Record versions, environment, test media, outputs and limitations. No skill is active until installed, pinned and validated.
