# Reference Reverse-Engineering Engine

## Canonical benchmark channels
- His Story: https://www.youtube.com/@hisytstory
- Her Story: https://www.youtube.com/@herytstory

Resolve and persist canonical channel IDs during implementation; handles can change.

## Discovery and ranking
Collect public video metadata and dated performance snapshots. Rank using a transparent combination of lifetime views, views per hour/day since publication, performance relative to each channel's own baseline, format/duration cohort, recency and outlier score where the data provider exposes methodology. Public metrics are snapshots, not private analytics.

Select a balanced sample: top-performing, recent, typical, Shorts, long-form and multiple emotional genres. Initial target: 20–30 videos per channel, then expand by evidence gaps.

## Shot-by-shot analysis contract
For each video, create:
- video_reference.json: source URL/ID, metadata, metrics snapshot, collection timestamp, provenance and rights/access notes.
- shots.json: shot index, start/end, duration, scale, angle, camera motion, composition, character positions, action, expression, lighting, palette, transition, narration/dialogue, music/SFX cue and confidence.
- Timestamped contact sheet.
- style_fingerprint.json with recurring techniques and distributions.
- analysis_notes.md with uncertainty and original adaptation opportunities.

Use ffprobe/FFmpeg for authorized local media; local vision models or agent-assisted inspection for sampled frames; faster-whisper for speech timing. Cache by source hash, analysis version and settings.

## Rights and acquisition gate
Internet research and yt-dlp are allowed when useful, subject to applicable platform terms and rights. Download only with permission, rights or a lawful basis and using a permitted method. Otherwise inspect the public player, metadata or authorized excerpts. Never bypass DRM, authentication, geographic restrictions or access controls. Store references in references/analysis-only. Final-render manifests must reject these paths and hashes.

## Translate techniques, not expression
For every observed technique, record evidence timestamps, why it works, confidence, exceptions, original adaptation, planned renderer/animation implementation and QA metric. Adapt pacing patterns, lighting principles, shot scale and acting approaches, but create new staging, characters and camera compositions. Do not reproduce exact frames, scripts, character designs, logos or distinctive compositions.

## Thumbnail research
Record subject scale/placement, eye-line, silhouette, background contrast, crop safety, colour hierarchy, text density and visual promise. Build original thumbnails from our own rendered characters and environments. Never reuse, trace or closely reproduce reference thumbnails.

## Approval and acceptance
Outputs: benchmark report, timestamped shot library, contact sheets, style maps and thumbnail-layout maps. User approves targets before character look development. Every recommendation must trace to source timestamps. Original adaptations require originality and human review.