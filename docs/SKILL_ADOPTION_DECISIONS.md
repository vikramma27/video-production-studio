# Skill Adoption Decisions — 2026-11-09

This register records evaluated repositories and the exact boundary for the Video Production Studio. These are adoption decisions and pilot specifications, not a declaration that any repository has been installed or production-validated.

| Repository | Decision | Why / boundary |
|---|---|---|
| [edenfunf/reelmimic](https://github.com/edenfunf/reelmimic) | Adopt selectively as reference-to-animation blueprint | Study reference analysis, shot fingerprints, approval-first storyboards, parallel shot production and evidence-backed QA. Do not vendor wholesale: audit its yt-dlp/network ingestion, hosted Claude/Codex inference, 2D focus and documented full-access Codex sandbox default. Internet acquisition is allowed for references; keep our renderers and never use downloaded footage in final renders. See [adoption assessment](REELMIMIC_ADOPTION.md). |
| [artemnovitckii/claude-animation-skills](https://github.com/artemnovitckii/claude-animation-skills) | Selectively port six recipes | 3D explainer, stick figure, minimalist graphics, map route, exploded breakdown and animated graph. Adapt recipes to the existing Windows-first HyperFrames + GSAP + Three.js/Blender stack. Do not add a second renderer or blindly run the macOS/Linux setup scripts. |
| [kyy-logs/code-review-skill](https://github.com/kyy-logs/code-review-skill) | Pilot for both Claude Code and Codex | Four fresh-context probes: behaviour, tests, repository rules and impact. Use only for meaningful/high-risk diffs. Reports are advisory, not independent model/human adjudication, and never auto-approve or auto-merge. |
| [konlu/story-studio](https://github.com/konlu/story-studio) | Reimplement useful patterns independently | Adopt the concept of audio-first storyboard timing, narration-anchored shot rows, persistent visual references and semantic script-to-shot checks. Do not copy its code/corpus until the root CC BY-NC-SA 4.0 licence versus README MIT wording is clarified. Its default paid TTS and hosted image-generation dependencies are excluded. |
| [imraywang/ray-sticker-shop](https://github.com/imraywang/ray-sticker-shop) | Keep separate | A potential future sticker-pack product workflow, not a core video pipeline dependency. Its generation path requires an OpenAI API key or manual hosted image-generation handoff; local post-processing does not make the full workflow offline. |
| [duyunzhoudyz/dyz-med-paper-skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills) | Exclude | Medical-academic domain is unrelated to this studio. Its PolyForm Noncommercial 1.0.0 licence is not a general commercial-use licence. |

## ReelMimic adoption boundary

Adopt the reference-analysis and fingerprinting approach, shot-to-reference storyboard mapping, approval gate, file-contract/resumable stage design, isolated parallel shot production, fresh-context review and before/after evidence. Keep our own Claude/Codex orchestration playbooks and existing HyperFrames + GSAP, Remotion, Blender + Three.js and FFmpeg stack. ReelMimic's own web app/server is not adopted as a second orchestrator in this phase.

**Adoption boundary:** yt-dlp and internet access are allowed when useful for research/reference acquisition, after auditing dependencies, network behaviour, source provenance and rights. Do not inherit upstream's documented `danger-full-access` Codex default. ReelMimic uses the user's Claude Code/Codex account for inference; local application execution is not fully local inference. Review each bundled engine/asset licence separately. Reference media is analysis-only and must never be used as final footage.

The first implementation target is a Windows-compatible, local-file-only Reference Intelligence Engine with versioned analysis reports and cached fingerprints. Full details and gates: [REELMIMIC_ADOPTION.md](REELMIMIC_ADOPTION.md).

## Animation Recipe Engine design

The planned flow is:

`Agent selects recipe → versioned JSON scene spec → deterministic local renderer → contact sheet + technical QA → bounded agent/human review`

The six recipe families are visual treatments and reusable scene patterns, not six new rendering engines. HyperFrames + GSAP remain primary. Remotion remains selective; Blender and Three.js remain specialist paths. Initial pilot candidates: graph, breakdown and map-route. Every recipe must declare inputs, outputs, assets, timing, renderer requirements, cache key, validation and known limitations.

## Code-review pilot protocol

Pin an exact revision before testing. Run a controlled evaluation against:
1. a small, low-risk diff;
2. a multi-file refactor with behaviour-preserving expectations;
3. a deliberately seeded defect with a known expected finding.

Record true findings, misses, false positives, reproducibility, runtime, invocation cost and host compatibility. A passing report is not proof of correctness. Keep tests, CI, security review and human approval.

## Audio-first storyboard QA protocol

Build narration-anchored shot rows from local transcription/timestamps. Each row should preserve narration range, shot purpose, visual reference, scene/asset requirements, continuity notes and semantic relation to the script. Deterministic code handles time mapping and validation; agents review semantic alignment and editorial ambiguity. After cuts, all dependent layers must map to the cleaned timeline.

## Licensing, privacy and offline gates

- Review code licence, bundled assets, model weights, fonts, music, dependencies and network behaviour separately.
- Story Studio code/corpus reuse is blocked pending licence clarification.
- Medical-paper skills remain excluded; non-commercial terms are not treated as commercial permission.
- No paid API, hosted inference, cloud upload, telemetry or external content transfer in the default workflow.
- No ComfyUI.
- Internet access and yt-dlp are allowed when useful; reference media must not appear in final renders.
- Final visuals must be code-authored/generated; no stock/static photos, downloaded clips, generic B-roll or still-image slides.
- Keep final renders independent of CDNs and remote runtime resources.
- Do not upload private scripts, narration, voice samples or media without explicit approval.

## Promotion gates

1. Pin source revision and record licence/dependency/network review.
2. Validate setup on Windows; installation downloads must be distinguished from offline runtime.
3. Demonstrate reproducible local execution after approved initial downloads.
4. Verify outputs with deterministic checks, contact sheets and full playback.
5. Measure quality, failures, cost and hardware impact.
6. Document limitations and obtain human approval before promotion.

**Status:** ReelMimic is approved for selective study and implementation planning, not installed or production-validated. Animation recipes, code-review integration and storyboard QA remain pilots/backlog. Ray Sticker Shop remains separate. Medical-paper skills are excluded.
