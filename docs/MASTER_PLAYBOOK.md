# Master Production Playbook — v5.0 (v4.1 baseline preserved)
**Video Production Studio | 2026-11-09**

Canonical operating specification for the offline-first, code-driven faceless video studio. Documentation is not implementation: no capability is considered installed or production-ready until it exists in the actual Windows project and passes representative tests.

## Mission and operating model
Build a repeatable studio for original long-form videos and Shorts, with English/Tamil narration options, code-generated visuals, reliable editing and human-reviewed delivery.

- **Intelligence plane:** Claude Code or Codex handles creative direction, planning, research synthesis, trade-offs, ambiguity, exception diagnosis and quality decisions.
- **Local execution plane:** PowerShell, Python, Node.js, FFmpeg/ffprobe, local specialist models and production renderers execute repeatable work.

Mandatory routing: **reuse/cache → deterministic local code → local specialist model → bounded agent reasoning → larger reasoning only if justified.** Batch work, persist state in files, invalidate only affected stages, summarize logs locally and stop after two failures using the same method.

## Production pipeline
1. Brief and success criteria.
2. Evidence-backed research, source notes and rights review.
3. Script, narrative structure, hooks and claim-level fact checks.
4. Voice generation/import; preserve source audio.
5. Local transcription and timing where required.
6. Narration-anchored EDL and cleaned timeline.
7. Reference-video analysis and production blueprint, when a visual reference is supplied.
8. Persistent visual language, storyboard approval and scene grammar.
9. Recipe selection and scene production.
10. Assembly of narration, visuals, music, effects and captions.
11. Technical QA, contact sheets, representative frame inspection and full playback.
12. Verified delivery and archived manifests, assets and decisions.

**Timeline integrity:** after cuts, all captions, B-roll, effects and audio must map to the cleaned timeline. Never reuse original timestamps without applying the edit mapping.

## Technology responsibilities
| Responsibility | Default |
|---|---|
| Primary motion | HyperFrames + GSAP |
| Specialist React/data scenes | Remotion selectively |
| 3D / technical visuals | Blender + Three.js |
| Media processing / final assembly | FFmpeg + ffprobe |
| Local transcription | faster-whisper |
| Offline narration candidates | Chatterbox + IndicF5 |
| Image enhancement | Upscayl |
| Automation | PowerShell, Python, Node.js |

Do not add a renderer merely because a skill bundles one. Preserve working integrations. Final renders must not depend on remote fonts, CDNs or network services.

