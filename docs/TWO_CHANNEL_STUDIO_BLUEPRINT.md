# Two-Channel Storytelling Studio — v5.0 Blueprint

**Status:** Approved direction; implementation pending.  
**Benchmarks:** [His Story](https://www.youtube.com/@hisytstory) · [Her Story](https://www.youtube.com/@herytstory)

## Mission
Build one local-first production system for two independently branded animated storytelling channels. The reference channels establish observable benchmarks for pacing, cinematic staging, character performance, visual readability, emotional clarity, repeatable quality and thumbnail communication. They are not identities to copy.

The studio reverse-engineers production techniques, then creates original characters, scripts, voices, environments, music direction, thumbnails and channel identities. Target comparable or better perceived quality with distinct original expression.

## Locked decisions
- Premium stylized 3D visual quality.
- Both Shorts and long-form.
- Hybrid human/AI workflow with explicit approval gates.
- Blender + Python as primary recurring 3D character/scene/animation engine.
- MCP for Blender as optional agent-facing creative interface; deterministic Blender Python/CLI remains production path.
- Preserve HyperFrames + GSAP, selective Remotion, Three.js, FFmpeg/ffprobe, faster-whisper, Chatterbox/IndicF5 candidates and Upscayl.
- Existing Suno subscription is a narrow music-composition exception. Local Stable Audio 3 / Audio Studio MCP remains an optional effects/ambience/loop specialist subject to licence and hardware checks.
- No ComfyUI.
- Internet and yt-dlp permitted for legitimate research/reference acquisition subject to platform terms, rights and provenance. Never bypass DRM, authentication or access controls.
- Reference media is analysis-only. Final visuals are original code-authored/generated 3D scenes, procedural graphics, animation, typography and geometry. No stock photos, generic downloaded video, reference footage or generic B-roll in final output.
- Publishing is manual/user-controlled in v1.

## Reference-first workflow
1. Resolve canonical channel IDs for the exact URLs above.
2. Collect balanced Shorts and long-form samples: top performers, recent performers, typical performers and varied emotional genres.
3. Rank using transparent public signals: lifetime views, age-normalized velocity, views/hour, recency, format cohort and outlier score where available. Do not infer private retention, CTR or demographics.
4. Review each selected video shot by shot; create contact sheets and timestamped shot records.
5. Measure shot duration, framing, camera movement, composition, character blocking, lighting, palette, facial acting, gestures, transitions, narration/dialogue timing, music/SFX roles and thumbnail layout.
6. Create channel-level style fingerprints and cross-channel comparisons.
7. Translate general techniques into original creative direction; document evidence and confidence.
8. Obtain user approval of benchmark targets before character production.

Initial sample: 20–30 videos per channel, balanced across formats and performance tiers. Expand only when evidence gaps remain.

## Rights and originality
"Same or better look" means matching production qualities—lighting, camera language, staging, animation polish, pacing, emotional readability, consistency and thumbnail clarity—not copying exact frames, scripts, dialogue, character designs, logos, distinctive compositions or music. Acquire/download references only where lawful and consistent with platform terms. If downloading is not authorized, inspect the public player/metadata or an authorized copy. Keep references in an isolated analysis-only workspace and reject them from final render manifests.

## Brand and asset lock sequence
1. Approve both reference benchmark reports.
2. Design original male-led and female-led protagonist candidates.
3. Produce turnarounds, facial expression sheets, body-action tests and playable animation pilots.
4. Iterate until the user explicitly freezes character versions.
5. Audition multiple original/local voice options per channel; user selects and freezes exact profiles.
6. Curate original channel names and check YouTube display-name/handle conflicts and confusing similarity.
7. User reserves final handles after immediate recheck.
8. Create original icons, banners, typography, colour system and thumbnail grammar.
9. Freeze versioned brand bibles and asset manifests.

Frozen versions are immutable. Changes create new candidates and require renewed approval.

## Content planning
For a desired backlog of 30–60 accepted ideas, normally generate 2–4 times as many candidates. Present cards with channel, format, premise, hook, emotional engine, novelty, complexity, duration, dependencies, risks and series potential. Support accept, reject, revise, shortlist, defer, merge duplicates and calendar lock.

After 30–60 ideas are approved, ask whether the next production batch should cover one week or two weeks and how much laptop time is available.

## Local execution
The laptop/workstation is the production host. Provide a visible queue with queued, running, awaiting approval, blocked, failed, paused and complete states. Persist manifests and checkpoints across restarts. Parallelize independent research, script QA, metadata and audio preparation. Serialize or strictly bound heavy Blender GPU renders until measured VRAM/RAM/thermal benchmarks justify concurrency. Provide pause, resume, cancel and stop-after-current-job controls. No always-on cloud worker assumption.

## Delivery
Produce video, thumbnail, captions, title/description suggestions, provenance/licence manifest, QA report and recommended publish slot. The user uploads and schedules manually.

## Source of truth
- [Reference Reverse Engineering](REFERENCE_REVERSE_ENGINEERING.md)
- [Character DNA and Locks](CHARACTER_DNA_AND_LOCKS.md)
- [Voice Identity](VOICE_IDENTITY_SYSTEM.md)
- [Brand Naming and Thumbnails](BRAND_NAMING_AND_THUMBNAILS.md)
- [Content Board and Batch Operations](CONTENT_BOARD_AND_BATCH_OPERATIONS.md)
- [Blender Production Engine](BLENDER_PRODUCTION_ENGINE.md)
- [Production Operations](PRODUCTION_OPERATIONS.md)
- [Acceptance Tests](IMPLEMENTATION_ACCEPTANCE_TESTS.md)

Documentation is not implementation. No capability is production-ready until tested on the target Windows machine.