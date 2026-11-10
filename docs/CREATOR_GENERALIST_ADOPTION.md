# Creator Generalist Adoption Assessment — v5.5

**Upstream:** [codepawl/creator-generalist](https://github.com/codepawl/creator-generalist)
**Licence:** MIT for this skill-pack repository; third-party tools, models, fonts, data and assets retain their own licences.
**Decision:** Selective adoption approved for a controlled, isolated skill pilot.
**Runtime status:** Documentation and architecture integration only. Not installed, pinned, executed, Windows-tested or production-validated.
**Scope:** 3D Generalist + selected craft skills, and 2D Generalist for code-generated educational graphics. No wholesale plugin installation.

## Executive decision

Creator Generalist is a broad agent skill pack, not a newly trained model or a renderer. It packages production instructions, reference material, helper scripts and tool recipes so existing agents can orchestrate 2D/3D work. Its strongest value to this studio is craft guidance for Blender character production, rigging, animation, cutaways, environments, maps, charts and editorial motion graphics.

Adopt it as a **specialist craft layer** underneath the existing studio orchestration and renderer architecture. It must not become a second project orchestrator, a new mandatory renderer, or a replacement for our own character DNA, voice, brand, content and approval systems.

## Repository review

Reviewed the upstream README, INSTALL.md, AGENTS.md and representative main/craft skill files on 2026-11-10. The published pack includes four plugin groups:

| Upstream group | Studio decision | Reason |
|---|---|---|
| 3D Generalist | Controlled pilot | Strong fit for Blender modelling, rigs, acting, cutaways, environments, camera and lighting. |
| 2D Generalist | Controlled pilot, filtered | Strong fit for maps, charts, timelines, diagrams and editorial motion; exclude photo-led modes and style imitation. |
| Watch Video | Study methods; do not install in first pilot | Frame sheets, transcripts and sound timelines may help reference analysis, but its acquisition/tooling paths need separate review and are not needed to test the craft layer. |
| Design Sound | Do not install | Includes web/ElevenLabs fetching and model-based foley paths; overlaps our separate local-first audio direction and may require substantial GPU resources. |

Useful craft skills include model-characters, sculpt-models, animate-characters, rig-characters, use-3d-software, draw-and-paint-art, paint-stylized-backgrounds and edit-video. The 3D/2D generalists act as the higher-level task routers; craft skills provide narrower techniques.

Upstream describes modes for cutaway, story, world, character and asset production; 2D map, chart-timeline, design and archival-collage work; and video/audio analysis. Its examples demonstrate the intended workflows, but README examples are not independent quality benchmarks.

## Where it fits in our architecture

| Existing component | Responsibility after adoption |
|---|---|
| Claude Code / Codex | Creative direction, task planning, ambiguity, exception diagnosis and approval requests. |
| Creator Generalist skills | Optional craft knowledge and workflow recipes for selected 2D/3D tasks. |
| Blender + Python | Primary original 3D modelling, character, rig, environment, lighting and render engine. |
| Remotion | First-class React composition and data-driven motion engine. |
| HyperFrames + GSAP | First-class timeline/beat-driven motion engine. |
| Three.js | Specialist realtime/interactive 3D, not a default additional renderer. |
| Cinematic Skill | Separate optional Python + Skia narration-led explainer pilot. |
| Cinetic | Separate optional Remotion launch-film/update-video pilot. |
| FFmpeg / ffprobe | Assembly, transcode, probing and delivery QA. |

Creator Generalist supplies instructions and recipes; it does not replace the renderers. Do not add 67.js as a first-class renderer during this pilot. If an upstream skill suggests a renderer/tool not already approved, the agent must explain the specific benefit and request approval before adding it.

## Non-negotiable studio policy overrides

These rules take precedence over upstream skill instructions and examples:

1. **Code-generated final visuals only.** Every final visual must be authored/generated in our production pipeline: procedural geometry, SVG, Canvas/WebGL, charts, typography, maps drawn from approved vector/geospatial data, Blender geometry/materials, animation and simulations.
2. **No photographic or downloaded final assets.** Do not put downloaded photographs, scanned documents, stock images, downloaded video, generic B-roll, AI-generated raster stills or pre-rendered third-party scene assets into final renders. Reference footage and stills are analysis-only and isolated from production manifests.
3. **Asset sourcing is not inherited.** Upstream's preference for CC0/CC BY scans, Poly Haven, ambientCG, Sketchfab, BlenderKit or Quaternius does not grant blanket permission for this studio. For the pilot, build assets procedurally or from original studio-authored geometry. Any future exception requires explicit user approval, rights review and a recorded provenance entry.
4. **No photo-led 2D modes.** Do not use the `photos` mode. Use archival-collage only if recreated entirely with original typography, shapes, vector elements and procedural texture—never actual archival images or newspaper scans.
5. **Original visual identity.** High-level craft principles may be learned from public examples; do not reproduce another channel's exact compositions, distinctive character designs, logos, scripts, templates or trade dress. Do not ask for a direct clone of a named creator/channel's style.
6. **Local-first and free by default.** Use local Blender, Remotion, HyperFrames, Three.js, FFmpeg and existing local TTS. No hosted TTS, paid generation, ElevenLabs, cloud upload or external inference by default.
7. **No ComfyUI.** Do not add or recommend it.
8. **No unapproved software installation.** Skill files may be staged in an isolated test workspace after source review. Ask before installing system applications, changing machine settings or adding heavyweight dependencies.
9. **Human approval remains mandatory.** Show low-cost previews/contact sheets before expensive renders. Never freeze a character, voice, brand or final creative direction without explicit approval.
10. **Publishing remains manual.** No automatic upload or scheduling.

## Risks and source-review findings

- The repository is new and has limited adoption history; public README demonstrations are not proof of robust output across arbitrary prompts or machines.
- MIT applies to the repository's skill-pack code/text, not automatically to Blender, Resolve, fonts, model weights, data, downloaded assets or every external dependency.
- INSTALL.md lists Blender 4.2+ (5.x preferred), FFmpeg, Node.js 20+ and Python 3.10+ as core toolchain requirements; optional tools include DaVinci Resolve, Krita, Inkscape, GIMP and QGIS. Verify exact per-skill requirements at the pinned revision.
- The upstream install instructions contain an apparent count mismatch: the manual-install section says twelve folders but enumerates thirteen. Do not blindly follow the count; verify each selected skill folder and manifest.
- The upstream `design-sound` group includes web/ElevenLabs fetching and HunyuanVideo-Foley paths; one documented path cites approximately 9 GB VRAM. It is excluded from this pilot.
- The upstream 3D workflow prefers scanned/licensed assets and includes optional asset sourcing. Those paths conflict with our strict final-visual policy unless separately reviewed and approved.
- The upstream 2D skill contains a `photos` mode and archival-collage recipes. These must be disabled/avoided for production output.
- Windows/Git Bash compatibility, dependency installation, Blender version-specific recipes, deterministic behaviour, resource use and offline execution have not yet been tested by this studio.
- The upstream README references 67.js as an additional 3D option. Avoid renderer proliferation until a measured test proves it is necessary.

## Controlled pilot scope

**Install/stage only after audit:**
- `3d-generalist`
- `model-characters`
- `sculpt-models`
- `animate-characters`
- `rig-characters`
- `use-3d-software`
- `2d-generalist`
- `draw-and-paint-art` only for original character/style-frame work
- `edit-video` only for local FFmpeg/Resolve craft guidance, with no media-download workflow
- `paint-stylized-backgrounds` only for original procedural or studio-authored backgrounds

Do not install `watch-video` or `design-sound` in the first pilot. Their ideas can be reviewed separately without introducing their scripts or network paths.

### Three required benchmark tasks

1. **Original character test:** create a studio-owned protagonist from an original brief, with turnaround, mesh, rig, facial expression set, walk cycle and a 10–15 second acting clip. Validate silhouette, deformations, foot contact, hand contact, timing, reproducibility and whether the result remains editable in Blender.
2. **Mechanical cutaway test:** create a code/procedural 3D mechanism (e.g. watermill or pump) with interacting components, cutaway view, camera movement, annotations and local narration timing. Validate physical contacts, causal motion, scene readability and render performance.
3. **2D educational sequence:** create an original vector map/route and true-scale timeline with typography, labels and transitions. Use approved vector/geospatial data only; no map screenshots, satellite imagery, photographs or downloaded visual tiles. Validate data provenance and code-generated output.

Run the first pilot in one agent environment only, preferably an isolated Claude Code test workspace. Do not install globally or into Claude Code and Codex simultaneously. If that environment is unavailable, use a separate Codex workspace; do not duplicate installations.

## Preflight and acceptance gates

### Gate A — pin and audit
- Record exact upstream commit SHA and selected plugin/skill paths.
- Inspect all selected SKILL.md files and referenced scripts before execution.
- Review Python/Node dependencies, subprocess calls, filesystem scope, network requests, telemetry, installers and licence notices.
- Confirm no `yt-dlp`, photo-fetch, web asset-fetch, hosted-generation or paid API path is invoked by the selected tasks.
- Record Blender, Python, Node, FFmpeg, OS and GPU versions; check available disk, RAM and VRAM.

### Gate B — isolated setup
- Stage selected skill files in an isolated test workspace, not the global agent skill directory.
- Run a toolchain audit; do not install missing system software without approval.
- Confirm the agent discovers the intended skills and no excluded plugin is loaded.
- Confirm all outputs stay inside the designated project workspace.

### Gate C — render and quality validation
- Complete all three benchmark tasks with code-generated visuals only.
- Inspect source files, editable scene structure, renders, contact sheets and complete playback.
- Verify character rig/animation checks, contact/foot-slip checks, map/timeline accuracy, narration sync and audio levels where applicable.
- Repeat at least one render from a clean process to test reproducibility and cache correctness.
- Record render time, peak RAM/VRAM, failures, recovery behaviour and manual correction time.
- Compare the same representative shots against direct Blender authoring and the existing Remotion/HyperFrames route where relevant.

### Gate D — promotion decision
- Promote only the individual skills that measurably improve output quality or reduce correction time without violating policy.
- Modify or locally wrap any skill whose upstream defaults conflict with studio policy.
- Reject skills that introduce unneeded dependencies, network access, asset-policy violations or renderer duplication.
- Only after the isolated pilot passes may we consider a wider Claude/Codex rollout.

## Sources

- [Repository](https://github.com/codepawl/creator-generalist)
- [README](https://github.com/codepawl/creator-generalist/blob/main/README.md)
- [INSTALL.md](https://github.com/codepawl/creator-generalist/blob/main/INSTALL.md)
- [AGENTS.md](https://github.com/codepawl/creator-generalist/blob/main/AGENTS.md)
- [3D Generalist skill](https://github.com/codepawl/creator-generalist/blob/main/plugins/3d-generalist/skills/3d-generalist/SKILL.md)
- [2D Generalist skill](https://github.com/codepawl/creator-generalist/blob/main/plugins/2d-generalist/skills/2d-generalist/SKILL.md)
- [MIT licence](https://github.com/codepawl/creator-generalist/blob/main/LICENSE)

## Status

Architecture, adoption decision and pilot gates are documented. The skill pack has **not** been installed, pinned, executed or validated on the user's Windows machine. No character, cutaway or 2D benchmark has been produced. Documentation completion must not be reported as runtime integration.
