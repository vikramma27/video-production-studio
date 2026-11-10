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

The first implementation target is a Windows-compatible Reference Intelligence Engine that can analyse local files and intentionally acquired online references, with versioned reports, source provenance and cached fingerprints. Full details and gates: [REELMIMIC_ADOPTION.md](REELMIMIC_ADOPTION.md).

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


## v5.0 additions — Blender and voice candidates

### MCP for Blender — controlled pilot
Source: https://github.com/ahujasid/mcp-for-blender. Current upstream documents Windows setup, Claude Code/Codex clients, scene inspection, Python execution, viewport/frame inspection and safe mode. Candidate for interactive character/scene iteration, not a production dependency. Pin revision; audit installer/dependencies/network/telemetry/permissions; disable telemetry, enable safe mode, localhost only. Keep optional cloud 3D generators off. Promote only after Windows tests and a deterministic CLI counterpart.

### Jamie Pine Voicebox — local voice-studio candidate
Source: https://github.com/jamiepine/voicebox. Candidate UI for local auditions/profile management; current docs list engines including Qwen3-TTS, Chatterbox variants and Kokoro. MIT app licence does not automatically license each model/weight. Verify commercial use, language, watermark and output terms for exact weights. Compare with Chatterbox/IndicF5; no adoption until Windows, voice quality, consistency and licence tests pass. Never clone reference narrators or identifiable voices without authorization.


## v5.2 — Cinetic and Remotion

