# ReelMimic Adoption Assessment — 2026-11-09

**Decision:** Adopt selectively as the reference-to-animation workflow blueprint. Do not vendor or install the repository wholesale.

Upstream: [edenfunf/reelmimic](https://github.com/edenfunf/reelmimic)  
Reviewed revision: `4e645857faefe34ff83596b09a43d7f610a4d481` (main tree inspected 2026-11-09)  
Upstream application licence: MIT. Bundled engines, assets, fonts and skills may carry separate licences; consult upstream `THIRD_PARTY_NOTICES.md` before reusing any of them.

## Why it matters

ReelMimic provides an unusually complete reference-video workflow rather than a single prompt or renderer:

1. Deterministic reference analysis: shot boundaries, shot durations, pacing, BPM/beats, colour/look statistics, framing and camera-motion estimates.
2. Style and production planning with a storyboard, character/asset plans and style frames.
3. A user approval gate before production.
4. File-contract-driven production stages, resumable jobs and explicit required outputs.
5. Parallel shot builders with fresh-context shot reviewers and bounded fix loops.
6. Evidence-backed corrections with before/after frame crops.
7. Final critique and timestamped user feedback.

Its analysis/perception code also exposes a useful direction for measuring similarity rather than relying only on subjective prompts: camera, rhythm, look, tension/peaks and frame-level components, with reference-to-output alignment.

## Source architecture observed

- React/Vite web interface, TypeScript/Node server, Python analysis tools and a repo-local agent workspace.
- The server dispatches Claude Code or Codex CLI agents and coordinates jobs through files/contracts and event streams.
- The documented production flow is analysis → style routing → planning → user approval → production setup/cast gate/parallel shot line → assembly → final critique/revision.
- The upstream README describes seven 2D drawing engines. It explicitly says the newer five are less mature than the vector/HyperFrames and painted-animation paths.
- Upstream reports 1–3.5 hours for a 30–60 second video after plan approval; this is an upstream estimate, not an independently benchmarked result.
- Current setup requirements documented upstream: Node 22.18+, Python 3.10+, FFmpeg, Chrome and a logged-in Claude Code or Codex CLI. The Windows installer installs Python requirements and npm dependencies; it does not make agent inference local.

## Adoption boundary for our studio

### Adopt as design patterns / evaluate for selective porting

- Reference-analysis report and contact-sheet workflow.
- Per-shot motion/camera, rhythm, look and audio-beat measurements.
- Versioned reference fingerprint and style-distance report, after validating metric usefulness.
- Shot-to-reference mapping in the storyboard (reference shot, technique being borrowed, camera/framing/motion intent).
- Human approval of storyboard, style frames and required inputs before rendering.
- File-contract-driven stage outputs, persistent job state, resumable stages and explicit cancellation.
- Parallel work only where files are isolated; independent fresh-context review for meaningful shots.
- Before/after evidence for fixes and a final full-video critique.

### Keep our existing production stack

- HyperFrames + GSAP remain the primary motion system.
- Remotion remains selective for React/data-driven scenes.
- Blender + Three.js remain specialist 3D/technical paths.
- FFmpeg/ffprobe remain media processing and final assembly.
- Our Animation Recipe Engine remains a structured scene-spec interface, not a second renderer.
- Our existing Claude-only and Codex-only playbooks remain the orchestration authority. ReelMimic's web app/server is not adopted as a second orchestrator in this phase.

### Explicit exclusions and blockers

- **yt-dlp is permitted where useful** for acquiring reference videos for analysis. Audit source, permissions, dependency, network behaviour, copyright and terms before use. Keep reference downloads in a separate analysis workspace and never connect them to final-render asset manifests.
- **No wholesale install/vendor.** Do not run upstream install scripts or copy the full repository. First audit dependency, script, network and licence surfaces.
- **No default full-access agent sandbox.** Upstream README documents `CODEX_SANDBOX` defaulting to `danger-full-access`. Do not inherit this default; use the host's least-privilege supported mode and inspect every command boundary.
- **No hosted inference or media upload by default.** ReelMimic runs locally but uses the user's Claude Code/Codex account for agent work. That is local orchestration, not fully local inference. Our studio keeps the local-model-first routing policy and requires explicit approval for hosted model use or external content transfer.
- **No replacement of our renderer stack.** Upstream's built-in drawing engines are 2D-focused. We retain our 3D and technical-visualization capability.
- **Third-party licence hygiene.** The upstream main code is MIT, but bundled skills/assets have separate licences (including Apache-2.0, MIT and font licences). Reuse only individually audited components with notices preserved.

## Proposed implementation sequence

### R0 — Safe reference-analysis adapter
- Define a controlled reference-input contract for local files and intentionally acquired online sources; record source URL, acquisition method, rights/provenance and local content hash.
- Probe metadata with ffprobe and generate normalized proxy/contact sheets.
- Detect cuts and compute shot durations, pacing, colour/look summaries and camera-motion estimates.
- Extract audio/beat cues only from supplied local audio/video.
- Persist a versioned `reference_report.json` plus source hash, tool versions and analysis settings.
- Cache by source hash and analysis-version; never reprocess unchanged references.

### R1 — Reference fingerprint and comparison
- Define versioned fingerprint schema for camera, rhythm, look, tension/peaks and frame summaries.
- Map storyboard shots to reference shot IDs.
- Compare the final render against the intended reference window and produce a diagnostic report plus visual overlays.
- Treat numerical scores as advisory until correlated with human assessments on a representative test set.

### R2 — Approval-first storyboard
- Generate storyboard rows with narration range, reference shot, borrowed technique, camera/motion intent, visual purpose, assets, continuity and acceptance criteria.
- Generate style frames/contact sheets.
- Require human approval and explicit required-input resolution before production.

### R3 — Isolated parallel production and QA
- Parallelize only independent shots with disjoint output files and a bounded worker budget.
- Dispatch reviewers in fresh context; reviewers must not review their own work.
- Use explicit review rounds, stop conditions and user escalation.
- Require before/after crops for claimed fixes; re-check fixed items.
- Assemble only after all blocking shot reviews pass or the user explicitly accepts documented exceptions.

### R4 — Production acceptance
- Test on Windows with local files only.
- Verify offline operation after approved dependencies are installed.
- Test determinism, cache invalidation, interruption/recovery, cancellation, bounded parallelism and failure handling.
- Compare analysis outputs with human annotations and inspect full playback.
- Record time, hardware, quality, failure rate and model usage; do not infer token savings.

## Acceptance criteria

A pilot is not promoted until:
- reference acquisition and analysis are explicit, auditable and rights-aware; yt-dlp may be used where useful;
- no downloaded reference video or still image can be referenced by a final-render scene;
- no hidden network calls or media uploads occur;
- local input and output paths are explicit and contained within the project workspace;
- dependency and third-party licences are recorded;
- analysis is repeatable and cache invalidation is correct;
- reference mappings and comparison reports are useful on representative clips;
- parallel workers cannot overwrite shared assets or each other's shot files;
- reviewers produce evidence-backed findings and cannot silently waive blockers;
- a Windows test run, contact-sheet inspection and complete playback review are recorded.

## Final-video rule
The final video must be composed entirely from code-authored/generated visuals. Permitted examples include SVG, Canvas/WebGL, procedural graphics, charts, typography, animation, simulations and 3D geometry. Prohibited final visual inputs include stock/static photos, downloaded video clips and generic downloaded B-roll. Reference footage can be downloaded and analysed, but is not a production asset.

## Current status

**Approved for selective study and implementation planning. Not installed, not vendored, and not production-validated in our studio.** The first implementation should be our own reference-analysis adapter with audited local/online ingestion, not a full ReelMimic clone.
