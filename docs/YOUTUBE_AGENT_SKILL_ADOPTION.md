# YouTube Agent Skill — Adoption Assessment

**Decision: selective adoption for an isolated evaluation; do not install the full upstream pack or promote it to the production baseline yet.**  
**Reviewed:** 2026-11-12  
**Upstream:** https://github.com/Jakeschincariol/youtube-agent-skill  
**Licence reported by upstream:** MIT (verify exact pinned revision and included files before reuse).

## Executive decision

This project complements the studio rather than replacing any renderer. Its strongest contribution is the pre-production and post-publication intelligence layer: script/hook iteration, title-thumbnail consistency, transcript-based edit decisions, chapter validation, Shorts candidate discovery and channel-performance interpretation.

Adopt the methods and evaluate the small deterministic Python utilities. Keep Claude/Codex as the orchestration layer, local tools as repeatable workers, and the existing renderer stack unchanged. Do not install it globally, add another agent framework, or claim channel automation.

## Upstream inventory

The upstream README describes eleven skills:

| Skill | Studio decision | Integration boundary |
|---|---|---|
| yt-script | Evaluate/adapt | Hook alternatives and script structure; score is advisory only |
| yt-package | Evaluate/adapt | Title + thumbnail pairing lint; does not generate or validate actual artwork |
| yt-edit | Evaluate/adapt | Transcript/SRT to edit-decision-list suggestions; map to cleaned timeline before use |
| yt-comment | Defer | Optional later; replies require human voice, moderation and safety review |
| yt-plan | Adapt selectively | Content calendar suggestions must respect approved channel DNA and operator capacity |
| yt-viral | Evaluate/adapt | Public listings only; treat outliers as research leads, not causal proof |
| yt-retention | Evaluate/adapt | Requires owner-provided YouTube Studio retention export; never invent missing data |
| yt-shorts | Evaluate/adapt | Candidate extraction only; final cut uses local FFmpeg/current renderers and human review |
| yt-seo | Adapt selectively | Descriptions/chapters metadata; tags are low priority and never a substitute for content quality |
| yt-chapters | Evaluate/adapt | Validate timestamps against actual final runtime and YouTube rules |
| yt-audit | Defer | Useful after enough owned-channel history exists; recommendations remain advisory |

The upstream README lists six standalone Python utilities: hook scoring, title/thumbnail lint, dead-air/retake cues, chapter validation, retention CSV analysis and public-video outlier analysis. It states these run on clean Python without third-party dependencies. Verify that claim against the pinned source before executing them in the Windows environment.

## What we should not import blindly

- Do not treat hook scores as a view/retention prediction. Upstream itself describes the score as heuristic and weak at separating one creator's hits from misses.
- Do not treat public view counts, title-formula labels or competitor outliers as causal evidence.
- Do not scrape private analytics or log into accounts. Use owner-exported CSVs unless a separately reviewed official integration is approved.
- Do not publish, schedule, reply to comments or alter channel settings automatically.
- Do not let suggested edits bypass the narration-anchored EDL, timeline remapping, visual-provenance checks or human playback.
- Do not use the upstream package's assumptions about cadence or formats as fixed rules for our two-channel strategy.
- Do not introduce hosted inference, API keys, external uploads or paid services into the default path.

## Proposed integration architecture

1. **Research intake:** record public research observations with URL, capture date, channel/topic, visible metrics, video age and uncertainty. Public data is not private analytics.
2. **Editorial brief:** generate multiple hooks and story structures, then human-select and fact-check. Preserve source notes and claim-level evidence.
3. **Packaging:** assess title/thumbnail as one promise. Thumbnail artwork remains original and code-authored/generated under the studio visual invariant.
4. **Narration and edit:** run local transcription; use edit-list suggestions as proposals. Apply cuts to a canonical cleaned timeline and remap every caption/shot/effect.
5. **Shorts discovery:** identify candidate ranges from long-form transcript/retention signals. Rebuild hooks and aspect-ratio composition; do not blindly crop a long-form frame.
6. **Metadata:** validate chapters against final runtime; generate descriptions and restrained query suggestions.
7. **Performance learning:** import owner-exported Studio CSVs and preserve snapshots over time. Compare videos against their own channel, format, topic and age cohorts where sample size allows.
8. **Next-episode feedback:** turn findings into testable editorial hypotheses, not automatic channel identity changes.

## Windows evaluation plan

Run in a disposable project-local environment, not a global Claude/Codex skill directory.

- Pin a commit SHA; archive the upstream README, licence and selected skill files with the evaluation record.
- Review every Python script and skill instruction for subprocess, filesystem, network, credential, prompt-injection and data-exfiltration behaviour.
- Verify Python version, paths with spaces/non-ASCII, CRLF/LF handling, malformed SRT/CSV, empty inputs and Unicode/Tamil text.
- Use synthetic fixtures first; then owner-provided, non-sensitive sample exports.
- Test all six utilities: expected outputs, invalid input behaviour, deterministic reruns and no network access.
- Compare generated EDL timestamps with a known cleaned timeline; ensure chapters fit the final duration.
- Measure useful findings, false positives, missed issues, execution time and human correction time.
- Do not store OAuth tokens, cookies, browser profiles or account secrets in the repository.

## Acceptance gates

- [ ] Exact upstream commit SHA and MIT licence file reviewed.
- [ ] All imported files and scripts listed in a provenance manifest.
- [ ] Static review finds no unapproved network calls, credential access or unsafe writes.
- [ ] Six utilities pass deterministic Windows tests with fixture inputs.
- [ ] Tamil/English transcription and Unicode paths are handled safely where applicable.
- [ ] EDL outputs map correctly to the cleaned timeline.
- [ ] Hook/title/thumbnail scores are explicitly labelled heuristic/advisory.
- [ ] Retention insights require a dated, owner-exported source file.
- [ ] No publishing, scheduling, comment replies or channel mutations occur.
- [ ] Human editorial approval and final full playback remain mandatory.

## Promotion rule

Promote only individual utilities/skills that show measurable quality or time savings on representative studio episodes. A green test, popularity or MIT licence alone is insufficient. Keep the upstream as an optional specialist reference, not a new orchestrator or renderer.

## Sources

- https://github.com/Jakeschincariol/youtube-agent-skill
- https://raw.githubusercontent.com/Jakeschincariol/youtube-agent-skill/main/README.md
