<div align="center">

# VIDEO PRODUCTION STUDIO

### A local-first, AI-orchestrated cinematic production system.

**Claude Code / Codex think. Local tools execute. Every repeatable task becomes automation.**

[Explore the Studio](https://vikramma27.github.io/video-production-studio/) · [Architecture](docs/ARCHITECTURE.md) · [Token Policy](docs/TOKEN_EFFICIENCY_POLICY.md) · [Changelog](CHANGELOG.md)

</div>

---

## What this repository is

This is the source of truth for a code-driven, offline-first video production studio. It brings creative direction, production workflow, agent instructions, reusable skills, technical standards and the automation roadmap into one version-controlled home.

The aim is not to make an AI agent perform every operation. The aim is to make a reliable production system in which reasoning is used deliberately and routine work is handled by deterministic local tools.

## The operating principle

| Layer | Responsibility | Examples |
|---|---|---|
| Intelligence & orchestration | Creative direction, planning, ambiguity, exception diagnosis and quality decisions | Claude Code, Codex |
| Local execution | Repeatable processing, rendering, conversion, validation and batching | PowerShell, Python, Node.js, FFmpeg, ffprobe |
| Specialist production tools | Focused visual, motion, audio and 3D work | HyperFrames, GSAP, Remotion, Blender, Three.js |
| Local AI | Offline speech, transcription and specialist inference | faster-whisper, Chatterbox and selected local models |

**Permanent rule:** before every operation, check whether an existing result, deterministic script, local tool or local specialist model can perform it reliably. Do not spend hosted-agent tokens on routine work that local automation can handle.

## Start here

- **[Master production playbook](docs/MASTER_PLAYBOOK.md)** — end-to-end production system and technical standards.
- **[Claude Code handover](agents/claude/CLAUDE_ONLY.md)** — instructions for Claude Code as the orchestration brain.
- **[Codex handover](agents/codex/CODEX_ONLY.md)** — independent instructions for Codex as the orchestration brain.
- **[Architecture & workflow](docs/ARCHITECTURE.md)** — production layers, pipeline and tool responsibilities.
- **[Token efficiency policy](docs/TOKEN_EFFICIENCY_POLICY.md)** — mandatory model-call gate and automation rules.
- **[Roadmap & implementation backlog](docs/ROADMAP.md)** — what is specified versus what still needs implementation.
- **[Changelog](CHANGELOG.md)** — version history and decisions.

## Production pipeline

1. **Brief** — define audience, objective, format, duration and creative treatment.
2. **Research & script** — establish factual claims, narrative structure and source notes.
3. **Voice & transcript** — generate or import narration; transcribe locally where required.
4. **Editorial plan** — create a timeline/EDL and map scenes to the cleaned narration timeline.
5. **Visual production** — build motion graphics, code-driven scenes, 3D elements and supporting footage.
6. **Assembly** — synchronize narration, music, sound design, captions and visuals.
7. **Quality assurance** — inspect contact sheets and renders; validate audio, frame rate, duration and captions.
8. **Delivery** — render, verify outputs and archive manifests and project state.

## Core technology direction

- **Primary motion system:** HyperFrames + GSAP.
- **Specialist React/data-driven scenes:** Remotion, when it provides a clear advantage.
- **3D and technical visuals:** Blender and Three.js.
- **Media processing and final assembly:** FFmpeg / ffprobe.
- **Local transcription:** faster-whisper.
- **Offline voice generation:** evaluate Chatterbox and other locally runnable candidates against quality and hardware constraints.
- **Image utilities:** Upscayl where useful.

Tools are adopted selectively after a practical pilot. A repository's existence or star count is not proof that it belongs in the production baseline.

## Non-negotiable constraints

- Offline-first and free/open-source by default.
- No paid inference APIs, hosted generation credits or cloud uploads in the default production path.
- No ComfyUI. No yt-dlp.
- No unnecessary CDN, remote fonts or network dependency in final renders.
- Keep source projects, manifests, assets and outputs reproducible.
- Preserve human review for factual accuracy, editorial judgement and final quality.
- Never describe planned automation as implemented until it exists and has passed a test.

## Repository map

```text
.
├── index.html
├── README.md
├── CHANGELOG.md
├── docs/
│   ├── MASTER_PLAYBOOK.md
│   ├── ARCHITECTURE.md
│   ├── TOKEN_EFFICIENCY_POLICY.md
│   └── ROADMAP.md
├── agents/
│   ├── claude/CLAUDE_ONLY.md
│   └── codex/CODEX_ONLY.md
└── .github/workflows/pages.yml
```

## Project status

The architecture and operating rules are documented. The helper-script backlog is a specification, not a claim that the scripts are already installed or enforced in a production environment. See [Roadmap](docs/ROADMAP.md) for the implementation boundary.

## Updating this system

All durable changes should be committed here. Update the relevant playbook, agent handover, policy and changelog together when a decision changes. Prefer small, reviewable commits with clear messages. Do not silently remove or weaken permanent architecture rules.

---

<div align="center">

**Build once. Automate the repeatable. Spend intelligence where it matters.**

</div>
