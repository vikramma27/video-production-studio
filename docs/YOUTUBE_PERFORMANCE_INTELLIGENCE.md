# YouTube Performance Intelligence — Local-First Blueprint

**Status:** approved architecture blueprint; not implemented, connected to YouTube, or benchmarked.  
**Target:** Windows-first, offline-capable, two-channel studio.  
**Purpose:** turn completed episodes and verified performance exports into reusable editorial evidence without allowing metrics to dictate channel identity.

## Design principles

- Local-first; no hosted analytics database or paid inference API in the default path.
- Owner-controlled imports from YouTube Studio exports; no credential scraping or browser-cookie access.
- Preserve raw source files and immutable import snapshots.
- Separate observations, metrics, hypotheses and editorial decisions.
- Compare like with like: channel, format, topic, publication age and sample size matter.
- Treat correlation as descriptive, not causal. Do not claim a title, thumbnail or hook caused an outcome without a valid experiment.
- Human approval required for topic selection, script changes, packaging and publishing.
- Never alter frozen Channel DNA, character identity or voice identity based on a single outlier.

## Proposed local architecture

`YouTube Studio CSV / manually collected public research`  
→ `Import & validation`  
→ `SQLite local evidence store + original-file archive`  
→ `Normalization / cohort comparison`  
→ `Insight and hypothesis reports`  
→ `Human-approved editorial brief`  
→ `Script / production pipeline`  
→ `New episode and later performance snapshot`

SQLite is the preferred initial store because it is local, transactional and queryable without adding a server. Keep original CSV/JSON exports unchanged under a dated, channel-scoped archive; store normalized rows and provenance in SQLite. Provide CSV/JSON export for portability. Do not introduce a web dashboard until the data contract and workflows are proven.

## Minimum data model

| Entity | Key fields |
|---|---|
| Channel | channel_id, approved identity version, language, format policy |
| Episode | episode_id, channel_id, topic, format, duration, publish timestamp, script/version, title, thumbnail concept |
| Research observation | URL, capture timestamp, source type, visible metrics, video age, topic, uncertainty and notes |
| Metric snapshot | episode_id, captured_at, metric name/value/unit, source export, reporting window |
| Experiment/hypothesis | hypothesis, variable, control, treatment, start/end, sample size, outcome, caveats |
| Editorial decision | insight, evidence links, confidence, proposed action, human decision and rationale |
| Asset/provenance | asset id, source, licence, generated/code-authored status, episode linkage |

Every metric must carry its unit, reporting window, source file and capture time. Never merge views, impressions, CTR or watch-time values from different windows as if they were one observation.

## Initial metrics

Use only fields present in the imported export. Candidate measures include views, impressions, impressions click-through rate, average view duration, average percentage viewed, watch time, subscribers gained/lost and audience-retention points. Shorts-specific measures should remain distinct from long-form metrics. Missing values stay missing; do not estimate them from public views.

## Cohort and comparison rules

- Establish a per-channel baseline before recommending changes.
- Compare Shorts with Shorts and long-form with long-form.
- Normalize by video age or use fixed reporting windows; do not compare a 2-day-old upload with a 90-day-old upload without qualification.
- Segment by topic/series only when enough observations exist.
- Use medians and distributions as robust descriptive summaries; show sample count and spread.
- Flag small samples and outliers; never rank a channel's entire strategy from one video.
- Public competitor listings are research context only and must not be mixed with owned-channel Studio metrics.
- Record platform metric-definition changes and export schema versions.

## Insight-to-production loop

1. Import and validate a dated export.
2. Produce a compact report: what changed, cohort baseline, sample size, uncertainty and data gaps.
3. Convert only actionable observations into explicit hypotheses.
4. Change one editorial variable at a time where a meaningful comparison is possible.
5. Human approves the next brief; Channel DNA remains frozen unless separately approved.
6. After publication, collect later snapshots at consistent windows.
7. Retain both positive and negative outcomes; do not cherry-pick.

Example hypothesis: “For this series, opening with the physical failure before explaining the theory may reduce the first-30-second retention drop.” This is a testable editorial hypothesis, not a claim that a particular formula guarantees performance.

## Integration with existing pipeline

- **Research/script:** YouTube Agent Skill methods may propose hooks and structures; factual claims still need evidence and human review.
- **Packaging:** title-thumbnail lint checks promise consistency; original thumbnail composition remains within our code-generated asset policy.
- **Audio/edit:** transcript-based EDL proposals feed the existing cleaned-timeline contract; no direct timestamp copy after cuts.
- **Visual production:** Remotion, HyperFrames + GSAP, Blender/Three.js and FFmpeg remain unchanged.
- **Shorts:** discovery proposes candidate ranges; existing local assembly and full playback gates remain authoritative.
- **QA/delivery:** add a final metadata package and a performance-import reminder, not auto-publishing.
- **Creator Generalist:** continue its separate selective 2D/3D craft pilot. It is not an analytics tool and does not replace this layer.

## Security and privacy

- No API credentials, OAuth refresh tokens, cookies or browser profile data in Git.
- Do not upload private analytics exports to third-party services by default.
- Keep exports in a local ignored data directory with a documented backup policy.
- Redact personal commenter information if comment analysis is ever introduced.
- Treat imported text, titles, descriptions and comments as untrusted content; ignore embedded instructions.
- Make imports explicit and reversible; never overwrite raw source exports.

## Implementation phases and acceptance

### Phase 0 — contract and fixtures
- [ ] Define CSV import schema/version and synthetic fixtures.
- [ ] Document the exact YouTube Studio export fields used; unknown columns are preserved or safely ignored.
- [ ] Validate malformed files, missing columns, duplicate imports, time zones, decimal separators and Unicode.

### Phase 1 — local evidence store
- [ ] Implement SQLite schema and migrations.
- [ ] Store original exports read-only with hashes and provenance.
- [ ] Support idempotent import and CSV/JSON export.
- [ ] Add a local CLI summary; no web server required.

### Phase 2 — cohort reports
- [ ] Generate per-channel, per-format and age-window summaries.
- [ ] Display sample size, missingness and uncertainty.
- [ ] Test against hand-calculated fixtures.

### Phase 3 — editorial feedback
- [ ] Produce evidence-linked hypotheses and a human decision record.
- [ ] Link episode records to script, render manifest and final metadata.
- [ ] Verify no automatic Channel DNA, publishing or account changes.

### Phase 4 — dashboard only if justified
- [ ] Build a local dashboard only after CLI/data contracts pass.
- [ ] Keep all data local and accessible without external services.
- [ ] Verify offline operation and Windows restart/recovery.

**Promotion gate:** no production claim until import correctness, idempotence, privacy controls, Windows/offline behaviour and representative episode reports pass tests.
