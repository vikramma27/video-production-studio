# VIDEO PRODUCTION STUDIO — v5.3 direction

### Frame / Foundry — an editorial production atlas for an original, code-first animation studio.

The landing page is a film-atelier front door: explore two original channel worlds, inspect the production engines, understand the Cinetic, Cinematic Skill and Creator Generalist pilots and navigate the full studio blueprint.

**Claude Code / Codex think. Local tools execute. Every repeatable task becomes automation.**

[Enter Story Foundry](https://vikramma27.github.io/video-production-studio/) · [Landing Experience](docs/LANDING_PAGE_EXPERIENCE.md) · [Landing Critique](docs/LANDING_PAGE_CRITIQUE_V5_3.md) · [Master Playbook](docs/MASTER_PLAYBOOK.md) · [Architecture](docs/ARCHITECTURE.md) · [Skill Decisions](docs/SKILL_ADOPTION_DECISIONS.md) · [Changelog](CHANGELOG.md)



## v5.3 — Editorial Production Atlas
The landing page has been rebuilt with a new visual identity, responsive navigation, channel and renderer explorers, a searchable document library and current v5.2 decisions. The critique pass and implementation notes are in [Landing Page Critique](docs/LANDING_PAGE_CRITIQUE_V5_3.md).

## v5.0 — Two-Channel Storytelling Studio

Approved direction: a reference-first production system for two original animated storytelling channels. Benchmark inputs: [His Story](https://www.youtube.com/@hisytstory) and [Her Story](https://www.youtube.com/@herytstory). They are production-quality references, not identities or assets to copy.

**Workflow:** reference discovery and shot-by-shot analysis → original character and voice auditions → user iteration and freeze → original channel naming/handle checks → icons/banner/thumbnail identity → 30–60 idea backlog → approved one/two-week batches → local Blender rendering → human QA → manual upload.

See [Blueprint](docs/TWO_CHANNEL_STUDIO_BLUEPRINT.md), [Reference Analysis](docs/REFERENCE_REVERSE_ENGINEERING.md), [Character DNA](docs/CHARACTER_DNA_AND_LOCKS.md), [Voice Identity](docs/VOICE_IDENTITY_SYSTEM.md), [Brand & Thumbnails](docs/BRAND_NAMING_AND_THUMBNAILS.md), [Content Board](docs/CONTENT_BOARD_AND_BATCH_OPERATIONS.md), [Blender Engine](docs/BLENDER_PRODUCTION_ENGINE.md), [Operations](docs/PRODUCTION_OPERATIONS.md) and [Acceptance Tests](docs/IMPLEMENTATION_ACCEPTANCE_TESTS.md).

v5.0 is an approved blueprint, not a claim that new modules are installed. Preserve v4.1 technologies and constraints. Suno is a narrow user-approved composition exception; it does not authorize other paid inference or hosted generation.

## What this repository is
The source of truth for an offline-first, code-driven faceless video studio: production architecture, tool responsibilities, agent handovers, skill decisions, QA gates and implementation roadmap. Creative intelligence directs; deterministic local tools and specialist models execute repeatable work.

## v5.4 — Cinematic Skill specialist pilot
Cinematic Skill (Python + Skia) is approved for a controlled documentary/explainer pilot. It adds narration-led beat planning, virtual-camera movement, drawn maps/diagrams/typography, subtitles and sound design. It is not installed or validated. Its archive/photo/AI-still paths are excluded from final renders; our code-generated-visual invariant remains absolute. See [Cinematic Skill Adoption Assessment](docs/CINEMATIC_SKILL_ADOPTION.md).

## v5.2 renderer decision
Remotion and HyperFrames + GSAP are co-equal first-class production engines. Remotion is approved for the current solo-operator workflow under its official Free License (including commercial use and automation, subject to terms); it is source-available under a proprietary licence, not OSI open source. Cinetic is approved for a controlled launch-film/update-video pilot, not installed. See [Cinetic Adoption Assessment](docs/CINETIC_ADOPTION.md), [Cinematic Skill Adoption Assessment](docs/CINEMATIC_SKILL_ADOPTION.md), [Master Playbook](docs/MASTER_PLAYBOOK.md) and [Skill Decisions](docs/SKILL_ADOPTION_DECISIONS.md).

## v4.1 architecture
| Plane | Responsibility | Examples |
|---|---|---|
| Intelligence/orchestration | Creative direction, planning, ambiguity, exception diagnosis and quality decisions | Claude Code or Codex |
| Local execution | Repeatable processing, rendering, conversion, validation and batching | PowerShell, Python, Node.js, FFmpeg, ffprobe |
| Specialist production | Motion, composition and 3D | HyperFrames, GSAP, Remotion, Blender, Three.js |
| Local AI | Offline speech and specialist inference | faster-whisper, Chatterbox, IndicF5 and evaluated local models |

**Mandatory routing:** cache/reuse → deterministic local code → local specialist model → bounded agent reasoning → larger reasoning only when justified.

## New v4.1 decision: Reference-to-Animation Intelligence
[ReelMimic](https://github.com/edenfunf/reelmimic) is now an approved upstream reference for a dedicated Reference Intelligence Engine. We will selectively adopt its strongest ideas:
- Analyse a supplied reference video into shot boundaries, pacing, camera movement, colour/look and optional audio-beat cues.
- Create versioned fingerprints and map storyboard shots to specific reference shots and techniques.
- Generate style frames and require approval before rendering.
- Use isolated parallel shot production, fresh-context reviews and before/after evidence for fixes.
- Compare the finished render with the reference as an advisory QA aid.

**Important:** this is a design/adoption decision, not an installed integration. Internet access and tools such as yt-dlp may be used when genuinely useful for research and reference-video acquisition. Downloaded references are analysis inputs only, never final-video footage. Our final visual frames must be original and code-generated using our own scene/rendering system; no stock/static photos or generic downloaded video clips. We will retain our existing HyperFrames + GSAP, Remotion, Blender + Three.js and FFmpeg stack. ReelMimic uses Claude Code/Codex account inference; it is not fully local inference.

## Other v4 decisions
- **Animation Recipe Engine (planned):** six recipe families—3D explainer, stick figure, minimal graphics, map route, exploded breakdown and graph—adapted to the existing local renderer stack. Target: JSON scene spec → deterministic render → contact sheet and QA report.
- **Code-review pilot:** evaluate the four-probe review skill for meaningful/high-risk diffs in both agent workflows. Advisory only; no auto-merge.
- **Audio-first storyboard QA (planned):** narration-anchored shot rows, visual references and semantic script-to-shot checks using local transcription.
- **Separate/excluded:** Ray Sticker Shop stays separate; medical-paper skills are excluded.

See [ReelMimic adoption assessment](docs/REELMIMIC_ADOPTION.md), [Skill Adoption Decisions](docs/SKILL_ADOPTION_DECISIONS.md) and [Master Playbook](docs/MASTER_PLAYBOOK.md) for implementation gates and licence boundaries.

## Production pipeline
1. Brief and success criteria.
2. Evidence-backed research and script.
3. Optional reference-video analysis and storyboard approval.
4. Voice generation/import and local transcript timing.
5. Narration-anchored EDL and cleaned timeline.
6. Visual language, scene recipes and code-driven scenes.
7. 3D/motion production, FFmpeg assembly, captions, music and sound design.
8. Technical QA, contact sheets and human playback review.
9. Verified delivery and archived project state.

## Core technology direction
- First-class motion engines: **HyperFrames + GSAP and Remotion**; optional specialist documentary renderer pilot: **Cinematic Skill (Python + Skia)**.
- Specialist React/data scenes: **Remotion**, selectively.
- 3D/technical visuals: **Blender + Three.js**.
- Media processing/final assembly: **FFmpeg / ffprobe**.
- Local transcription: **faster-whisper**.
- Offline voice: **Chatterbox / IndicF5** and locally runnable candidates after evaluation.
- Image enhancement: **Upscayl**, where useful.

A skill's existence or star count is not proof that it belongs in the production baseline. Preserve working integrations; pilot before promotion.

## Non-negotiable constraints
- **Final-visual invariant:** every final visual element/frame must be authored or generated through code in our production pipeline (e.g. SVG, Canvas, WebGL, procedural graphics, charts, typography, animation and 3D geometry). No stock/static photos, downloaded video clips, generic downloaded B-roll in the final render.
- Reference footage, online research, documentation and downloaded examples may be used for analysis and inspiration, subject to rights and provenance. They must not be inserted into the final video.
- Offline-first and free/open-source by default.
- No paid inference APIs, hosted generation credits or cloud uploads in the default path.
- **No ComfyUI.** Internet tools, including yt-dlp, are permitted when useful for research/reference acquisition; they must never supply footage or still images to the final video.
- No remote CDN/fonts/runtime dependency in final renders.
- Preserve human review for factual accuracy, editorial judgement and final quality.
- Respect software, model, font, image, music, SFX and 3D-asset licences separately.
- Never claim planned automation or skill pilots are implemented until tested.

## Start here
- [Master Production Playbook](docs/MASTER_PLAYBOOK.md)
- [Cinetic Adoption Assessment](docs/CINETIC_ADOPTION.md)
- [Cinematic Skill Adoption Assessment](docs/CINEMATIC_SKILL_ADOPTION.md)
- [Claude Code handover](agents/claude/CLAUDE_ONLY.md) · [Claude playbook](agents/claude/CLAUDE_ONLY_PLAYBOOK.md)
- [Codex handover](agents/codex/CODEX_ONLY.md) · [Codex playbook](agents/codex/CODEX_ONLY_PLAYBOOK.md)
- [Architecture](docs/ARCHITECTURE.md) · [Roadmap](docs/ROADMAP.md)
- [Token-efficiency policy](docs/TOKEN_EFFICIENCY_POLICY.md) · [Skill decisions](docs/SKILL_ADOPTION_DECISIONS.md)
- [ReelMimic adoption assessment](docs/REELMIMIC_ADOPTION.md)
- [Changelog](CHANGELOG.md)

## Project status
Architecture and upstream adoption decisions are documented, including the Cinematic Skill controlled pilot. Reference Intelligence Engine, Animation Recipe Engine, code-review integration and storyboard QA remain pilots/backlog until implemented and tested. Helper scripts and runtime enforcement are not represented as active.

---
**Build once. Automate the repeatable. Spend intelligence where it matters.**

## v5.5 — Creator Generalist craft-skill layer
Creator Generalist is approved for a selective, isolated pilot: selected Blender 3D craft skills and a filtered 2D Generalist for code-generated maps, charts, timelines and diagrams. It is a skill pack, not a new model or renderer. Watch Video and Design Sound are excluded from the first pilot; 67.js and all photo/downloaded-asset paths are excluded. Not installed, pinned or validated. See [Creator Generalist Adoption Assessment](docs/CREATOR_GENERALIST_ADOPTION.md).