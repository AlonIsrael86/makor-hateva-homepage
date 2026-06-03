# DESIGN.md — Makor Hateva (מקור הטבע) Homepage

## Objective
A premium, warm, heritage-credible Hebrew/RTL homepage for Makor Hateva — central solar
water-heating systems for apartment buildings and private homes, founded 1963. The page must
make a building committee (ועד בית) feel that this is the vendor who has quietly kept hot water
running for 60 years and will answer the phone for the next 60. Primary conversion: book a free
on-site visit + consultation (ביקור וייעוץ ללא עלות) by form, phone, or WhatsApp. Editorial Roei Deutsch /
Wiz line — category-led, one ownable metaphor, meaningful motion — never generic SaaS.

## Audience
Building committees and house reps; private-home builders and contractors. Non-technical,
risk-averse, value reliability, longevity, fair per-apartment metering, fast real service, and a
named human who picks up. They are persuaded by proof of heritage, named manufacturers, written
warranty, and "it just works," not by feature lists or hype.

## References
| Reference | What To Learn | What Not To Copy |
|---|---|---|
| Wiz.io | Category-before-UI hierarchy, one carried metaphor, frame-breaking motion at section edges | The dark neon cyber palette; it's a security brand, not a heritage trades brand |
| SolarEdge / Israeli solar leaders | Domain credibility, technical proof shown early | Sterile corporate stock-photo feel, cold blue-only palette |
| Stripe / Linear | Restrained, meaningful micro-motion; premium micro-detail | SaaS-dashboard aesthetic; English-LTR rhythm |
| Heritage Israeli utility/craft brands (1960s-rooted) | Warmth + longevity signaling, "trusted for decades" tone | Dated, low-contrast visuals; literal retro pastiche |

## Visual Theme
Warm engineering trust. Deep navy ground + a living amber "heat" that flows through the page.
Editorial, confident, a little hand-made (brush accents, original SVG diagram), never sterile.
Atmosphere: late-afternoon rooftop sun on collectors — premium but human. The page should feel
like it radiates a low warmth from the screen.

## Color System
| Token | Hex | Semantic role |
|---|---|---|
| --navy | #002F5E | Primary brand ink; dark section base |
| --navy-deep | #001B38 | Deepest background — header, trust, footer |
| --navy-700 | #0A3A6B | Mid navy, gradients, card surfaces on dark |
| --blue | #0077C0 | Secondary / cool-return flow / links |
| --orange | #FF6000 | Lead accent — CTAs, heat-supply, primary energy |
| --orange-deep | #C00000 | CTA depth, gradient anchor, error |
| --amber | #FFB23E | Warm highlight — sun, numerals, the flow-line, focus ring |
| --surface | #F6F8FB | Light section background |
| --surface-2 | #EAF0F6 | Light controls / FAQ icon idle |
| --ink | #0E1C28 | Body text on light |
| --muted | #586A7A | Secondary text |
| --line | #DBE3EC | Borders, hairlines |
| --white | #FFFFFF | Cards, light text on dark |

Metaphor mapping: heat/supply = orange→amber; cool/return = blue; ground/trust = navy.
Lead color = orange; single bold accent = amber. No other hues.

## Typography
- Display: "Suez One" (single weight 400). Body: "Heebo" (400-900).
- Load: `https://fonts.googleapis.com/css2?family=Heebo:wght@400;500;600;700;800;900&family=Suez+One&display=swap`
- `--display:"Suez One",Georgia,serif;  --body:"Heebo",-apple-system,"Segoe UI",sans-serif;`
- Suez One ONLY on: hero H1, section H2, `.stat-big`/`.hero__stats` numerals. Everything smaller
  (card H3, FAQ Q, footer H4, step H3, why H3) = Heebo 800. Build hierarchy with size + amber, not weight.
- Hebrew/RTL tuning: headline line-height 1.12-1.16, letter-spacing -0.005em large-only, never
  tracking-wide, no uppercase/capitalize. Body line-height 1.7, base 18px (min 16px), spacing 0.
- Numerals LTR-isolated. Accent words use a hand-drawn amber underline SVG, not gradient-clip text.

## Layout Rules
- Container max 1220px; `--pad-inline:clamp(18px,5vw,68px)`; logical properties only (ms/me/ps/pe,
  inset-inline-*). Never left/right.
- Section rhythm (fixed order): Hero -> Trust strip -> Services (3) -> Why (6) -> How/Proof diagram ->
  Stats/Heritage band -> Contact -> FAQ -> Footer.
- Section padding `clamp(64px,8.5vw,116px)`. One warm amber glow per section at a consistent edge.
- Hero content column max 660px, anchored to inline-start (right in RTL). Zero horizontal overflow
  at 360/414/768/1024/1440 (overflow-x:clip as a safety net, not a crutch).