| Candidate | Decision | Boundary |
|---|---|---|
| [Remotion](https://www.remotion.dev/) | Promote to first-class engine alongside HyperFrames + GSAP | Solo operator qualifies for official Free License, including commercial use and automation, subject to terms. Source-available/proprietary, not OSI open source. Reassess if ownership/team/collaboration changes. |
| [Leonxlnx/cinetic](https://github.com/Leonxlnx/cinetic) | Approve controlled pilot | Optional launch-film/update-video/teaser/social-cutdown skill. Not a second orchestrator, not a full-episode default, not installed yet. Test v1.5 34-scene Remotion starter on Windows. |
| Cinetic scene bank | Evaluate, do not wholesale promote | Curate scenes for our channel identities. Do not assume HyperFrames compatibility; port ideas separately only after validation. |
| Cinetic music path | Conditional / separate | Its requirement for licensed human-made instrumental tracks does not replace or invalidate the user's narrow approved Suno composition exception. Track licence/provenance separately. |
| Cinetic asset discovery | Restricted | No downloaded stock imagery/video/B-roll in final renders. Use original code-generated scenes and approved original brand assets only. |

Remotion official references: [License FAQ](https://convert.remotion.dev/docs/license/faq), [Terms](https://www.remotion.dev/docs/terms), [LICENSE](https://github.com/remotion-dev/remotion/blob/main/LICENSE.md). Cinetic implementation gates and constraints: [CINETIC_ADOPTION.md](CINETIC_ADOPTION.md).

## v5.4 — Cinematic Skill

| Candidate | Decision | Boundary |
|---|---|---|
| [Moh4696/cinematic-skill](https://github.com/Moh4696/cinematic-skill) | Controlled specialist-renderer pilot | Python + Skia narration-led documentary/explainer sequences; not installed or validated. See [assessment](CINEMATIC_SKILL_ADOPTION.md). |
| Narration beat contract | Standardise a minimal renderer-neutral contract | VO timing, shot/beat IDs, visual intent, camera path, transition, provenance and approval state can feed Cinematic Skill, Remotion, HyperFrames and Blender. Do not create a bloated universal scene format. |
| Archive/photo/AI-still path | Excluded from final renders | No downloaded photos, scans, stock imagery, downloaded video, generic B-roll or AI-generated raster stills in final output. |

Cinematic Skill is best suited to maps, diagrams, typography, annotations and camera travel for science/engineering/history explainers. It does not displace the co-equal Remotion/HyperFrames engines or Blender's 3D role. Pin and review the upstream revision, dependencies, licence, network/filesystem behaviour and Windows setup before isolated installation. Use the existing local voice profile. Promotion requires a 60–90 second code-only pilot, offline/Windows validation, performance measurements and a comparative human review.

## v5.5 — Creator Generalist

| Candidate | Decision | Boundary |
|---|---|---|
| [codepawl/creator-generalist](https://github.com/codepawl/creator-generalist) | Selective controlled skill pilot | Skill pack, not a new model or renderer. Not installed, pinned or validated. |
| 3D Generalist + craft skills | Pilot selected skills | Blender modelling, characters, rigging, acting, cutaways, environments and camera/lighting. Blender remains the renderer. |
| 2D Generalist | Pilot with strict filtering | Maps, charts, timelines, diagrams and editorial motion using code-generated visuals only. Exclude `photos` mode and photo-led collage. |
| Watch Video | Do not install in first pilot | Study frame-sheet/transcript analysis concepts separately; audit any acquisition scripts and network paths before future use. |
| Design Sound | Exclude from first pilot | Web/ElevenLabs fetching and model-based foley overlap or conflict with local-first audio direction. |
| 67.js | Do not promote | Avoid renderer proliferation; require a separate benchmark and explicit decision before adoption. |

Hard policy overrides: no downloaded/stock/scanned imagery, downloaded video, generic B-roll, AI raster stills or unapproved third-party visual assets in final renders; no hosted/paid generation, ElevenLabs or ComfyUI. Original/procedural visuals and local TTS only. Pilot one isolated agent environment after pinned-source and dependency/security review. See [Creator Generalist Adoption Assessment](CREATOR_GENERALIST_ADOPTION.md).

## v5.7 — Infographic Motion Engine

| Candidate | Decision | Boundary |
|---|---|---|
| Supplied infographic mega-prompt patterns | Selective architecture adoption | Channel DNA, Episode DNA, procedural vector scenes, puppets, motion, narration sync, deterministic rendering, QA and episode history. |
| Infographic Motion Engine | Approved controlled prototype blueprint | Specialist subsystem, not orchestrator or new renderer. Not implemented or benchmarked. |
| Channel DNA | Permanent, human-approved manifest | Versioned and frozen; never randomly regenerate identity. |
| Episode DNA | Bounded variation | Curated alternatives and reproducible seed; anti-repetition warnings; no identity mutation. |
| Image-heavy workflow | Reject for final visuals | No AI raster plates, stock photos, scans, downloaded video or generic B-roll. |
| Voice/render defaults | Adapt and benchmark | Local TTS/alignment; no ElevenLabs/hosted inference. No fixed WPM, frame-rate, motion-blur or parallel-browser assumptions. |

See [Infographic Motion Engine Blueprint](INFOGRAPHIC_MOTION_ENGINE.md). Preserve Remotion/HyperFrames/Blender/FFmpeg responsibilities.


## v5.8 — Givemotion

| Candidate | Decision | Boundary |
|---|---|---|
| Givemotion v0.1.5 | Approved for controlled renderer pilot; not installed or validated | Agent-native HTML/CSS/JS authoring, preview, checks and incremental rendering. Compare with Remotion and HyperFrames on identical briefs before promotion. |
| Givemotion as first-class renderer | Not approved yet | Do not route routine episodes or add it to the production engine selector before Windows/offline/security/performance/quality gates and explicit user approval. |
| Givemotion skill install | Isolated workspace only after audit | Pin source; review scripts, subprocesses, filesystem/network access, dependencies and licences. Do not bulk-install into both agents. |
| Givemotion external resources | Prohibited in final renders | No CDN, remote font, script, media, external Lottie resource, stock/downloaded imagery, AI raster plates or generic B-roll. |
| Givemotion security | Restricted execution | Compositions are executable HTML/JS. Use trusted code only, sandbox it, expose no secrets and block outbound network during render. |

The upstream benchmark is author-run and small-sample; it is a test hypothesis, not proof. See [Givemotion Adoption Assessment](GIVEMOTION_ADOPTION.md) for the benchmark matrix, version pin, Windows/offline preflight and acceptance gates.


## v5.8 — Givemotion

| Candidate | Decision | Boundary |
|---|---|---|
| Givemotion v0.1.5 | Approved for controlled renderer pilot; not installed or validated | Agent-native HTML/CSS/JS authoring, preview, checks and incremental rendering. Compare with Remotion and HyperFrames on identical briefs before promotion. |
| Givemotion as first-class renderer | Not approved yet | Do not route routine episodes or add it to the production engine selector before Windows/offline/security/performance/quality gates and explicit user approval. |
| Givemotion skill install | Isolated workspace only after audit | Pin source; review scripts, subprocesses, filesystem/network access, dependencies and licences. Do not bulk-install into both agents. |
| Givemotion external resources | Prohibited in final renders | No CDN, remote font, script, media, external Lottie resource, stock/downloaded imagery, AI raster plates or generic B-roll. |
| Givemotion security | Restricted execution | Compositions are executable HTML/JS. Use trusted code only, sandbox it, expose no secrets and block outbound network during render. |

The upstream benchmark is author-run and small-sample; it is a test hypothesis, not proof. See [Givemotion Adoption Assessment](GIVEMOTION_ADOPTION.md) for the benchmark matrix, version pin, Windows/offline preflight and acceptance gates.
