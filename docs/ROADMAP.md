# Roadmap and implementation status

## Documented baseline

- [x] Two-plane architecture: intelligence/orchestration and local execution.
- [x] Permanent token-efficiency routing rule.
- [x] HyperFrames + GSAP primary motion direction.
- [x] Remotion as a selective specialist renderer.
- [x] Blender / Three.js for 3D and technical visuals.
- [x] FFmpeg / ffprobe for media operations and delivery.
- [x] Local-first transcription and TTS evaluation direction.
- [x] Explicit exclusions: ComfyUI and yt-dlp.

## Implementation backlog

### Foundation
- [ ] Create production project template and standard directory layout.
- [ ] Implement preflight and dependency checks.
- [ ] Implement asset hashing and metadata manifest.
- [ ] Implement project state and decision log conventions.

### Execution automation
- [ ] Build batch media probe and report.
- [ ] Build contact-sheet generation.
- [ ] Build stage runner with cache keys and selective invalidation.
- [ ] Build render QA checks and compact failure summaries.

### Production pilots
- [ ] Pilot a complete short-form video using local narration/transcription.
- [ ] Pilot a long-form explainer with persistent visual language.
- [ ] Compare motion approaches on the same representative scene.
- [ ] Validate local TTS quality, latency and hardware needs.

## Status discipline

A checkbox is marked complete only after implementation and a representative test. Documentation of a proposed script is not implementation. A successful smoke test is not proof of editorial quality. Record tool versions, test media, outputs and known limitations for every pilot.