## Component Rules
- Buttons: pill, primary = orange->orange-deep gradient with shine-sweep on hover, min-height 54px,
  2-3 word Hebrew labels. Ghost = white outline glass on dark.
- Cards (.svc): white, 1px --line, watermark Suez One numeral bleeding off top corner, amber
  flow-line top-rule that fills on hover, hover lift translateY(-7px). H3 = Heebo 800 navy.
- Trust wordmarks: aged-nameplate chips (border + inset highlight), not flat text.
- Forms: surface inputs, amber focus ring (not blue), required marked with amber asterisk; success
  state reuses the brand sun Lottie. Always validate before the WhatsApp continue.
- Header: fixed navy-glass (blur), solidifies on scroll; logo on frosted backing so it always reads.
- Footer: centered everything — columns text-align:center, bottom row stacked + centered, amber
  flow-line divider, centered sun + "מאז 1963" signature mark.
- The amber flow-line (dashed, animated) is the shared connective motif: eyebrow rule, card top,
  stats timeline, FAQ dividers, footer sign-off.

## Motion System
- Purpose only: motion must explain (heat flow), reveal hierarchy, or reward action — never decorate.
- Assets: (1) brand sun-radiance Lottie (hero anchor, lottie-web SVG, loop, recolored to brand);
  (2) original animated heat-loop SVG (the proof — flowing supply/return + sequential boiler glow +
  temperature tags); (3) amber flow-line draws (stroke-dashoffset / background-position); (4) reveal
  stagger, count-ups, hover lifts, CTA shine. All transform/opacity only.
- Performance: never make Lottie the LCP; IntersectionObserver-gate; one or two animations active
  on mobile. Reserve layout (aspect-ratio boxes) — zero CLS.
- prefers-reduced-motion: freeze the Lottie on a representative frame; disable sun rays, flow,
  boiler glow, count-ups, brush draw; reveals show immediately.

## Content Rules
- Voice: warm, plain, committee-friendly Hebrew. Short editorial headlines, manifesto-adjacent
  ("מים חמים לכל דייר. שקט נפשי לכל ועד."). No jargon, no English tech terms, no emojis in UI.
- Always factual: phones 054-480-2380 / 03-677-7935, email makorhateva1@gmail.com, address
  רח' עוזיאל 63 רמת גן, hours Sun-Thu 08:00-17:00, manufacturers כרומגן/אמקור/סנהדרין/אידיאל.
- Do NOT fabricate: ח.פ., review counts/stars, or unverified "500+" without sign-off. No fake metrics.
- Forbidden generic copy: filler superlatives, "הבחירה המושלמת", empty buzzwords.

## Responsive Rules
- Desktop >=1024: 3-col services/why, 4-col stats, 2-col how + contact.
- Tablet 768-1024: 2-col grids, stacked how/contact.
- Mobile <760: single column, hamburger drawer, 44px+ tap targets, hero min-height auto, sun
  opacity reduced and pushed to corner clear of text, scroll cue hidden, footer fully centered stacked.
- WhatsApp float bottom-inline-end; sticky tel/WhatsApp affordance reachable on mobile.

## Accessibility and SEO
- lang="he", dir="rtl", hreflang he-IL, semantic landmarks, skip link, amber visible focus ring,
  RTL tab order = reading order. WCAG 2.1 AA contrast (amber text only on navy, never on white).
- All alt/aria/placeholder in Hebrew. Phone/email/URLs wrapped LTR.
- Full meta (title/description/canonical/OG/Twitter/og:locale he_IL). JSON-LD: HVACBusiness
  LocalBusiness with geo (areaServed = named מרכז הארץ cities + coordinates), openingHours,
  foundingDate 1963, hasOfferCatalog of services, knowsAbout; WebPage w/ dateModified; FAQPage
  matching on-page Q&A. GEO/AEO: clear entity naming, real Q&A text on the page, answer-first blocks,
  speakable-friendly answers, llms.txt + robots (AI bots allowed) + sitemap shipped. noindex ONLY
  while it's a preview; drop on launch.

## Visual QA Checklist
- [ ] No orphan word on any heading/CTA/banner at 360/414/768/1440 (Range/getClientRects check).
- [ ] Hero eyebrow "מאז 1963" fully legible over the sun (navy-glass chip present).
- [ ] Logo reads on the frosted header at all scroll states; hero/desktop + mobile.
- [ ] Suez One only on H1/H2/big numerals; Heebo 800 on small headings; numerals not bidi-flipped.
- [ ] Footer centered (top columns + bottom row); flow-line + sun signature present.
- [ ] Heat-loop SVG flow + temperature tags animate and explain; reduced-motion freezes cleanly.
- [ ] Lottie renders (SVG nodes present), not LCP, IO-gated; zero horizontal overflow any width.
- [ ] Amber focus ring on inputs; form validates before WhatsApp continue.
- [ ] Screenshots captured: desktop 1440 full + hero, mobile 390 full + hero, live URL hero.

