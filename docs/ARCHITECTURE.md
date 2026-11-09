# Studio architecture

## Two-plane design

### Intelligence and orchestration plane
Claude Code and Codex own objectives, creative direction, planning, trade-off decisions, ambiguous reasoning, exception diagnosis and quality review. They should create reusable automation when a repeated task has no reliable local implementation.

### Local execution plane
PowerShell, Python, Node.js, FFmpeg/ffprobe and specialist production tools execute deterministic work. Local specialist models handle suitable offline inference tasks.

## Routing hierarchy

1. Reuse an existing output or valid cache.
2. Run deterministic local code or a CLI tool.
3. Use a suitable local specialist model.
4. Make a bounded agent call for judgement or unresolved ambiguity.
5. Use a larger reasoning call only when the problem warrants it.

## Production responsibilities

| Domain | Preferred direction |
|---|---|
| Motion graphics | HyperFrames + GSAP |
| React/data-driven scenes | Remotion selectively |
| 3D and technical visuals | Blender / Three.js |
| Media probing, assembly, encoding | FFmpeg / ffprobe |
| Local transcription | faster-whisper |
| Offline TTS | Chatterbox and evaluated local alternatives |
| Image enhancement | Upscayl |

## Pipeline

Brief → research/script → narration/transcript → editorial timeline → visual production → assembly → QA → delivery/archive.

Timeline rule: after editorial cuts, captions, B-roll, effects and audio must follow the cleaned timeline. Do not reuse original source timestamps without applying the edit mapping.

## Reliability

Every repeatable stage should be independently rerunnable, cache-aware and batchable. Store project state, decisions, asset metadata, stage manifests and QA results with the project. Invalidate only downstream stages affected by a change.

## Scope boundary

The architecture and helper backlog are documented here. Scripts are not considered implemented until committed, executed and tested on representative media. Cloud inference and external uploads are excluded from the default path. No ComfyUI or yt-dlp.
