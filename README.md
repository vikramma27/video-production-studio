# VIDEO PRODUCTION STUDIO

### A local-first, AI-orchestrated cinematic production system.

**Claude Code / Codex think. Local tools execute. Every repeatable task becomes automation.**

[Explore the Studio](https://vikramma27.github.io/video-production-studio/) · [Master Playbook](docs/MASTER_PLAYBOOK.md) · [Architecture](docs/ARCHITECTURE.md) · [Skill Decisions](docs/SKILL_ADOPTION_DECISIONS.md) · [Changelog](CHANGELOG.md)

## What this repository is
The source of truth for an offline-first, code-driven faceless video studio: production architecture, tool responsibilities, agent handovers, skill decisions, QA gates and implementation roadmap. Creative intelligence directs; deterministic local tools and specialist models execute repeatable work.

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

**Important:** this is a design/adoption decision, not an installed integration. Internet access and tools such as yt-dlp may be used when genuinely useful for research and reference-video acquisition. Downloaded references are analysis inputs only, never final-video footage. Our final visual frames must be original and code-generated using our own scene/rendering system; no stock photos, downloaded clips, generic B-roll, static-image slides or AI-generated raster-image assets. We will retain our existing HyperFrames + GSAP, Remotion, Blender + Three.js and FFmpeg stack. ReelMimic uses Claude Code/Codex account inference; it is not fully local inference.

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
- Primary motion: **HyperFrames + GSAP**.
- Specialist React/data scenes: **Remotion**, selectively.
- 3D/technical visuals: **Blender + Three.js**.
- Media processing/final assembly: **FFmpeg / ffprobe**.
- Local transcription: **faster-whisper**.
- Offline voice: **Chatterbox / IndicF5** and locally runnable candidates after evaluation.
- Image enhancement: **Upscayl**, where useful.

A skill's existence or star count is not proof that it belongs in the production baseline. Preserve working integrations; pilot before promotion.

## Non-negotiable constraints
- **Final-visual invariant:** every final visual element/frame must be authored or generated through code in our production pipeline (e.g. SVG, Canvas, WebGL, procedural graphics, charts, typography, animation and 3D geometry). No stock/static photos, downloaded video clips, generic downloaded B-roll, still-image slides or AI-generated raster-image assets in the final render.
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
- [Claude Code handover](agents/claude/CLAUDE_ONLY.md) · [Claude playbook](agents/claude/CLAUDE_ONLY_PLAYBOOK.md)
- [Codex handover](agents/codex/CODEX_ONLY.md) · [Codex playbook](agents/codex/CODEX_ONLY_PLAYBOOK.md)
- [Architecture](docs/ARCHITECTURE.md) · [Roadmap](docs/ROADMAP.md)
- [Token-efficiency policy](docs/TOKEN_EFFICIENCY_POLICY.md) · [Skill decisions](docs/SKILL_ADOPTION_DECISIONS.md)
- [ReelMimic adoption assessment](docs/REELMIMIC_ADOPTION.md)
- [Changelog](CHANGELOG.md)

## Project status
Architecture and upstream adoption decisions are documented. Reference Intelligence Engine, Animation Recipe Engine, code-review integration and storyboard QA remain pilots/backlog until implemented and tested. Helper scripts and runtime enforcement are not represented as active.

---
**Build once. Automate the repeatable. Spend intelligence where it matters.**
