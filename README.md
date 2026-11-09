# VIDEO PRODUCTION STUDIO

### A local-first, AI-orchestrated cinematic production system.

**Claude Code / Codex think. Local tools execute. Every repeatable task becomes automation.**

[Explore the Studio](https://vikramma27.github.io/video-production-studio/) · [Master Playbook](docs/MASTER_PLAYBOOK.md) · [Architecture](docs/ARCHITECTURE.md) · [Skill Decisions](docs/SKILL_ADOPTION_DECISIONS.md) · [Changelog](CHANGELOG.md)

## What this repository is
The source of truth for an offline-first, code-driven faceless video studio: production architecture, tool responsibilities, agent handovers, skill decisions, QA gates and implementation roadmap. Creative intelligence directs; deterministic local tools and specialist models execute repeatable work.

## v4 architecture
| Plane | Responsibility | Examples |
|---|---|---|
| Intelligence/orchestration | Creative direction, planning, ambiguity, exception diagnosis and quality decisions | Claude Code or Codex |
| Local execution | Repeatable processing, rendering, conversion, validation and batching | PowerShell, Python, Node.js, FFmpeg, ffprobe |
| Specialist production | Motion, composition and 3D | HyperFrames, GSAP, Remotion, Blender, Three.js |
| Local AI | Offline speech and specialist inference | faster-whisper, Chatterbox, IndicF5 and evaluated local models |

**Mandatory routing:** cache/reuse → deterministic local code → local specialist model → bounded agent reasoning → larger reasoning only when justified.

## New v4 decisions
- **Animation Recipe Engine (planned):** six recipe families—3D explainer, stick figure, minimal graphics, map route, exploded breakdown and graph—adapted to the existing local renderer stack. Target: JSON scene spec → deterministic render → contact sheet and QA report.
- **Code-review pilot:** evaluate the four-probe review skill for meaningful/high-risk diffs in both agent workflows. Advisory only; no auto-merge.
- **Audio-first storyboard QA (planned):** narration-anchored shot rows, visual references and semantic script-to-shot checks using local transcription.
- **Separate/excluded:** Ray Sticker Shop stays separate; medical-paper skills are excluded.

See [Skill Adoption Decisions](docs/SKILL_ADOPTION_DECISIONS.md) and [Master Playbook](docs/MASTER_PLAYBOOK.md) for licence caveats, pilot criteria and status boundaries.

## Production pipeline
1. Brief and success criteria.
2. Evidence-backed research and script.
3. Voice generation/import and local transcript timing.
4. Narration-anchored EDL and cleaned timeline.
5. Visual language and recipe selection.
6. Code-driven scenes, 3D and motion production.
7. FFmpeg assembly, captions, music and sound design.
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
- Offline-first and free/open-source by default.
- No paid inference APIs, hosted generation credits or cloud uploads in the default path.
- **No ComfyUI. No yt-dlp.**
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
- [Changelog](CHANGELOG.md)

## Project status
Architecture and skill decisions are documented. The Animation Recipe Engine, code-review integration and storyboard QA remain pilots/backlog until installed and tested. Helper scripts and runtime enforcement are not represented as active.

---
**Build once. Automate the repeatable. Spend intelligence where it matters.**
