# Blender Production Engine

## Primary role
Blender + Python is primary for recurring 3D characters, environments, rigging, animation, camera, lighting and rendered shots. Three.js remains specialist web/interactive scene path. HyperFrames + GSAP and selective Remotion remain for motion graphics, titles, data visuals and compositing. FFmpeg/ffprobe remains media processing/final assembly.

## MCP for Blender candidate
Evaluate [ahujasid/mcp-for-blender](https://github.com/ahujasid/mcp-for-blender). Upstream documents Windows setup, Claude Code/Codex clients, scene inspection, Python execution, viewport/frame inspection and safe mode. It is third-party, not an official Blender component.

Before installation: pin and inspect revision/licence; audit install script, dependencies, network and permissions; disable telemetry; enable safe mode; bind socket to localhost only; never expose the unauthenticated socket to a network; keep optional cloud 3D generators and external asset imports disabled by default. Test non-sensitive scenes first.

MCP is an agent-facing interactive tool. Production must run via local Blender Python/CLI independently, with validated shot specs and manifests.

## Deterministic scene contract
Input: validated shot JSON, pinned asset manifest, scene template and render configuration. Output: .blend scene/state, frames/video, contact sheet, logs, render metadata and QA report. Record Blender version, engine, device, samples, resolution, FPS, colour management, asset hashes and script version. Cache by all relevant inputs.

## Quality and performance
Benchmark Eevee and Cycles on the same representative scene. Use preview settings for iteration and final settings for approved shots. Use proxies where useful. Serialize heavy GPU renders by default until hardware benchmarks justify bounded concurrency. Recover at shot boundaries and do not invalidate unrelated completed shots.

## Acceptance
A .blend project is reviewable; headless CLI reproduces the shot; manifests validate; character IDs resolve to frozen assets; outputs are inspectable; failure recovery/cache invalidation work; telemetry/network behaviour is documented.