# Master production playbook

This repository is the canonical home for the production architecture and agent handovers. The complete master playbook package is maintained as a versioned artifact and should be integrated here as full source documents when imported.

## Production standard

1. Start with a brief: audience, purpose, format, duration, platform and success criteria.
2. Research claims and maintain source notes for factual content.
3. Lock narrative structure and narration before detailed visual production.
4. Generate or import voice; create word-level timestamps when precise editorial retiming is required.
5. Build an edit decision list (EDL) and a cleaned timeline.
6. Design a coherent visual language. Prefer a persistent visual world over unrelated visuals every few seconds.
7. Build scenes with the primary motion stack or a justified specialist tool.
8. Assemble narration, music, effects, captions and visuals on the cleaned timeline.
9. Run deterministic preflight and QA; inspect representative frames and full playback.
10. Render final outputs, verify technical properties and archive manifests.

## Tool direction

- HyperFrames + GSAP: primary motion and timeline-driven code visuals.
- Remotion: selective React/data-driven scenes.
- Blender / Three.js: 3D and technical illustration.
- FFmpeg / ffprobe: probing, assembly, encoding and validation.
- faster-whisper: local transcription.
- Chatterbox and other local candidates: evaluate for offline voice generation.
- Upscayl: image enhancement where appropriate.

## Editorial integrity

Never let source timestamps drift after cuts. Every dependent layer must be mapped to the final edited timeline. Keep narration, subtitles, B-roll, effects and audio synchronized.

## Quality gates

- Correct aspect ratio, resolution, frame rate and duration.
- No missing media, black frames, accidental gaps or broken transitions.
- Audio is intelligible, consistent and free of clipping.
- Captions are synchronized and readable.
- Factual claims and names are checked.
- Representative frames and the complete export are reviewed.

## Constraints

Offline-first and free/open-source by default. No paid inference APIs, hosted generation credits or cloud uploads in the default workflow. No ComfyUI and no yt-dlp. Planned automation must not be described as implemented until tested.
