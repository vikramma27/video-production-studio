# Story Foundry Landing Experience — v5.1

## Purpose
The GitHub Pages landing page is an interactive editorial front door for the v5 two-channel storytelling studio. It should feel like entering a creative facility, not reading a generic SaaS feature page.

## Experience architecture
1. **World entrance:** cinematic title and abstract original character silhouette.
2. **Two-world switcher:** channel A/B identity panels. These are conceptual profiles, not approved character assets or names.
3. **Identity explorer:** interactive warmth, performance energy, stylisation and palette controls. The preview is illustrative and never writes to production specifications.
4. **Discipline switcher:** character DNA, voice identity, brand, story universe and reference intelligence.
5. **Production map:** six gates from reference analysis through local rendering, with human approval points visible.
6. **Organisation index:** direct links to all v5 blueprint documents.
7. **Truth/status statement:** makes clear v5.0 is an approved blueprint; engines and interfaces remain to be implemented and tested.

## Visual direction
- Dark editorial foundry environment, acid-lime and ember accents, large typographic hierarchy, grid/technical motifs, original inline SVG silhouettes.
- Avoid generic SaaS cards, gradients-as-decoration, fake dashboards, fake metrics and stock imagery.
- Distinguish the two channel identities using different accent palettes and separate creative profiles.
- Responsive layout from mobile to desktop; mobile navigation is a native button.
- No remote font, script, image or runtime dependency. Use system font fallbacks and inline SVG.
- No autoplay motion. Respect reduced-motion preferences.

## Interaction contracts
- Channel switcher changes the world profile, labels, palette and original inline silhouette.
- Identity explorer updates a concept preview only; it must never imply persistent storage or a real production asset.
- Discipline tabs update the associated specification panel.
- Repository document cards navigate directly to the canonical Markdown sources.
- Every navigation/action control must work with keyboard and touch; focus states remain visible.

## Content truth
- Benchmark channels are production-quality references only, not source identities to copy.
- Original characters, narrator profiles, names, handles, logos, channel art and thumbnail language require user review and explicit approval.
- Frozen identities are versioned and cannot silently drift.
- Final video visuals are original code-authored/generated; reference material remains analysis-only.
- User retains manual publishing and scheduling.
- No ComfyUI. Local-first/free/open-source by default; Suno is the narrow, previously approved music-composition exception.

## Acceptance checklist
- [x] Channel A/B switcher communicates distinct identities.
- [x] Identity controls update the preview and state that values are temporary.
- [x] Discipline tabs update the correct content.
- [x] All nine specification links resolve in the repository.
- [x] Mobile navigation and responsive controls are present.
- [x] No remote assets or external runtime dependencies.
- [x] Reduced-motion support; no essential information depends on motion.
- [x] Status copy does not claim planned engines are already implemented.
- [ ] Visual QA on GitHub Pages across desktop and Android mobile browsers.
