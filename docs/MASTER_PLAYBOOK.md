# Master Production Playbook — v4.1
**Video Production Studio | 2026-11-09**

Canonical operating specification for the offline-first, code-driven faceless video studio. Documentation is not implementation: no capability is considered installed or production-ready until it exists in the actual Windows project and passes representative tests.

## Mission and operating model
Build a repeatable studio for original long-form videos and Shorts, with English/Tamil narration options, code-generated visuals, reliable editing and human-reviewed delivery.

- **Intelligence plane:** Claude Code or Codex handles creative direction, planning, research synthesis, trade-offs, ambiguity, exception diagnosis and quality decisions.
- **Local execution plane:** PowerShell, Python, Node.js, FFmpeg/ffprobe, local specialist models and production renderers execute repeatable work.

Mandatory routing: **reuse/cache → deterministic local code → local specialist model → bounded agent reasoning → larger reasoning only if justified.** Batch work, persist state in files, invalidate only affected stages, summarize logs locally and stop after two failures using the same method.

## Production pipeline
1. Brief and success criteria.
2. Evidence-backed research, source notes and rights review.
3. Script, narrative structure, hooks and claim-level fact checks.
4. Voice generation/import; preserve source audio.
5. Local transcription and timing where required.
6. Narration-anchored EDL and cleaned timeline.
7. Reference-video analysis and production blueprint, when a visual reference is supplied.
8. Persistent visual language, storyboard approval and scene grammar.
9. Recipe selection and scene production.
10. Assembly of narration, visuals, music, effects and captions.
11. Technical QA, contact sheets, representative frame inspection and full playback.
12. Verified delivery and archived manifests, assets and decisions.

**Timeline integrity:** after cuts, all captions, B-roll, effects and audio must map to the cleaned timeline. Never reuse original timestamps without applying the edit mapping.

## Technology responsibilities
| Responsibility | Default |
|---|---|
| Primary motion | HyperFrames + GSAP |
| Specialist React/data scenes | Remotion selectively |
| 3D / technical visuals | Blender + Three.js |
| Media processing / final assembly | FFmpeg + ffprobe |
| Local transcription | faster-whisper |
| Offline narration candidates | Chatterbox + IndicF5 |
| Image enhancement | Upscayl |
| Automation | PowerShell, Python, Node.js |

Do not add a renderer merely because a skill bundles one. Preserve working integrations. Final renders must not depend on remote fonts, CDNs or network services.

