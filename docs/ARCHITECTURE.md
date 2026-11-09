# Studio Architecture — v4.1

## Two-plane design
**Intelligence/orchestration:** Claude Code or Codex owns objectives, creative direction, planning, trade-offs, ambiguity, exception diagnosis, reusable automation design and quality decisions. Only one is the active AI worker for a project session.

**Local execution:** PowerShell, Python, Node.js, FFmpeg/ffprobe, local specialist models and selected renderers perform deterministic work.

## Routing hierarchy
1. Reuse valid output/cache.
2. Run deterministic local code or CLI.
3. Use a suitable local specialist model.
4. Make a bounded agent call.
5. Use a larger reasoning call only if justified.

## Tool responsibilities
| Domain | Default |
|---|---|
| Primary motion | HyperFrames + GSAP |
| React/data scenes | Remotion selectively |
| 3D/technical visuals | Blender / Three.js |
| Media operations | FFmpeg / ffprobe |
| Local transcription | faster-whisper |
| Offline TTS | Chatterbox / IndicF5 candidates |
| Image enhancement | Upscayl |

## v4.1 additions
- **Reference Intelligence Engine (planned):** local-file reference analysis, shot/camera/rhythm/look measurements, versioned fingerprints, shot-to-reference mapping and human approval before production. Selectively study ReelMimic; do not adopt its second orchestrator or renderer collection.
- **Animation Recipe Engine:** JSON scene spec → local renderer → contact sheet/QA. Six recipe families are patterns, not a new renderer.
- **Code-review skill:** advisory four-probe pilot for meaningful/high-risk diffs; never auto-merge.
- **Storyboard QA:** independently implement narration anchors, visual references and semantic shot checks using local transcription.
- Ray Sticker Shop stays separate; medical-paper skills excluded.

## Reference-to-animation flow
1. Accept a user-supplied local reference file; no URL download path.
2. Probe and normalize media; create a source hash, proxy and contact sheets.
3. Analyse cuts, durations, rhythm, camera movement, look and optional local audio cues.
4. Save a versioned report and fingerprint; cache only against matching source hash, analysis version and settings.
5. Build storyboard rows mapped to reference shots, with borrowed technique, camera intent, timing, narration anchor and continuity notes.
6. Generate style frames and request approval before production.
7. Dispatch isolated shot work to existing renderers; use bounded concurrency and disjoint output files.
8. Run fresh-context review, record evidence-backed fixes and compare final output to the reference as an advisory QA signal.

Numerical similarity is not a substitute for human judgement. Reference analysis learns techniques, not source footage, distinctive characters, logos or protected assets. Verify rights and provenance.

## Safety and compatibility boundary
The inspected ReelMimic revision is MIT for its main code, but bundled engines/assets have separate notices. Its `requirements.txt`, analysis script and agent instructions currently include yt-dlp, which is excluded here. Do not run upstream installers or copy code until the dependency, network, sandbox and licence audit is complete. The first adapter is local-file-only and must not inherit broad agent permissions.

## Pipeline and timeline
Brief → research/script → optional reference intelligence → voice/transcript → cleaned editorial timeline → visual language/recipes → render → assembly → QA → delivery/archive. After editorial cuts, remap captions, B-roll, effects and audio to the cleaned timeline.

## Reliability and scope
Every repeatable stage should be cache-aware, batchable and independently rerunnable. Persist project state, decisions, asset metadata, stage manifests and QA results. Offline-first; no paid inference/cloud uploads by default. No ComfyUI or yt-dlp. Scripts and pilots are backlog until implemented and tested on representative Windows hardware.
