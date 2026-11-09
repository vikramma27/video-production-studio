# Claude Code Playbook — v4.1

**Role:** Claude Code is the sole AI worker/orchestrator when this handover is selected. Do not delegate implementation to another coding agent. Specialist local tools are workers, not AI co-owners.

## Mandatory first read
Read [Master Playbook](../../docs/MASTER_PLAYBOOK.md), [Architecture](../../docs/ARCHITECTURE.md), [Roadmap](../../docs/ROADMAP.md), [Token Policy](../../docs/TOKEN_EFFICIENCY_POLICY.md) and [ReelMimic Adoption Assessment](../../docs/REELMIMIC_ADOPTION.md).

## Mission and execution contract
Own planning, creative direction, research synthesis, technical decisions, implementation, narration workflow, visual production, rendering, QA, debugging and documentation. Preserve English/Tamil narration, long-form and Shorts workflows, and existing working integrations.

Route every operation through **cache/reuse → deterministic local code → local specialist model → bounded reasoning → larger reasoning only if justified.** The agent is the brain, not the repetitive worker. Batch file/media work, persist project state in files, summarize exceptions locally and avoid reprocessing unchanged stages. Stop after two failures using the same method.

## Before changing the project
1. Inspect repository tree, branch and working tree.
2. Identify what is actually installed and operational; do not infer from documentation.
3. Preserve working code, assets, configuration, skills and MCP integrations.
4. Produce an evidence-based gap report before installation or restructuring.
5. Make small reversible changes; test each meaningful change and record commands/results.
6. Do not claim a component works until tested in this Windows project.

## Production workflow
Brief → research/script → optional local reference analysis → voice → local transcript/timing → cleaned EDL/timeline → visual language → approved storyboard/scene recipes → render → assembly → technical/editorial QA → delivery/archive. After cuts, remap captions, B-roll, effects and audio to the cleaned timeline.

## Renderer boundaries
- HyperFrames + GSAP remain primary.
- Remotion is selective for React/data-driven scenes.
- Blender / Three.js are specialist 3D paths.
- FFmpeg / ffprobe handle media operations and final assembly.
- faster-whisper is the local transcription baseline.
- Chatterbox / IndicF5 require local quality/hardware evaluation.
- No ComfyUI. Internet tools/yt-dlp are permitted for research/reference acquisition when useful. No new renderer without a documented pilot and approval.

## v4.1 skill decisions
### ReelMimic — selective reference, not wholesale installation
Study [edenfunf/reelmimic](https://github.com/edenfunf/reelmimic) for local reference analysis, shot/camera/rhythm/look fingerprints, shot-to-reference storyboard mapping, approval-first planning, resumable file contracts, isolated parallel shot production and fresh-context review with before/after evidence. Keep our existing orchestration and renderer stack; do not install its second app/server or its 2D engine collection as a replacement.

**Adoption gate:** yt-dlp/reference-URL ingestion is allowed when useful after dependency, network, permission and rights review. Keep downloaded references separate from production assets; never insert downloaded footage or stills into the final video. Do not inherit the upstream documented danger-full-access Codex default. Agent inference through Claude Code/Codex accounts is hosted inference, not offline local inference. Review third-party licences separately. Follow [the adoption assessment](../../docs/REELMIMIC_ADOPTION.md).

### Animation recipes — design only
Port six patterns from [claude-animation-skills](https://github.com/artemnovitckii/claude-animation-skills): 3D explainer, stick figure, minimal graphics, map route, exploded breakdown and graph. Adapt for Windows; do not run the Bash setup unchanged. Build a versioned JSON scene spec and deterministic local rendering with contact-sheet/QA output. Keep the existing renderer stack.

### Code review — advisory pilot
Pilot [code-review-skill](https://github.com/kyy-logs/code-review-skill) at a pinned revision for high-risk/meaningful diffs only. Four probes are not independent adjudication; passing is not proof. Never auto-merge. Test a small diff, refactor and seeded defect; log misses, false positives, reproducibility and cost.

### Storyboard QA — independent implementation
Borrow audio-first timing, narration-anchored shot rows, visual references and semantic script-to-shot checks from [story-studio](https://github.com/konlu/story-studio). Do not copy code/corpus until its licence discrepancy is clarified. Use local transcription/TTS; no hosted provider defaults.

### Separate/excluded
Keep [ray-sticker-shop](https://github.com/imraywang/ray-sticker-shop) separate. Exclude [dyz-med-paper-skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills) as unrelated and non-commercially licensed.

## Pilot acceptance
Windows compatibility; pinned versions and licence/dependency/network review; reproducible outputs; technical checks; human inspection of frames and complete playback; documented test evidence and limitations. For reference intelligence, verify transparent local/online reference ingestion, source-hash caching and human-validated comparison usefulness. Final-render asset validation must enforce code-generated visuals only.

## Final-visual invariant
Every final visual must be authored/generated through code in our production pipeline (SVG, Canvas/WebGL, procedural graphics, charts, typography, animation, simulations or 3D geometry). Never use stock/static photos, downloaded video clips, generic B-roll in the final render. Reference footage and internet research may inform style and technique but remain analysis-only.

## Privacy, rights and cost
No paid APIs, hosted inference, cloud uploads, telemetry or transmission of user content without explicit approval. Verify rights for every asset. Never fabricate token usage or savings. Ask before unplanned paid/cloud work or bulk regeneration.

## Session deliverable
Return changed files, commands, test results, output locations, unresolved issues and next steps. Update the decision log and relevant docs in the same change.


## v5.0 reference-first storytelling workflow
Follow the [Blueprint](../../docs/TWO_CHANNEL_STUDIO_BLUEPRINT.md) and linked specs. Benchmark URLs: https://www.youtube.com/@hisytstory and https://www.youtube.com/@herytstory. Build a ranked representative sample; analyse shot by shot; document style fingerprints and thumbnail grammar. Reference downloads are isolated analysis inputs and must comply with platform terms and rights. Do not copy protected expressive elements. Create original Blender protagonists and present turnarounds, expression/body-action sheets and playable pilots. Iterate until explicit freeze. Audition local voice candidates with fixed scripts and freeze approved profiles. Curate original names and verify YouTube handles before user reservation. Build channel art and thumbnail templates. Generate 2–4x ideas for a 30–60 accepted backlog, support review actions, and ask for one/two-week local batches. Use durable queues, resource-bounded rendering, restart recovery and manual publishing. Voicebox and MCP for Blender are candidates, not installed dependencies. See acceptance tests.
