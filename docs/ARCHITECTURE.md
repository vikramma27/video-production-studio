# Studio Architecture — v5.0 (v4.1 baseline preserved)

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
1. Accept a user-supplied local file or intentionally acquired online reference, subject to rights/platform terms and access restrictions.
2. Probe and normalize media; create a source hash, proxy and contact sheets.
3. Analyse cuts, durations, rhythm, camera movement, look and optional local audio cues.
4. Save a versioned report and fingerprint; cache only against matching source hash, analysis version and settings.
5. Build storyboard rows mapped to reference shots, with borrowed technique, camera intent, timing, narration anchor and continuity notes.
6. Generate style frames and request approval before production.
7. Dispatch isolated shot work to existing renderers; use bounded concurrency and disjoint output files.
8. Run fresh-context review, record evidence-backed fixes and compare final output to the reference as an advisory QA signal.

Numerical similarity is not a substitute for human judgement. Reference analysis learns techniques, not source footage, distinctive characters, logos or protected assets. Verify rights and provenance.

## Safety and compatibility boundary
The inspected ReelMimic revision is MIT for its main code, but bundled engines/assets have separate notices. Its reference-ingestion path uses yt-dlp; this is permitted when useful after dependency, network, sandbox and rights review. Reference downloads are analysis-only and must never enter final renders. Do not inherit broad agent permissions.

## Pipeline and timeline
Brief → research/script → optional reference intelligence → voice/transcript → cleaned editorial timeline → visual language/recipes → render → assembly → QA → delivery/archive. After editorial cuts, remap captions, B-roll, effects and audio to the cleaned timeline.

## Final-video visual invariant
All final visual content must be authored/generated through code in our rendering pipeline: vector graphics, Canvas/WebGL, procedural animation, charts, typography, simulations and 3D geometry. Never place stock/static photos, downloaded video, generic B-roll in final renders. Online/reference footage may be analysed for technique and style but is never a final visual asset.

## Reliability and scope
Every repeatable stage should be cache-aware, batchable and independently rerunnable. Persist project state, decisions, source provenance, stage manifests and QA results. Local-first; internet access is allowed when it materially improves research/reference acquisition. No paid inference/cloud uploads by default. No ComfyUI. Scripts and pilots are backlog until implemented and tested on representative Windows hardware.


## v5.0 two-channel production architecture

The system adds reference intelligence, brand/identity locks and a repeatable local episode factory. Benchmarks: https://www.youtube.com/@hisytstory and https://www.youtube.com/@herytstory. They inform quality attributes, never copied expressive assets.

Subsystems: (1) reference discovery/ranking, shot-by-shot segmentation, contact sheets and style fingerprints; (2) separate original channel bibles and Blender character/rig/animation library; (3) local voice auditions and immutable profile versions; (4) original channel names/handles, icons, banners and thumbnail grammar; (5) idea generation at 2–4x target, review board and 30–60 locked ideas; (6) local job orchestration with durable manifests and resumable resource-aware queues.

Reference downloads are allowed only where lawful and consistent with platform terms; never bypass access controls. Isolate references from production assets. Analyse shot length, framing, camera movement, lighting, palette, acting, transitions, narration rhythm and thumbnail layout. Do not reproduce exact frames, scripts, character designs, logos or distinctive compositions.

Blender + Python is primary for channel 3D. MCP for Blender is a candidate interactive interface only; deterministic Blender Python/CLI runs production independently. Audit revision, installer, dependencies, telemetry and permissions; disable telemetry, safe mode, localhost only. Preserve HyperFrames + GSAP, selective Remotion, Three.js and FFmpeg/ffprobe.

The laptop/workstation is the local execution host. Parallelize independent preparation; serialize heavy GPU renders until measured VRAM/RAM/thermal benchmarks justify concurrency. Persist queue state and recover after restarts. User chooses one/two-week batches. Prepare upload packages; user publishes manually.

Evaluate Jamie Pine Voicebox as a local UI candidate; Chatterbox/IndicF5 remain candidates. Verify exact model/weight licences. Suno is a narrow user-approved music-composition exception; no other paid hosted inference is implied.


## v5.2 renderer and Cinetic decisions

Remotion and HyperFrames + GSAP are co-equal first-class motion engines. Remotion supports full React-based compositions, reusable scene components and data-driven/launch-film/update-video workflows; HyperFrames + GSAP remains first-class for precise timeline and beat-driven motion. Renderer selection is scene-specific and evidence-based, not a blanket default. Blender + Python remains the primary original 3D character/environment engine; Three.js is specialist; FFmpeg/ffprobe owns final media assembly and technical QA.

The project is currently operated by one individual. Remotion's official Free License permits individual personal/commercial use and automation, subject to its terms. Remotion is source-available under a proprietary licence, not OSI open source. Reassess if project ownership, collaboration or involved-party headcount changes. See [official FAQ](https://convert.remotion.dev/docs/license/faq) and [Terms](https://www.remotion.dev/docs/terms).

Cinetic (MIT) is approved for a controlled pilot as an optional agent skill for launch films, update videos, trailers and social cut-downs—not as a second orchestrator or replacement renderer. Evaluate its v1.5 34-scene Remotion starter on Windows. Do not assume those scenes are HyperFrames-compatible. Preserve original code-generated visuals; exclude stock/downloaded imagery. Its human-made instrumental music requirement is separate from the user's narrow approved Suno exception. Validate dependencies, Git Bash/Windows support, render-time impact (especially motion blur), reproducibility, audio sync and QA before adoption. See [Cinetic Adoption Assessment](CINETIC_ADOPTION.md).
