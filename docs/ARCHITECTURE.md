# Studio Architecture — v4

## Two-plane design
**Intelligence/orchestration:** Claude Code or Codex owns objectives, creative direction, planning, trade-offs, ambiguity, exception diagnosis, reusable automation design and quality decisions. Only one is the active AI worker for a project session.

**Local execution:** PowerShell, Python, Node.js, FFmpeg/ffprobe, local specialist models and selected renderers perform deterministic work.

## Routing hierarchy
1. Reuse valid output/cache.
2. Run deterministic local code or CLI.
3. Use a suitable local specialist model.
4. Make a bounded agent call.
5. Use a larger reasoning call only if justified.

## Tool responsibilities
| Domain | Default |
|---|---|
| Primary motion | HyperFrames + GSAP |
| React/data scenes | Remotion selectively |
| 3D/technical visuals | Blender / Three.js |
| Media operations | FFmpeg / ffprobe |
| Local transcription | faster-whisper |
| Offline TTS | Chatterbox / IndicF5 candidates |
| Image enhancement | Upscayl |

## v4 additions
- Animation Recipe Engine: JSON scene spec → local renderer → contact sheet/QA. Six recipe families are patterns, not a new renderer.
- Code-review skill: advisory four-probe pilot for meaningful/high-risk diffs; never auto-merge.
- Storyboard QA: independently implement narration anchors, visual references and semantic shot checks using local transcription.
- Ray Sticker Shop stays separate; medical-paper skills excluded.

## Pipeline and timeline
Brief → research/script → voice/transcript → cleaned editorial timeline → visual language/recipes → render → assembly → QA → delivery/archive. After editorial cuts, remap captions, B-roll, effects and audio to the cleaned timeline.

## Reliability and scope
Every repeatable stage should be cache-aware, batchable and independently rerunnable. Persist project state, decisions, asset metadata, stage manifests and QA results. Offline-first; no paid inference/cloud uploads by default. No ComfyUI or yt-dlp. Scripts and pilots are backlog until implemented and tested on representative Windows hardware.
