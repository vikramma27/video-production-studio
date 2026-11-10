# Infographic Motion Engine — v5.7

**Decision:** approved for specification and a controlled prototype only. No runtime implementation or benchmark is claimed.

## Purpose
Translate the supplied infographic-channel mega-prompt into our existing studio architecture. Adopt versioned Channel DNA, bounded Episode DNA, procedural vector scenes, original 2D puppets, reusable motion primitives, local narration alignment, deterministic rendering, checkpoints, contact sheets, QA and episode history. Do not copy its image-heavy asset workflow, auto-installer, hosted voice defaults or standalone renderer assumptions.

## Architecture
This is a specialist scene-authoring subsystem, not an orchestrator, model or new renderer. Claude Code/Codex provide direction. The existing narration beat contract remains renderer-neutral. The first prototype must target one existing engine only: Remotion or HyperFrames + GSAP. Blender remains the 3D path; Three.js remains specialist realtime 3D; FFmpeg/ffprobe handle assembly and QA. Map the shared beat contract into native engine structures rather than creating a universal schema.

## Channel DNA
Create a versioned, human-approved manifest for identity, palette, local/licensed typography, composition grid, motion language, approved narrator reference, pronunciation, audio policy and thumbnail grammar. User approval freezes permanent identity. Never randomly regenerate or silently change a character, voice, palette or logo.

## Episode DNA
Allow bounded variation from curated options: hook pattern, accent colour, motif, chapter rhythm, layout family, transition pairing and thumbnail composition. Record the seed and choices for reproducibility. Compare the last five episodes and flag repeated combinations; recommendations never mutate approved identity.

## Procedural scene builder
Use original SVG paths, Canvas drawing, HTML/CSS typography, plots, charts, diagrams, maps from approved vector/geospatial data, procedural textures and original Blender geometry. No downloaded photographs, scans, stock imagery, downloaded video, generic B-roll, AI raster stills or third-party pre-rendered scene plates in final renders. Reference media remains analysis-only.

## 2D puppet system
Optional vector puppet with layered head/body/limbs, pivots, poses, expressions, two-bone arm IK, blink/head-nod and simple walk/gesture cycles. All artwork is original vector/code geometry. This complements, not replaces, Blender 3D character rigs. Chroma-keyed raster cutouts are not the default.

## Motion and narration
Build reusable easing/spring, staggered reveal, counter, chart-growth, path-draw, camera push/pan, vector-layer parallax, squash/stretch, anticipation/settle and transition primitives. Animation must be a deterministic function of time/state. Align shots to local word/phrase timestamps and the shared beat contract; do not assume a universal 175-WPM rate. No hosted TTS, ElevenLabs or cloud transcription by default.

## Rendering, QA and history
Use deterministic frame/time evaluation, explicit render manifests, scene/chapter chunks, checkpoints, cancellation and restart recovery. Concurrency is measured and adaptive; no fixed browser parallelism or motion-blur default. Cache keys include source revision, DNA versions, episode manifest, voice/audio hashes, renderer version and output settings.

Produce contact sheets and check missing/duplicate, black/frozen or discontinuous frames, subtitles, narration/shot alignment, audio peaks/loudness, duration, metadata and provenance. Human full-playback review remains mandatory. Episode registry stores topic, script/voice hashes, Episode DNA, motif/layout/transition use, render settings, QA, corrections and approval state.

## Proposed contracts
- Channel DNA: approved persistent identity and version.
- Episode DNA: bounded variation, seed, recent-history comparison and approval.
- Episode manifest: episode ID, script/voice refs, beat IDs, renderer mapping, provenance, checkpoints and QA state.
- Scene spec: dimensions, duration, layers, semantic elements, timing and renderer adapter metadata.
- Puppet spec: original vector parts, pivots, constraints, poses and expressions.
- Render manifest: settings, cache fingerprints, chunk/frame ranges and output hashes.
- QA report: machine checks, contact-sheet refs, human review and unresolved defects.
Do not duplicate the existing narration beat contract; extend it only for a proven missing requirement.

## First benchmark: 60-second centrifugal-pump explainer
Create five to eight original procedural scenes: hook and pump silhouette; impeller/casing cross-section; inlet/outlet flow paths; staged explanation of pressure conversion; procedural chart and annotated callouts; recap. All geometry, arrows, labels, charts and transitions are code-generated or Blender-authored. Technically review the explanation; it is not a certified engineering drawing.

## Pilot gates
P0: define minimal manifests; choose one existing renderer; pin/audit local fonts, browser, FFmpeg, TTS, transcription, licences, Windows paths and offline execution.
P1: create the 60-second 5–8-scene vector animatic and contact sheets.
P2: add motion and local phrase/word alignment; verify deterministic seeking, subtitles and shot sync.
P3: add one original vector host, bounded Episode DNA and last-five repetition warnings; prove episode edits cannot mutate frozen Channel DNA.
P4: measure render time, peak RAM/VRAM, utilisation, cache reuse, correction effort and interruption/recovery; compare one alternate existing renderer only if justified.

Acceptance requires traceable code provenance, frozen Channel DNA, bounded Episode DNA, reproducible frames/manifests, human-reviewed narration sync, contact sheets and full playback, Windows/offline success, measured resource/recovery evidence and human approval gates. Review fonts, code, music and SFX licences separately. Preserve the narrow approved Suno exception; do not expand it to paid inference. No auto-publishing, cloud rendering, paid APIs, ComfyUI or renderer replacement.

**Status:** approved blueprint/prototype direction. No implementation, installation, runtime execution, Windows/offline validation or production benchmark is claimed. Promotion requires evidence and explicit user approval.