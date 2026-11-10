# Cinematic Skill — Adoption Assessment

**Decision: controlled specialist-renderer pilot approved. Installation: not performed. Production validation: pending.**  
Upstream: [Moh4696/cinematic-skill](https://github.com/Moh4696/cinematic-skill) · [MIT licence](https://github.com/Moh4696/cinematic-skill/blob/main/LICENSE) · [Skill instructions](https://github.com/Moh4696/cinematic-skill/tree/main/skills/cinematic-film) · [Renderer](https://github.com/Moh4696/cinematic-skill/blob/main/skills/cinematic-film/scripts/render.py) · [Requirements](https://github.com/Moh4696/cinematic-skill/blob/main/requirements.txt)

## Executive decision

Cinematic Skill is a useful, distinct addition to the studio: a narration-led documentary/explainer workflow built around Python + Skia drawing and virtual-camera movement. It can compose typography, maps, diagrams, cards, annotations and other drawn visual elements into a camera-travel sequence, then render and finish with FFmpeg. It plans narration beats and visual timing, and includes subtitle/audio/SFX and contact-sheet/QA steps.

Adopt it as an **optional specialist renderer and workflow**, not a new orchestration layer and not a replacement for Remotion, HyperFrames + GSAP, Blender or FFmpeg. Its strongest fit is history, science, engineering and data-led mini-documentaries, explainers, evidence-board sequences and selected Shorts. It is not the preferred engine for original rigged character acting, expressive performance or complex 3D worlds.

## What we can reuse

- Narration-first screenplay/shot planning with one clear visual idea per line or beat.
- Explicit voiceover-to-shot timing and camera-movement planning.
- A Skia-based 2D drawing surface with interpolated virtual-camera motion.
- Maps/routes, labels, cards, annotations, typography and diagram composition.
- Local render orchestration, subtitles/SRT, sound-effect layers, audio mix, contact sheets and visual QA.
- A possible fast path for documentary sequences that would be slower to hand-author in a full React composition.

**Cross-engine design principle:** narration timing and beat planning are reusable production capabilities, not properties that should be trapped inside Skia. Keep a renderer-neutral beat/shot contract that can feed Cinematic Skill, Remotion, HyperFrames or Blender. Each renderer should consume only the scene data it needs.

## Non-negotiable studio adaptations

The upstream workflow can use archive photographs, scanned documents, downloaded/public-domain imagery and optional AI-generated stills. That default asset model conflicts with this studio's final-visual policy. Therefore:

1. Final output must contain only code-authored/generated visuals: Skia paths/shapes, procedural textures, original diagrams, charts, maps, typography, annotations and other deterministic graphics.
2. Do not use downloaded photos, scanned documents, stock imagery, downloaded video, generic B-roll or AI-generated raster stills in final renders—even when described as public domain.
3. Reference media may be used in a separate analysis-only workspace with provenance; never link it into a final render manifest.
4. Do not use the skill's archive/download/asset-discovery path for final-video assets. Do not let archive inputs silently become scene backgrounds.
5. Original brand assets may be used only when approved and their provenance/licence is recorded. Prefer reconstructing the intended information as original diagrams rather than embedding source images.
6. Use the studio's approved local TTS/narrator profiles. The skill's scratch voice examples are setup conveniences, not our voice-identity system. No reference narrator imitation or unapproved voice cloning.
7. No hosted TTS, image generation, paid API, cloud upload or remote runtime dependency in the default path.
8. Keep music/SFX provenance and licence checks separate. Generated or synthesised effects must be reviewed; no unlicensed copied sounds.

## Position in the production stack

| Layer | Responsibility | Status |
|---|---|---|
| Claude Code or Codex | Creative direction, beat/shot plan, exceptions and review | Existing orchestration |
| Narration beat contract | Renderer-neutral VO timing, visual intent, shot IDs and transitions | Design to standardise |
| Cinematic Skill (Python + Skia) | Optional 2D documentary/explainer sequences with camera travel | Controlled pilot; not installed |
| Remotion | First-class React/component/data compositions | First-class |
| HyperFrames + GSAP | First-class timeline/beat-driven motion | First-class |
| Blender + Python | Original 3D characters, rigs, environments and cinematic shots | Primary 3D |
| Three.js | Specialist realtime/procedural 3D | Specialist |
| FFmpeg + ffprobe | Audio/video assembly, encoding and technical QA | Delivery foundation |

Do not chain renderers without a clear creative or technical reason. A Cinematic Skill scene may be exported as a clean intermediate and assembled by FFmpeg; it does not automatically become a Remotion or HyperFrames scene.

## Setup and compatibility preflight

The repository is a skill, not a standalone polished desktop application. Its workflow uses Python/Skia and FFmpeg; the documented installer is:

```bash
npx skills add Moh4696/cinematic-skill
```

Before running it, pin and inspect a specific upstream commit. The current setup documentation indicates a modern Node runtime (Node 22+; the project notes 22.20+ for the installer), Python 3.11+, FFmpeg 6+, Bash/Git Bash and Chromium-related tooling. Python dependencies include Skia and supporting numeric/image libraries. Treat exact versions as revision-dependent and verify against the pinned revision rather than assuming they remain stable.

Windows is not yet validated. Test Git Bash invocation, paths containing spaces/non-ASCII, font discovery, Skia wheels, FFmpeg resolution, subprocess handling, multiprocessing, Chromium dependencies (if used), output paths and cleanup. Separate one-time setup downloads from offline runtime. Font downloads and archive discovery are not required for our code-only pilot; use legally installed local fonts and record their licences.

Do not install globally or into both Claude and Codex before the isolated pilot. Review scripts, dependency licences, network calls, filesystem scope and subprocess behaviour first. Install into a dedicated project/workspace or one agent environment only after the preflight passes.

## Pilot plan

**Test film:** one 60–90 second original engineering/science explainer. Use only procedural diagrams, labels, charts, maps where relevant, typography and original vector/Skia illustrations. Use an approved local narrator profile and a fixed script. No photos, downloaded stills, AI raster images or downloaded video.

1. Pin upstream commit and archive the source/review record.
2. Run dependency, licence, script, network and Windows compatibility review.
3. Create a renderer-neutral narration beat sheet: beat ID, VO start/end, narration text, visual intent, camera path, transition, source/provenance and review state.
4. Adapt the beat sheet into Cinematic Skill's own scene representation.
5. Render a low-resolution animatic/contact sheet first; human-approve composition and timing.
6. Render 1080p locally; generate subtitles and SFX/audio mix only from approved local/cleared sources.
7. Export a manifest proving each visual is code-generated and no archive/photo/video asset is referenced.
8. Watch the full render and inspect audio, subtitles, continuity, camera easing, text legibility and factual accuracy.
9. Build the same representative sequence in Remotion or HyperFrames as a fair comparator where practical.

## Acceptance criteria

- [ ] Pinned revision, MIT skill licence and all dependency/asset/font licences recorded.
- [ ] No unreviewed network calls, telemetry, hosted inference or uploads in execution path.
- [ ] Windows setup succeeds on the actual target machine; failures and workarounds documented.
- [ ] Offline render succeeds after approved dependencies/fonts are installed.
- [ ] All visual assets resolve to original code-generated scene data; prohibited raster/photo/video assets are rejected.
- [ ] Narration timing is stable; edits/cuts do not desynchronise later beats.
- [ ] Camera motion is smooth and intentional; no clipping, unreadable typography or accidental blank frames.
- [ ] Subtitles, SFX and audio mix pass full-playback review.
- [ ] Render time, peak RAM/VRAM, CPU/GPU utilisation, failure recovery and output size are recorded.
- [ ] Human correction time and creative quality are compared with Remotion/HyperFrames.
- [ ] Re-running the same inputs produces acceptably reproducible output.
- [ ] The renderer-neutral beat contract is useful to at least one other engine, or its abstraction is kept deliberately small.

**Promotion rule:** keep as a specialist pilot unless the evidence demonstrates a repeatable quality or speed advantage for documentary/explainer sequences. Do not promote to a first-class general-purpose renderer merely because the sample film succeeds.

## Known limitations and cautions

- Author-reported render-time examples are not independent benchmarks; measure on the actual Windows machine.
- The Skia approach is strongest for drawn 2D boards and camera movement, not expressive 3D character performance.
- A renderer-neutral beat sheet should not become an overengineered universal scene schema; standardise only timing, IDs, intent and provenance.
- Initial setup may need internet for packages/fonts, but the target production run must not depend on online asset fetching.
- A clean code-generated image is not automatically an original story; editorial originality and fact-checking remain human approval gates.

## Sources

- [Repository and README](https://github.com/Moh4696/cinematic-skill)
- [Skill workflow](https://github.com/Moh4696/cinematic-skill/tree/main/skills/cinematic-film)
- [Renderer implementation](https://github.com/Moh4696/cinematic-skill/blob/main/skills/cinematic-film/scripts/render.py)
- [Dependency list](https://github.com/Moh4696/cinematic-skill/blob/main/requirements.txt)

This document records a reviewed adoption decision. It does **not** mean the skill has been installed, executed, benchmarked or production-validated.