## Reference Intelligence Engine — approved design, not yet implemented
Study [ReelMimic](https://github.com/edenfunf/reelmimic) selectively. Its source demonstrates a reference-analysis → style plan → user approval → parallel shot production → independent review → final critique workflow. It also provides a useful direction for measurable reference fingerprints across camera movement, rhythm, look, tension/peaks and frame summaries.

**Adopt:** local reference analysis, shot segmentation, camera/motion and look summaries, audio/beat cues, versioned fingerprints, storyboard-to-reference shot mapping, approval-first planning, file-contract-driven resumable stages, isolated parallel shot work, fresh-context reviewers and before/after evidence for fixes.

**Do not adopt wholesale:** ReelMimic's app/server as a second orchestrator, its 2D-only renderer collection, or its default agent permission configuration. Keep our existing HyperFrames + GSAP, selective Remotion, Blender + Three.js and FFmpeg responsibilities. Treat similarity scores as advisory until validated against human-labelled clips.

**Adoption boundary:** the inspected upstream revision includes yt-dlp in its reference-ingestion path. This is not a project-level prohibition: internet access and yt-dlp may be used when they materially help research or acquire reference footage. Audit the command, source, rights and network behaviour; do not inherit its documented `danger-full-access` Codex default. Reference footage is for analysis only and must never be inserted into final renders. Upstream uses the user's Claude Code/Codex account for inference; local execution is not equivalent to fully local inference.

Target flow: **local reference file → versioned analysis report + contact sheets → reference fingerprint → storyboard with reference-shot mapping → user approval → our existing renderers → shot QA and final comparison.** Cache by source hash, analysis version and settings. Preserve reference provenance and rights. See [ReelMimic Adoption Assessment](REELMIMIC_ADOPTION.md) for source findings, staged implementation and acceptance criteria.

## Animation Recipe Engine — approved design, not yet implemented
Selectively port six recipe families from [artemnovitckii/claude-animation-skills](https://github.com/artemnovitckii/claude-animation-skills): 3D explainer, stick figure, minimal graphics, map route, exploded breakdown and animated graph. These are scene-design patterns, not a new rendering runtime. HyperFrames + GSAP remain primary; Three.js/Blender are used only where justified. Do not run its macOS/Linux Bash setup unchanged on Windows.

Target contract: **agent selects recipe → versioned JSON scene spec → deterministic local renderer → contact sheet + QA report → agent reviews exceptions.** Schema should capture recipe/version, canvas, duration/FPS, objects, timing, camera, labels, assets, animation parameters, narration anchors and validation rules. Cache using stable inputs, recipe and renderer versions, and relevant settings.

Pilot one graph recipe and one breakdown or map-route recipe. Compare with hand-authored scenes for quality, determinism, render time, dependencies and token usage. Do not promote until Windows tests and human review pass.

## Code-review skill — advisory pilot
Evaluate [kyy-logs/code-review-skill](https://github.com/kyy-logs/code-review-skill) at a pinned revision for meaningful/high-risk diffs in both agent workflows, not every trivial edit. Its four fresh-context probes cover behaviour, tests, repository rules and impact. Treat results as advisory: probes are not independent models or human adjudication. A pass is not proof and must never auto-merge. Retain tests, CI, security review and human approval.

Test a small diff, multi-file refactor and intentionally seeded defect. Record misses, false positives, reproducibility, host compatibility and invocation cost.

## Storyboard QA — independently implement useful patterns
Borrow useful patterns from [konlu/story-studio](https://github.com/konlu/story-studio): narration/audio-first timing, persistent visual references, narration-anchored shot rows and semantic script-to-shot checks. Independently implement these patterns with local transcription. Do not copy code or corpus until the CC BY-NC-SA root licence versus MIT README wording is resolved. Do not use paid TTS or hosted image generation. Treat sample scripts as inspiration, not verified facts.

## Other evaluated skills
- [Ray Sticker Shop](https://github.com/imraywang/ray-sticker-shop): separate potential sticker-pack workflow, not a video-studio dependency; not offline-first.
- [Medical Paper Skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills): exclude; unrelated medical-academic workflow with a PolyForm Noncommercial licence.

## Promotion gates
| Pilot | Evidence required |
|---|---|
| Reference Intelligence | Windows analysis of local or intentionally acquired reference files, transparent network/source handling, versioned/cacheable reports, useful shot/camera/rhythm/look metrics, human-validated comparisons |
| Animation recipes | Windows setup, offline render after approved downloads, deterministic outputs, contact sheets and human approval |
| Code review | Pinned revision, seeded-defect test, measured misses/false positives, host compatibility; advisory only |
| Storyboard QA | Local transcription, correct timeline anchors, visual consistency, semantic usefulness and repeatable outputs |

Record revision, environment, commands, test media, outputs, limitations and promotion decision. A smoke test is not editorial-quality proof.

## Final-video visual invariant
Every visual element in the finished video must be authored/generated through code in our production pipeline: SVG, Canvas, WebGL, procedural graphics, charts, typography, animation, simulations and 3D geometry are valid. **Never use stock/static photos, downloaded video clips, generic downloaded B-roll in the final render.**

Reference videos, web pages, screenshots and downloaded examples may be analysed for style, pacing, camera language, composition and technique, subject to rights and provenance. They are references, not final assets.

## Non-negotiable constraints
- Offline-first and free/open-source by default.
- No paid inference APIs, hosted generation credits, cloud uploads or subscriptions by default.
- **No ComfyUI.** Internet access and yt-dlp are permitted for research/reference acquisition when useful; downloaded media remains reference-only and is prohibited from final renders.
- No silent renderer replacement or bulk skill installation.
- No remote runtime dependency in final renders.
- Respect code, model, font, image, music, sound and 3D-asset licences separately.
- Preserve asset provenance and rights evidence.
- No uploading media, scripts, voice samples or private content without explicit approval.
- Human review remains mandatory for factual accuracy, editorial judgement and final quality.
- Never describe planned helpers, pilots or integrations as installed or validated until tested.

## Change control
When a decision changes, update this playbook, affected agent handovers, architecture, roadmap, token policy and changelog together. Prefer reviewable commits. Never weaken permanent constraints without explicit approval.


## v5.0 — Two-channel storytelling production (approved blueprint)

Canonical specification: [Two-Channel Blueprint](TWO_CHANNEL_STUDIO_BLUEPRINT.md). Benchmarks: [His Story](https://www.youtube.com/@hisytstory) and [Her Story](https://www.youtube.com/@herytstory). These channels define observable quality benchmarks only; do not copy names, characters, scripts, exact frames, dialogue, logos, distinctive compositions or music.

### Mandatory sequence
1. Research both channels and select representative/top-performing Shorts and long-form using transparent public metrics.
2. Analyse selected videos shot by shot; create timestamped shot records, contact sheets, channel style fingerprints and thumbnail-layout maps.
3. Translate observations into original techniques and quality targets; isolate reference assets.
4. Design original male-led and female-led protagonist candidates in Blender. Produce turnarounds, facial expressions, body-action samples and playable animation pilots.
5. Iterate with user feedback and explicitly freeze selected versions. Frozen assets are immutable; revisions branch.
6. Audition multiple local voice options per channel; user selects and freezes exact profiles, model/weights and settings.
7. Curate original channel names, check YouTube name/handle conflicts and similar use, then user reserves the final handle after immediate recheck.
8. Create original icons, banners, typography, colour system and thumbnail grammar using approved characters.
9. Generate 2–4x candidate ideas for 30–60 desired approvals. User accepts/rejects/revises/shortlists and locks calendar.
10. Ask whether the next production batch is one or two weeks and how much laptop time is available.
11. Run resumable local batches with resource-bounded parallelism; serialize heavy Blender GPU renders until benchmarks justify concurrency.
12. Deliver videos and upload packages; user uploads/schedules manually.

### Reference acquisition and originality
Internet research and yt-dlp are allowed where lawful and consistent with platform terms. Download only with rights/permission or lawful basis; otherwise inspect public player/metadata or authorized copies. Never bypass DRM, authentication or access controls. Reference footage is analysis-only. Match production qualities, not protected expressive details. See [Reference Reverse Engineering](REFERENCE_REVERSE_ENGINEERING.md).

### Character and voice identity locks
Each episode pins exact character, rig, wardrobe, animation and voice profile versions. Never silently change identity. See [Character DNA](CHARACTER_DNA_AND_LOCKS.md) and [Voice Identity](VOICE_IDENTITY_SYSTEM.md).

### Voicebox and Suno
Evaluate [Jamie Pine Voicebox](https://github.com/jamiepine/voicebox) as a local voice-studio candidate; it is not yet selected or installed. Review each model/weight licence separately. Chatterbox and IndicF5 remain candidates. The user's existing Suno subscription is a narrow approved composition exception; archive song ID, prompt, generation/download dates, plan and licence evidence. This does not authorize other paid services or hosted inference.

### Blender MCP security
Evaluate [MCP for Blender](https://github.com/ahujasid/mcp-for-blender) at a pinned revision. Review install script, dependencies, telemetry and permissions; disable telemetry, use safe mode, bind only to localhost and never expose the unauthenticated socket. Blender Python/CLI remains the deterministic production path.

### Content board and local scheduler
Generate a larger candidate pool, support accept/reject/revise/shortlist/defer/merge and lock a 30–60 idea backlog. Weekly/two-week batch selection is user-approved. Durable local job state, pause/resume/cancel, restart recovery and GPU-aware concurrency are mandatory. Publishing remains manual. See [Content Board](CONTENT_BOARD_AND_BATCH_OPERATIONS.md), [Operations](PRODUCTION_OPERATIONS.md) and [Acceptance Tests](IMPLEMENTATION_ACCEPTANCE_TESTS.md).


## v5.2 — Remotion + HyperFrames first-class engines; Cinetic specialist skill

### Renderer decision (supersedes earlier selective-Remotion wording)
Remotion and HyperFrames + GSAP are co-equal first-class 2D/motion production engines. Choose per scene/project based on composition needs, deterministic behaviour, rendering performance, maintainability and reuse; do not force every shot through one renderer.

- **Remotion:** full React composition system for component-driven scenes, data-driven visuals, reusable scene systems, complex layout/state, launch films and update videos. It is no longer restricted to occasional specialist use.
- **HyperFrames + GSAP:** first-class timeline/motion engine for precise beat-based animation, editorial sequencing and web-native motion compositions.
- **Blender + Python:** original 3D characters, rigs, environments, camera/lighting and cinematic shots.
- **Three.js:** specialist interactive/realtime 3D scenes where justified.
- **FFmpeg + ffprobe:** media inspection, audio/video assembly, encoding and final technical QA.

A scene may combine engines only through explicit, tested interchange contracts. Prefer a renderer-native scene where possible; avoid needless cross-renderer handoffs. Both renderers must honour the final-visual invariant: all final visual content is authored/generated in code; no stock photos, downloaded video or generic B-roll.

### Remotion licence and operating boundary
The project owner/operator is currently one individual. Remotion's official Free License covers individuals for personal or commercial video creation, including automation, without registration or payment, subject to its terms. It includes full functionality. Remotion is source-available under a proprietary licence, not OSI open source. Recheck the official [License FAQ](https://convert.remotion.dev/docs/license/faq), [Terms](https://www.remotion.dev/docs/terms) and [LICENSE](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md) before any material change in project ownership, team composition or deployment.

Do not confuse this personal studio with employer-owned work. If a future employer/client or other party jointly owns, controls or directly operates the same Remotion project, reassess the involved-party/headcount and project-ownership provisions before use. Delivering only a finished MP4 to a client who never accesses or operates the Remotion project is treated differently in the official terms. This is a licensing checkpoint, not a reason to restrict the present solo workflow.

### Cinetic — approved for controlled pilot, not installed
Source: [Leonxlnx/cinetic](https://github.com/Leonxlnx/cinetic). Cinetic is an agent skill for code-first launch films, product/update videos, teasers and social cut-downs. Its v1.5 line adds a 34-scene Remotion starter library. Cinetic itself is MIT-licensed; bundled scene assets, music and other dependencies require their own review.

**Adopt as an optional specialist creative-direction/finishing workflow**, not as a replacement orchestrator, renderer, or our storytelling engine. Useful patterns to evaluate: brief/script-first planning, beat grids, scene selection, motion/sound QA, contact sheets, critic passes, sync checks and delivery manifests. It is especially relevant to channel launch films, channel identity reveals, season/series announcements, production updates and trailers. It is not the default engine for full narrative episodes.

**Integration order:** Remotion first for the Cinetic pilot, with HyperFrames retained as an equal first-class alternative and possible target for independently adapted scene ideas. Do not assume Cinetic's 34 Remotion scenes run in HyperFrames. Port only after a separate implementation and quality test. Curate deterministic scene selection; do not accept random template assembly that erases the two channels' distinct visual identities.

**Hard constraints:** Windows support is less proven than Linux; use Git Bash where required and validate on the actual Windows machine. Verify prerequisites at the pinned Cinetic revision (Node 22+, Python 3.11+, FFmpeg 6+, Chromium, Bash and documented earshot companion). Do not install until preflight and licence/dependency/network review are complete. Cinetic's documented music path requires licensed human-made instrumental music and excludes AI-generated tracks; keep this separate from the user's narrow approved Suno composition exception. Disable/exclude downloaded stock imagery/marks/B-roll from final renders. Motion blur can materially increase render time; benchmark before enabling broadly. Final render must be reproducible offline after approved dependencies/assets are present. Test one agent workflow first; do not install into both Claude and Codex automatically.

### Cinetic pilot acceptance
Create one 20–30 second original launch film for a channel concept using a fixed brief and approved brand/character assets. Compare Cinetic + Remotion with a hand-directed Remotion composition; add a HyperFrames equivalent if it helps isolate renderer value. Measure Windows setup reliability, reproducibility, scene-editability, render time, peak RAM/VRAM, motion quality, audio sync, QA findings, manual corrections and originality. Inspect contact sheets and watch the complete video. Promote only if Cinetic adds measurable value beyond direct Remotion authoring.

Detailed constraints, preflight and test matrix: [Cinetic Adoption Assessment](CINETIC_ADOPTION.md).

## v5.4 — Cinematic Skill specialist pilot

Read [Cinematic Skill Adoption Assessment](CINEMATIC_SKILL_ADOPTION.md) before using this candidate. It is a Python + Skia narration-led documentary/explainer workflow with drawn visual boards, camera movement, subtitle/audio/SFX and QA support. Status is **controlled pilot approved; not installed, not Windows-validated and not production-ready**.

Use it for engineering/science/history explainers, maps, diagrams, evidence-board sequences and selected Shorts when its drawn 2D camera language is a better fit than hand-authoring in Remotion/HyperFrames. Do not use it for rigged character performance or complex 3D; Blender remains the route. Remotion and HyperFrames remain co-equal first-class motion engines.

### Narration beat contract
Standardise only a small renderer-neutral timing contract: `beat_id`, `shot_id`, `vo_start`, `vo_end`, `narration_text`, `visual_intent`, `camera_path`, `transition`, `provenance`, `approval_state`. Local transcription/timing and deterministic mapping create/update this data; agents are used for creative intent and ambiguous alignment, not one call per line/frame. Each renderer maps this contract into its own native scene format. Preserve original VO and user-approved local narrator profile.

### Hard visual and operational boundaries
The upstream archive/photo/scanned-document/AI-still paths are excluded from final renders. Final visuals must be code-authored/generated only: Skia geometry, paths, maps, charts, diagrams, typography, annotations and procedural textures. No downloaded photos, stock imagery, scanned pages, downloaded video, generic B-roll or AI-generated raster stills. Reference footage remains isolated analysis-only. Use existing local TTS; no hosted TTS, paid inference or cloud uploads. Review dependencies/scripts/network/filesystem access, pin a revision and validate Windows/Git Bash, fonts, Skia, FFmpeg, offline operation and resource usage before installation.

### Pilot gate
Produce one 60–90 second original engineering/science explainer with code-generated visuals only, approved local narration and full subtitles/audio QA. Create contact sheets/animatic before full render. Compare a representative section with Remotion or HyperFrames. Record pinned versions, render time, peak memory, reproducibility, correction time, Windows failures and human quality judgement. Promote only for the documentary/explainer niche if evidence shows a durable advantage.