## Reference Intelligence Engine — approved design, not yet implemented
Study [ReelMimic](https://github.com/edenfunf/reelmimic) selectively. Its source demonstrates a reference-analysis → style plan → user approval → parallel shot production → independent review → final critique workflow. It also provides a useful direction for measurable reference fingerprints across camera movement, rhythm, look, tension/peaks and frame summaries.

**Adopt:** local reference analysis, shot segmentation, camera/motion and look summaries, audio/beat cues, versioned fingerprints, storyboard-to-reference shot mapping, approval-first planning, file-contract-driven resumable stages, isolated parallel shot work, fresh-context reviewers and before/after evidence for fixes.

**Do not adopt wholesale:** ReelMimic's app/server as a second orchestrator, its 2D-only renderer collection, or its default agent permission configuration. Keep our existing HyperFrames + GSAP, selective Remotion, Blender + Three.js and FFmpeg responsibilities. Treat similarity scores as advisory until validated against human-labelled clips.

**Hard exclusions:** the inspected upstream revision includes yt-dlp in `requirements.txt`, `analyze.py`, `SKILL.md` and `AGENTS.md`. Do not install or execute it as-is. The studio's adapter accepts user-supplied local files only and must contain no yt-dlp dependency or URL-download path. Upstream uses the user's Claude Code/Codex account for inference; local execution is not equivalent to fully local inference. Do not inherit its documented `danger-full-access` Codex default.

Target flow: **local reference file → versioned analysis report + contact sheets → reference fingerprint → storyboard with reference-shot mapping → user approval → our existing renderers → shot QA and final comparison.** Cache by source hash, analysis version and settings. Preserve reference provenance and rights. See [ReelMimic Adoption Assessment](REELMIMIC_ADOPTION.md) for source findings, staged implementation and acceptance criteria.

## Animation Recipe Engine — approved design, not yet implemented
Selectively port six recipe families from [artemnovitckii/claude-animation-skills](https://github.com/artemnovitckii/claude-animation-skills): 3D explainer, stick figure, minimal graphics, map route, exploded breakdown and animated graph. These are scene-design patterns, not a new rendering runtime. HyperFrames + GSAP remain primary; Three.js/Blender are used only where justified. Do not run its macOS/Linux Bash setup unchanged on Windows.

Target contract: **agent selects recipe → versioned JSON scene spec → deterministic local renderer → contact sheet + QA report → agent reviews exceptions.** Schema should capture recipe/version, canvas, duration/FPS, objects, timing, camera, labels, assets, animation parameters, narration anchors and validation rules. Cache using stable inputs, recipe and renderer versions, and relevant settings.

Pilot one graph recipe and one breakdown or map-route recipe. Compare with hand-authored scenes for quality, determinism, render time, dependencies and token usage. Do not promote until Windows tests and human review pass.

## Code-review skill — advisory pilot
Evaluate [kyy-logs/code-review-skill](https://github.com/kyy-logs/code-review-skill) at a pinned revision for meaningful/high-risk diffs in both agent workflows, not every trivial edit. Its four fresh-context probes cover behaviour, tests, repository rules and impact. Treat results as advisory: probes are not independent models or human adjudication. A pass is not proof and must never auto-merge. Retain tests, CI, security review and human approval.

Test a small diff, multi-file refactor and intentionally seeded defect. Record misses, false positives, reproducibility, host compatibility and invocation cost.

## Storyboard QA — independently implement useful patterns
Borrow useful patterns from [konlu/story-studio](https://github.com/konlu/story-studio): narration/audio-first timing, persistent visual references, narration-anchored shot rows and semantic script-to-shot checks. Independently implement these patterns with local transcription. Do not copy code or corpus until the CC BY-NC-SA root licence versus MIT README wording is resolved. Do not use paid TTS or hosted image generation. Treat sample scripts as inspiration, not verified facts.

## Other evaluated skills
- [Ray Sticker Shop](https://github.com/imraywang/ray-sticker-shop): separate potential sticker-pack workflow, not a video-studio dependency; not offline-first.
- [Medical Paper Skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills): exclude; unrelated medical-academic workflow with a PolyForm Noncommercial licence.

## Promotion gates
| Pilot | Evidence required |
|---|---|
| Reference Intelligence | Local-file-only Windows analysis, no yt-dlp/network ingestion, versioned/cacheable reports, useful shot/camera/rhythm/look metrics, human-validated comparisons, offline tests |
| Animation recipes | Windows setup, offline render after approved downloads, deterministic outputs, contact sheets and human approval |
| Code review | Pinned revision, seeded-defect test, measured misses/false positives, host compatibility; advisory only |
| Storyboard QA | Local transcription, correct timeline anchors, visual consistency, semantic usefulness and repeatable outputs |

Record revision, environment, commands, test media, outputs, limitations and promotion decision. A smoke test is not editorial-quality proof.

## Non-negotiable constraints
- Offline-first and free/open-source by default.
- No paid inference APIs, hosted generation credits, cloud uploads or subscriptions by default.
- **No ComfyUI. No yt-dlp.**
- No silent renderer replacement or bulk skill installation.
- No remote runtime dependency in final renders.
- Respect code, model, font, image, music, sound and 3D-asset licences separately.
- Preserve asset provenance and rights evidence.
- No uploading media, scripts, voice samples or private content without explicit approval.
- Human review remains mandatory for factual accuracy, editorial judgement and final quality.
- Never describe planned helpers, pilots or integrations as installed or validated until tested.

## Change control
When a decision changes, update this playbook, affected agent handovers, architecture, roadmap, token policy and changelog together. Prefer reviewable commits. Never weaken permanent constraints without explicit approval.
