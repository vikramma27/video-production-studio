# Givemotion — controlled renderer pilot

**Decision:** approved for an isolated, comparative renderer pilot  
**Upstream:** [givemotion/givemotion](https://github.com/givemotion/givemotion)  
**Pinned candidate:** release/tag `v0.1.5` (npm package `givemotion@0.1.5`)  
**Licence:** MIT for the project code; bundled fonts and external runtime components retain their own licences  
**Runtime status:** not installed in the studio, not executed in our Windows environment, not benchmarked by us and not production-validated.

## Executive decision

Givemotion deserves a place in the studio's renderer evaluation because its agent-native loop is unusually close to the workflow we want for procedural motion: an agent authors a composition, launches a local preview, inspects frames and diagnostics, iterates, then renders a deterministic video. Its incremental segment rendering and HTML/CSS/JavaScript authoring make it a strong candidate for the v5.7 Infographic Motion Engine prototype.

This is a **controlled pilot**, not a declaration that Givemotion is better than Remotion or HyperFrames. The upstream project's own benchmark is encouraging but self-reported, small-sample and author-run. We will use identical briefs and local measurements before changing renderer status.

## What it contributes

- A code-first HTML/CSS/JavaScript composition model, with no JSX or separate build step required by its documented workflow.
- A deterministic virtual clock and time-based animation primitives, with preview, frame capture, checks and contact-sheet review.
- Agent-oriented iteration for Claude Code, Codex and other supported coding agents.
- Incremental segment rendering with fingerprints, intended to rerender only changed portions of a composition.
- Kinetic typography, diagrams, charts, captions, camera movement, paths, transitions, audio and video timeline support.
- SVG, Canvas, WebGL and Three.js as possible procedural visual techniques.
- Local MP4 and image/video export paths using a browser runtime and FFmpeg.

Givemotion is an animation authoring/preview/render tool, not a generative-video model and not a replacement for Blender's rigging, character acting, geometry or full 3D environment pipeline.

## Position in our architecture

Givemotion is a **candidate 2D/procedural renderer** and a possible first implementation target for the Infographic Motion Engine. It is not yet a first-class production engine and it does not become a second orchestrator.

- **Remotion:** remains first-class for React/component/data-driven compositions and reusable scene systems.
- **HyperFrames + GSAP:** remains first-class for timeline/beat-driven motion and editorial sequencing.
- **Givemotion:** isolated candidate for agent-native HTML/CSS/JS animation, deterministic preview, visual checks and incremental rendering.
- **Blender + Python:** remains the primary path for original 3D characters, rigging, animation, environments, camera and cinematic shots.
- **Three.js:** specialist real-time/procedural 3D when it is the better fit.
- **FFmpeg / ffprobe:** media assembly, encoding and technical QA.
- **Cinematic Skill:** optional Python + Skia documentary/explainer pilot; independent of this renderer test.
- **Infographic Motion Engine:** remains renderer-neutral. Its Channel DNA, Episode DNA and narration-beat contract must map into each engine's native format rather than force a universal renderer API.

Do not add Givemotion to the production engine selector or route routine episodes to it until the pilot has passed and the user explicitly approves promotion.

## Upstream evidence and benchmark caution

The upstream repository reports comparisons against Remotion and HyperFrames across its own experiment rounds. Its recent round reports favourable blind-judge scores and faster render times for selected briefs, but the study is not independent: sample sizes are small, the author maintains the project, the skill was tuned between rounds, AI judges assessed motion strips, and results vary by workload and hardware. The repository also reports cases where Givemotion was slower, especially for heavier 3D work.

Treat these numbers as a reason to test, not proof of superiority. We will not copy upstream headline scores into our project claims or use them as our acceptance threshold. Record our own exact versions, machine, prompts, outputs, timings and review notes.

## Windows, dependencies and operational preflight

The reviewed upstream documentation describes Node.js 20+, FFmpeg and Chrome/Chromium as prerequisites. It does not establish that our Windows setup is production-ready.

Before installation or execution:

1. Pin the exact upstream release/tag and verify its source and package contents.
2. Review CLI scripts, install behaviour, subprocess calls, filesystem access, browser launch flags and any automatic browser installation.
3. Verify Node, FFmpeg and Chromium versions and paths on the target Windows machine; test from the intended shell.
4. Use a disposable project directory with no credentials, personal files, production assets or unrelated workspaces mounted.
5. Audit bundled fonts and every optional dependency/resource separately; the MIT licence does not relicense those components.
6. Record all environment variables and generated files; no silent global installation or changes to either agent's general configuration.
7. Do not auto-install missing packages during the pilot. Make every dependency explicit and reproducible.

## Security and offline rules

Givemotion compositions are executable HTML/JavaScript. A malicious or compromised composition can run browser-side code and attempt to access resources available to the rendering environment. The upstream security guidance recommends treating compositions as trusted code and isolating execution.

- Run only compositions authored by us or reviewed before execution.
- Use a disposable VM/container or equivalent restricted workspace; do not expose secrets, tokens, SSH keys, browser profiles or production credentials.
- Block outbound network access during rendering. Loopback preview access may be enabled only where required.
- Do not allow external fonts, scripts, images, Lottie CDN resources, remote media or analytics. Vendor approved dependencies locally and record their licences.
- Verify offline operation after setup by rendering with network access disabled and inspecting logs/network attempts.
- Do not point the renderer at arbitrary downloaded HTML or untrusted project folders.

## Non-negotiable studio visual and production policy

Final visuals must remain original and code-generated. Permitted techniques include original SVG, HTML/CSS, Canvas/WebGL, procedural textures, charts, typography, maps from approved vector/geospatial data, simulations and original Three.js geometry.

The following remain prohibited in final renders:

- Downloaded photographs, scans, stock imagery, downloaded video and generic B-roll.
- AI-generated raster stills or generated image plates.
- Reference footage or stills used as production assets; references remain analysis-only.
- Unlicensed or unreviewed fonts, music, sound effects, models or other third-party assets.
- Hosted TTS, paid generation APIs, cloud uploads or remote asset dependencies by default.

Use local TTS and approved local audio assets. Preserve narration beat metadata from the shared renderer-neutral contract: `beat_id`, `shot_id`, `vo_start`, `vo_end`, `narration_text`, `visual_intent`, `camera_path`, `transition`, `provenance`, `approval_state`.

## Comparative pilot plan

### Benchmark A — 60-second engineering infographic

Use the existing v5.7 benchmark: an original centrifugal-pump explainer. Build the same approved script, voice track, beat sheet, duration, output resolution and visual brief in:

1. Givemotion.
2. Remotion.
3. HyperFrames + GSAP.

Use procedural vector pump, impeller, flow arrows, pressure/velocity labels, section views and typography. Do not use raster image plates. Keep Blender out of this first 2D comparison unless a clearly isolated 3D insert is needed.

### Benchmark B — 30-second data-led motion story

Use an identical small dataset, chart grammar, typography and narration in all three engines. Evaluate labels, axis clarity, transitions, visual hierarchy and editability.

### Benchmark C — small character-motion probe

Create a simple original vector puppet with a few expressions and a limited arm/head action. This is a capability probe, not a replacement for the Blender character pipeline. Compare correction effort and whether the result becomes brittle as acting complexity increases.

### Record for every run

- Exact release/tag, source hash, Node/FFmpeg/Chromium versions and machine specification.
- Agent/model and instruction set used, with approximate token/API spend where available.
- Time to first preview, total authoring/correction time and final render time.
- Peak RAM/VRAM, CPU/GPU utilisation and worker count.
- Determinism: repeat the same render and compare frame/video hashes or a defined visual-difference metric.
- Preview accuracy, frame-accurate seeking, segment-cache correctness and invalidation behaviour.
- Visual quality, timing, typography, transitions, motion smoothness and full-playback QA.
- Audio/narration synchronisation, subtitle accuracy and local-only audio handling.
- Windows reliability, offline reproducibility, recovery after interruption and error clarity.
- Human correction count, editability and maintainability of the composition.
- Any network attempt, external resource, unexpected file access or licence ambiguity.

Do not maximise worker count before profiling. Start serially; increase concurrency only after measured memory headroom. Motion blur and high-resolution subframes must be measured rather than assumed to be cheap.

## Acceptance gates

Givemotion can be considered for promotion only if all gates pass:

- [ ] Pinned source and complete dependency/licence review.
- [ ] Windows install, preview and render succeed in the isolated workspace.
- [ ] Offline render succeeds with outbound network blocked and no remote resources.
- [ ] Security review finds no unexpected access beyond the sandbox contract.
- [ ] All final visuals are original and procedural; provenance is recorded.
- [ ] Benchmark A and B are completed in Givemotion, Remotion and HyperFrames under equivalent conditions.
- [ ] Benchmark C clarifies where vector puppets stop being useful and Blender should take over.
- [ ] Determinism, segment invalidation, checkpoint/recovery and complete playback QA pass.
- [ ] RAM/VRAM, render time, authoring time and correction effort are recorded.
- [ ] The user reviews the outputs and explicitly approves any change to production status.

Until then, status remains **approved for controlled pilot; not installed, not executed, not benchmarked by us, not production-validated**.

## Upstream references

- [Repository](https://github.com/givemotion/givemotion)
- [README and workflow](https://github.com/givemotion/givemotion/blob/v0.1.5/README.md)
- [Package manifest](https://github.com/givemotion/givemotion/blob/v0.1.5/package.json)
- [Agent skill](https://github.com/givemotion/givemotion/blob/v0.1.5/skills/givemotion/SKILL.md)
- [Security guidance](https://github.com/givemotion/givemotion/blob/v0.1.5/SECURITY.md)
- [Third-party notices](https://github.com/givemotion/givemotion/blob/v0.1.5/THIRD_PARTY_NOTICES.md)
- [Upstream experiment notes](https://github.com/givemotion/givemotion/blob/v0.1.5/docs/experiments/2026-11-rounds-7-8.md)