## Implementation Notes
- Stack: single-file vanilla HTML/CSS/JS, Hebrew RTL, deployed on Vercel (public repo), preview
  noindex via vercel.json. No framework — keep it one file for portability into Wix/host later.
- Asset ownership: sun Lottie hand-authored (brand-colored, local assets/energy-pulse.json);
  heat-loop SVG original; manufacturer names are text nameplates (no third-party logos). Pull final
  high-res rooftop/array photos from the client Wix once access is granted; replace hero.jpg.
- Risks: Suez One is single-weight — do not fake bold/light; rely on size + amber. Watch Hebrew
  legibility of Suez One at small sizes (that's why small headings use Heebo). Confirm ח.פ., hours,
  warranty wording, the "500+" claim, and the exact geo coordinates before launch; wire the form to
  a real endpoint.

## Round 5 updates (2026-06-03)
- Booking modal `#bookModal`: two-panel on desktop (navy editorial aside + white form); on mobile a compact bottom-sheet (`@media max-width:760px { .modal place-items:end }`) - aside bullets/since hidden, fits one screen, no blank space. Aside warm glow softened (diffuse, blurred) so it reads as ambient heat, not a pasted sun. Triggers: any `[data-book]` element (header CTA, mobile-nav CTA, hero CTA).
- Header logo uses `assets/logo-white.png` (white-subtext lockup) for legibility on the dark header - matches the footer logo.
- Trust/logos band: centered column always; star icon flows inline-centered with the label (no off-center push). 4 manufacturer logos shown (6 brands named in copy; Prat+Nimrod logos pending).
- Hero sun: animated - spinning rays + breathing disc (`@keyframes sunbreathe`) + low-opacity Lottie; disabled under `prefers-reduced-motion`.
- Favicon = sun only (`assets/favicon.svg` navy badge + gold sun; PNG fallbacks `favicon-32.png`, `apple-touch-icon.png`). OG/Twitter image = branded `assets/og-image.png` (1200x630, navy + sun + white logo + headline), rendered via `scripts/utils/makor-assets-gen.js`.
- WhatsApp links carry a friendly opener (`?text=...`) set at runtime on all static `wa.me` links; form-success links override with a contextual text on submit.
- Icon consistency: hero primary (arrow) and hero phone (phone icon) both lead on the right (RTL leading edge); mobile-nav phone is a ghost button with the icon on the right.

## Round 6 updates (2026-06-03)
- **Hero now two-column** (`.hero .container.hero__grid`): editorial text on the right (RTL start), a **device-framed portrait video on the left** showing the company's REAL field footage (`assets/field-video.mp4`, his actual Wix home video, 9:16). Rounded frame (`.hero__media-frame`, radius 28px, warm 1px border + soft shadow + inner ring), glass caption chip "מהשטח · מערכת אמיתית" with a glowing live dot, soft radial glow behind. Reveals on load, plays only while in view (IntersectionObserver), `preload=none` + poster (`field-poster.jpg`) so it never blocks LCP; gated by `prefers-reduced-motion` + `saveData`.
  - Reference (Mobbin, web): **TikTok for Business "You are here"** — portrait video framed beside the headline; and **Savee** — portrait video left, text right. Adopted the device-framed-portrait-beside-headline principle, not the assets.
  - The decorative `.hero__sun` is **hidden on desktop (>900px)** because the real video now owns the hero-left visual zone; the sun still shows on mobile/tablet (stacked layout), where the portrait video drops to a centered card after the stats.
  - **Stock background montage removed from motion**: `heroVid` no longer autoloads; hero background is the calm rooftop still (`hero.jpg`). One meaningful motion (real footage) instead of two competing videos.
- **Two-sun differentiation** (mobile): the top-left `.hero__sun` is an animated radiant sun (rotating rays re-enabled small + breathing disc); the eyebrow `.sun-dot` is a small flat marker that glows (`@keyframes dotglow`) — distinct treatments so they don't read as the same circle twice.
- **Mobile header logo** hugs the right (RTL start); fixed the `.brand{margin-inline-start:auto}` vs `justify-content:space-between` conflict with `.brand{margin-inline-start:0}` on mobile. Scrolled logo shrinks less (46px).
- **All 6 manufacturer logos** now in the trust strip (Prat + Nimrod sourced from their official sites; Prat cropped from its black-bg badge to the core sun-disc for legibility at 36px).
- Video asset pipeline: sourced from the public live site (Playwright network capture of `video.wixstatic.com/video/<id>/480p/mp4/file.mp4`), compressed with ffmpeg to 3.5MB h264 (no audio, faststart) + JPG poster. Script reference: ad-hoc ffmpeg in `assets-from-wix/home-video/`.
