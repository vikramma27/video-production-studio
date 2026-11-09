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
