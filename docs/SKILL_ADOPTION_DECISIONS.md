# Skill Adoption Decisions — 2026-11-09

| Repository | Decision | Boundary |
|---|---|---|
| [claude-animation-skills](https://github.com/artemnovitckii/claude-animation-skills) | Selectively port six animation recipes | HyperFrames + GSAP remain primary; no second renderer; adapt for Windows |
| [code-review-skill](https://github.com/kyy-logs/code-review-skill) | Pilot in both agent workflows | Meaningful/high-risk diffs only; advisory; never auto-merge |
| [story-studio](https://github.com/konlu/story-studio) | Independently implement useful patterns | Audio-first storyboard, visual references, semantic QA; no copying until licence discrepancy clarified |
| [ray-sticker-shop](https://github.com/imraywang/ray-sticker-shop) | Separate future product idea | Not an offline video-pipeline dependency |
| [dyz-med-paper-skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills) | Exclude | Unrelated and PolyForm Noncommercial |

## Promotion gates
1. Review source, exact revision, licence, dependencies and network calls.
2. Validate Windows compatibility and offline behaviour after approved downloads.
3. Run representative tests and preserve outputs.
4. Inspect frames and full playback; evaluate misses/false positives for code review.
5. Record revision, environment, commands, results and limitations.
6. Mark installed/active only after actual integration and validation.

These are documented decisions and pilot backlog, not claims of installed skills or runtime automation.
