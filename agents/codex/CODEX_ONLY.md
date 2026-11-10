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


## v5.0 two-channel studio contract
Read the [Blueprint](../../docs/TWO_CHANNEL_STUDIO_BLUEPRINT.md), [Reference Analysis](../../docs/REFERENCE_REVERSE_ENGINEERING.md), [Character DNA](../../docs/CHARACTER_DNA_AND_LOCKS.md), [Voice Identity](../../docs/VOICE_IDENTITY_SYSTEM.md), [Brand/Thumbnails](../../docs/BRAND_NAMING_AND_THUMBNAILS.md), [Content Board](../../docs/CONTENT_BOARD_AND_BATCH_OPERATIONS.md), [Blender Engine](../../docs/BLENDER_PRODUCTION_ENGINE.md), [Operations](../../docs/PRODUCTION_OPERATIONS.md) and [Acceptance Tests](../../docs/IMPLEMENTATION_ACCEPTANCE_TESTS.md). Benchmark @hisytstory and @herytstory only. Analyse top-performing and representative videos shot by shot, subject to rights/platform terms. Create original characters, voices, names, stories and thumbnails. Present playable pilots; never freeze without explicit approval. Generate 2–4x idea candidates for a 30–60 user-approved backlog. Ask for one/two-week batch choice. Run local resumable jobs with resource-bounded Blender renders. Prepare upload packages; user publishes manually.


## v5.2 renderer and Cinetic update
Treat Remotion and HyperFrames + GSAP as co-equal first-class engines; Remotion is not restricted to selective specialist scenes. Choose the engine per scene and use Blender/Three.js for justified 3D. Read [Cinetic Adoption Assessment](../../docs/CINETIC_ADOPTION.md): Cinetic is approved for a controlled launch-film/update-video pilot only, not installed and not a replacement orchestrator. Remotion's solo-operator Free License is documented in the master playbook; reassess if project ownership/team/collaboration changes. Preserve the final code-generated-visual invariant, separate Cinetic's human-made instrumental music rule from the approved Suno exception, and never assume its Remotion scenes are HyperFrames-compatible. Do not install until the Windows preflight and pilot plan are approved.

## v5.4 Cinematic Skill workflow
Read [Cinematic Skill Adoption Assessment](../../docs/CINEMATIC_SKILL_ADOPTION.md). Moh4696/cinematic-skill is approved only for an isolated Python + Skia documentary/explainer pilot; it is **not installed, Windows-validated or production-ready**. Use it for code-drawn diagrams, maps, typography, annotations and virtual-camera movement—not character acting/complex 3D. Keep Remotion and HyperFrames + GSAP first-class and Blender as primary 3D.

Create a minimal renderer-neutral narration beat contract (`beat_id`, `shot_id`, VO in/out, narration text, visual intent, camera path, transition, provenance, approval state), then map it into the selected engine's native scene format. Use deterministic local tools for timing/rendering/contact sheets/QA; reserve Codex reasoning for creative intent and exceptions.

Do not install globally or into both agents. First pin and audit the upstream revision, licence, dependencies, scripts, network/filesystem behaviour and Windows/Git Bash requirements. Existing local TTS only. Final visuals remain code-generated: exclude archive photographs, scans, downloaded/stock imagery, video, generic B-roll and AI raster stills. Require a 60–90 second code-only pilot, offline/Windows tests, full playback and comparison before promotion.

## v5.5 Creator Generalist skill policy
Read [Creator Generalist Adoption Assessment](../../docs/CREATOR_GENERALIST_ADOPTION.md). It is a selective, isolated skill pilot—not installed or validated. Use only selected 3D Generalist/craft skills and filtered 2D Generalist for code-generated maps/charts/diagrams. Blender remains the 3D renderer; Remotion and HyperFrames + GSAP remain co-equal motion engines. Do not add 67.js.
Do not install Watch Video or Design Sound in the first pilot. No photo mode, downloaded asset sourcing, scans, stock imagery, downloaded video, generic B-roll, AI raster stills, ElevenLabs, hosted generation or ComfyUI. Final visuals are original and code-generated; reference media remains analysis-only. Pin and audit the source/dependencies/licences/network/filesystem behaviour, then stage in one isolated workspace only after approval. Do not bulk-install globally or into both agents.