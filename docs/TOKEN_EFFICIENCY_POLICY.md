# Permanent token-efficiency policy

<aside><strong>Status: permanent architectural rule — non-negotiable default.</strong></aside>

## Core rule

Claude Code and Codex are the brains of the production studio, not the workers performing every repetitive operation. The agent reasons, plans, directs, creates reusable automation and handles exceptions. Deterministic local tools and specialist local models perform routine work.

This rule must not be weakened or bypassed without explicit user approval.

## Mandatory routing gate

Before every operation, ask in this order:

1. Can an existing output or valid cache be reused?
2. Can a deterministic local script or CLI tool do it reliably?
3. Can a local specialist model do it adequately?
4. Is agent reasoning genuinely required?
5. Does the task justify a large reasoning call?

If local execution is reliable, do not spend hosted-agent tokens on that operation.

## Agent responsibilities

- Creative direction, story and editorial judgement.
- Planning, architecture and technical trade-offs.
- Ambiguous language or contextual reasoning.
- Diagnosing exceptions after deterministic checks.
- Designing reusable scripts and tests.
- Reviewing representative outputs and making bounded corrections.

## Local worker responsibilities

- File discovery, hashing, copying and organization.
- Media probing and metadata extraction.
- Batch conversion, trimming, muxing and encoding.
- Subtitle format conversion and deterministic alignment transforms.
- Contact sheets, thumbnails, waveform/metadata reports.
- Template-driven motion rendering and repeatable scene generation.
- Preflight, lint, validation and output checks.
- Cache management and manifests.

## Execution standards

- Batch operations instead of drip-feeding one file at a time.
- Cache by stable inputs, tool versions and relevant settings.
- Keep stages independently rerunnable.
- Use event-driven triggers where practical; avoid wasteful polling.
- Persist project state and decisions in files, not oversized chat context.
- Send the agent compact summaries, diffs and exception reports—not entire media inventories.
- Do not fabricate token usage or claim savings without measurement.
- After two failures with the same method, stop and diagnose rather than repeating blindly.
- Keep human review for factual claims, editorial judgement and final quality.

## Proposed helper backlog

These are planned implementation items, not installed runtime enforcement:

- `scripts/preflight.ps1`
- `scripts/probe-media.ps1`
- `scripts/hash-assets.ps1`
- `scripts/validate-project.ps1`
- `scripts/build-contact-sheet.ps1`
- `scripts/qa-render.ps1`
- `scripts/run-stage.ps1`
- `scripts/summarize-failures.ps1`
- `PROJECT_STATE.md`, `DECISIONS.md`, `STAGE_MANIFEST.json`, `ASSET_MANIFEST.json`, `QA_REPORT.md`

## Acceptance criteria

A workflow is compliant when routine work can run without hosted-agent calls, repeated stages reuse valid cache, failures are reported compactly, invalidation is selective, and agent calls are reserved for tasks requiring reasoning or judgement.
