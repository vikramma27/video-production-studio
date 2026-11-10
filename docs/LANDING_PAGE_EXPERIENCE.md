# Landing Page Experience — v5.3 Production Atlas

## Product intent
The landing page is the public front door to the Video Production Studio repository. It should feel like an independent animation and film atelier with a documented operating system—not a SaaS dashboard, generic AI landing page or portfolio template.

## Design philosophy: Frame / Foundry
- **Visual identity:** warm archival-paper canvas, deep ink, signal orange, restrained cobalt and sage. Editorial serif display typography contrasts with compact technical mono labels.
- **Composition:** asymmetric two-column opening, an original illustrated film-frame, oversized editorial typography, horizontal manifesto strip, full-bleed dark renderer lab, modular production sequence and an index-like document library.
- **Visual language:** original inline SVG character studies, film-frame borders, registration rings, typographic hierarchy and deliberate negative space. No stock imagery, remote fonts, remote scripts, icon libraries or runtime CDN.
- **Responsive behaviour:** desktop two-column compositions collapse to touch-first single-column sections; navigation becomes a real disclosure button; grids adapt without horizontal overflow.
- **Motion:** only small interaction transitions; no autoplay, parallax or motion-dependent content. Reduced-motion preferences remove transitions and smooth scrolling.

## Information architecture
1. **Opening statement:** “Stories, built from the frame up.” Clearly communicates the two-channel, code-first studio.
2. **Two original worlds:** interactive A/B switcher. Profiles are conceptual; characters and voices remain candidates until user approval and explicit freeze.
3. **Production engines:** interactive engine selector for Remotion, HyperFrames + GSAP, Blender + Python, Three.js and FFmpeg/ffprobe.
4. **Cinetic specialist:** clearly labelled controlled pilot, with 34-scene Remotion starter noted as untested/uninstalled.
5. **Operating method:** six stages from reference intelligence through local production, with originality and approval gates.
6. **Latest decisions:** v5.2 Remotion first-class decision, Cinetic pilot boundary, Blender/3D and local operations.
7. **Blueprint library:** searchable links to the master playbook, architecture, two-channel specs, Cinetic assessment, skill register, roadmap and Claude/Codex handovers.
8. **Production philosophy:** intelligence directs, deterministic local tools execute, human review remains mandatory.

## Interaction contracts
- Channel A/B switcher updates labels, descriptive copy, accent colours and inline SVG study.
- Engine selector updates engine role, current status, description and capability tags; Remotion and HyperFrames are explicitly co-equal first-class engines.
- Document search filters the document index and exposes a useful empty state.
- Mobile menu reports aria-expanded, closes after navigation and remains keyboard operable.
- No interaction writes to a production profile, saves data or claims to generate a production-ready character.

## Content and status truth
- Benchmark channels are production-quality references only; no identities, scripts, voices, logos or expressive assets are copied.
- Both channel protagonists and voice profiles are still subject to iteration and explicit user freeze.
- Remotion is a first-class engine under the current solo-operator licence decision, subject to its official terms and future ownership/team reassessment.
- HyperFrames + GSAP is equally first-class; choose per scene.
- Cinetic is approved for a controlled launch/update-film pilot only. It is not installed; its 34-scene starter has not been tested on Windows.
- Blender + Python is the original 3D production path; Three.js is specialist; FFmpeg/ffprobe handles assembly and QA.
- The v5.0/v5.2 documents define approved direction and pilots, not completed software integrations.
- Final visuals are code-authored/generated; no stock/static photos, downloaded clips or generic B-roll.
- Local-first/free/open-source by default; Suno remains the narrow, user-approved music exception.
- Publishing/scheduling remains manual.

## Accessibility and performance
- Semantic header, navigation, main, sections, article and footer landmarks.
- Descriptive accessible names on interactive controls; aria-pressed, aria-expanded, and live region for engine detail.
- Visible keyboard focus, native buttons/links, labelled search field and accessible empty state.
- Responsive breakpoints at 900px and 640px; system font stacks; no remote assets.
- Reduced-motion support and no essential information conveyed only by animation.

## Critique pass and changes applied
A separate adversarial design/implementation review was performed after the initial build. Findings and disposition are recorded in [Landing Page Critique v5.3](LANDING_PAGE_CRITIQUE_V5_3.md). A separate Notion Custom Agent could not be spawned because the connected workspace's agent-search capability requires a Business plan or higher; no external parallel agent review is claimed.

## Acceptance checklist
- [x] Complete visual direction replaced; no reuse of the former dark lime/coral dashboard aesthetic.
- [x] Opening, navigation, content hierarchy, production-engine presentation and document library redesigned.
- [x] Remotion + HyperFrames co-equal status included.
- [x] Cinetic 34-scene pilot status and caveats included.
- [x] Two-channel story blueprint and character/voice approval gates preserved.
- [x] Searchable documentation library and direct source links included.
- [x] No external fonts, scripts, images, libraries or CDN dependencies.
- [x] Mobile navigation, responsive grids, keyboard focus and reduced-motion behaviour included.
- [x] No fake metrics, fabricated completion states or automatic publishing claims.
- [ ] Verify final deployment on GitHub Pages and inspect on desktop and Android mobile browsers.
