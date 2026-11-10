# Cinetic Adoption Assessment — v5.2

**Decision:** Approved for a controlled pilot; not installed. **Scope:** Optional creative-direction and finishing skill for launch films, product/channel updates, trailers and social cut-downs.

## Source
- Repository: https://github.com/Leonxlnx/cinetic
- Licence: Cinetic source is MIT; review bundled scene, asset, music and dependency licences separately.
- v1.5 adds a 34-scene Remotion starter library. Treat it as a candidate scene bank, not an approved visual identity.

## Fit with our studio
Cinetic can contribute brief/script-first planning, beat grids, scene selection, motion/audio QA, contact sheets, critic passes, sync checks and delivery manifests. Best uses: original channel launch film and identity reveal; series/season announcement and story-universe teaser; studio progress/update videos; social cut-downs from approved original material. It is not the main narrative engine for full episodes and must not become a second orchestrator. Our story engine, character/voice locks, content board and human approval gates remain authoritative.

## Renderer policy
Remotion and HyperFrames + GSAP are co-equal first-class engines. Remotion serves React compositions, reusable components, data-driven visuals and launch/update films. HyperFrames + GSAP serves timeline/beat-led motion and editorial sequencing. Blender + Python remains the original 3D character/environment engine; Three.js is specialist; FFmpeg + ffprobe handles assembly, encoding and technical QA. Choose per scene. Do not assume Cinetic Remotion components run in HyperFrames; port ideas separately and test. Avoid unnecessary cross-renderer handoffs.

## Remotion licensing
The project is currently operated by one individual. Remotion's official Free License covers individuals for personal or commercial video creation and automation, with full functionality and no sign-up required, subject to terms:
- https://convert.remotion.dev/docs/license/faq
- https://www.remotion.dev/docs/terms
- https://github.com/remotion-dev/remotion/blob/main/LICENSE.md

Remotion is source-available under its proprietary licence, not OSI-defined open source. Reassess before use if another company/client/person jointly owns, controls or directly operates the same Remotion project, or if involved-party structure changes. Do not assume the solo creator licence covers unrelated employer-owned projects.

## Non-negotiable integration constraints
1. **Windows first:** upstream is less tested on Windows than Linux. Use Git Bash where required. Verify exact current requirements from the pinned revision before installation; documented requirements include Node 22+, Python 3.11+, FFmpeg 6+, Chromium, Bash and the earshot companion.
2. **No premature install:** pin revision; inspect install scripts, dependencies, permissions, network calls and licences. Do not claim installed until Windows setup succeeds.
3. **Original visuals only:** disable/exclude stock-photo, downloaded image/video and generic B-roll paths from final renders. Final visual invariant remains code-authored/generated visuals plus approved original assets.
4. **Music separation:** Cinetic's documented workflow requires licensed human-made instrumental music and excludes AI-generated tracks. This is a Cinetic workflow constraint only; it does not replace the user's narrow approved Suno composition exception. Preserve music provenance, source, plan/licence evidence and attribution obligations.
5. **Motion blur:** benchmark before enabling globally; it can materially increase render time.
6. **Offline final render:** after approved dependencies/assets are present, render and QA must run without remote runtime/CDN dependencies or uploads.
7. **Agent rollout:** test one controlled Claude Code or Codex workflow first. Do not install into both environments or add competing skill wrappers until invocation and outputs are stable.

## Pilot protocol
Create one 20–30 second original launch film from a fixed brief using only approved original brand/character assets. Compare Cinetic + Remotion with hand-authored Remotion; add a HyperFrames + GSAP equivalent where useful. Capture pinned commits, environment, commands, setup issues, network calls, downloaded files, scene editability, render duration, peak RAM/VRAM, motion-blur overhead, audio sync, QA findings, contact sheets, complete playback review, human corrections and originality/channel fit.

**Promotion rule:** promote Cinetic only if it provides a measurable workflow or quality advantage over direct Remotion authoring without compromising originality, licensing, offline operation or reliability. Otherwise retain useful independently documented ideas and do not keep the dependency.

## Status
- Remotion first-class decision: approved/documented.
- Cinetic pilot: approved/documented.
- Cinetic installation: not performed.
- 34-scene bank: not yet evaluated on the Windows machine.
- Production readiness: not established.
