# HANDOFF — Makor Hateva Homepage (owner: Nir)

This project is transferring to Nir for full ownership. This file is the contributor brief. Read `DESIGN.md` before any visual change.

## TL;DR
- Premium Hebrew/RTL homepage redesign for **Makor Hateva** (מקור הטבע).
- Single-file static site. **Deploy = `git push origin main`** → Vercel auto-deploys. No Vercel account needed.
- Current phase: **logo-first reset**. The homepage build is **paused** until the client approves a new logo. Do not resume the homepage layout work until the logo direction is locked.

## What the business is (read first — common mistake)
Makor Hateva is a **solar WATER-HEATING** company. Rooftop solar systems for apartment buildings (מערכות סולאריות מרכזיות), solar boilers (דודי שמש), electric boilers (דודי חשמל), plus repair/maintenance of existing systems. Founded **1963**, 2nd-generation family business (owner **Noam Avishar**). Mid-Israel service area.

It is **NOT** photovoltaic / electricity generation. Never describe it as solar panels that make electricity. Imagery must read Israeli (rooftops, apartment water-tank arrays, collectors).

Dual audience: (1) private homeowners (דודי שמש/חשמל), (2) building committees + maintenance companies (ועדי בית, central systems). Strong commercial angle: cheap repair/rehab of old systems instead of replacement. Google rating 4.9.

## Live URLs
- Homepage preview (noindex): https://makor-hateva-homepage.vercel.app
- Logo brand-deck (for the client meeting): https://makor-hateva-homepage.vercel.app/logos

## Stack
- Vanilla HTML / CSS / JS. No framework, no build step.
- `index.html` is the whole homepage. `logos.html` is the logo presentation page (served at `/logos`).
- Hebrew/RTL: `lang="he" dir="rtl"`. Type system + colors are defined in `DESIGN.md` (Roei Deutsch / Wiz premium line; navy + amber heat-flow metaphor).
- Assets in `assets/` (images, logos, brand lockups, favicon set).

## Deploy model (important)
- **Push to `main` → Vercel auto-builds and deploys.** That is the entire deploy flow.
- The repo is **PUBLIC on purpose. Do not make it private.** (Vercel's Hobby plan blocks deploys from non-owner commit authors on *private* repos; keeping it public means your pushes deploy with no Vercel account required.)
- You do **not** need any Vercel access. Pushing to GitHub is enough.
- Do **not** run the `vercel` CLI from this folder — it tries to upload large local video masters and errors. Use `git push` only.
- Stage explicit files. The repo ignores `.vercel`, `node_modules`, and the large `assets/video-src/` + `assets/hero-stock-*.mp4` masters.

## Current state — logo-first reset
- The premium homepage in this repo was shown to the client. He asked to **restart from the logo** and rebuild the homepage around a new logo ("ten years forward"). The homepage layout is therefore **paused**.
- **6 wide logo directions** were generated (the **droplet-sun** mark is the lead recommendation). They are presented on the `/logos` brand-deck page, built for the client meeting.
- **Next:** the client picks a logo direction + slogan at the meeting → vectorize the chosen mark to a clean SVG + export set + favicon → then rebuild the homepage around it.
- The favicon is already updated to the droplet+sun mark.

## What is already built and wired (do not break)
- **Lead capture:** `#leadForm` and `#bookForm` POST to an n8n webhook → Lead Manager (CRM), with WhatsApp as a fallback. The backend lives in n8n / Lead Manager and is managed on Alon's side — coordinate with Alon before changing form endpoints or field names.
- **Live Google reviews section:** real GBP reviews (4.9 / 158). **Never fabricate reviews** — only real ones.
- **SEO:** JSON-LD (LocalBusiness + FAQ), `llms.txt`, `robots.txt`, `sitemap.xml`, and `noindex` preview headers (`vercel.json`).
- Real brand facts (founded 1963, manufacturer brands, phone/address) are embedded in `index.html` and summarized in `DESIGN.md`.

## File map
| File | Purpose |
|---|---|
| `index.html` | The homepage (the layout that is paused pending the new logo) |
| `logos.html` | Logo brand-deck, served at `/logos` |
| `DESIGN.md` | Design contract — READ FIRST |
| `assets/` | Images, logos, brand lockups, favicon set |
| `llms.txt`, `robots.txt`, `sitemap.xml`, `vercel.json` | SEO + deploy config |

## House method (keep the quality bar)
Premium Hebrew/RTL in the Roei Deutsch / Wiz line. Ground UI in real shipped patterns (Mobbin) and components (21st.dev). Motion only where it explains (Lottie), never decoration. Run RTL visual QA before shipping. The client is strict on quality.

## Open items / next steps
1. Client meeting: get the logo direction + slogan pick.
2. Vectorize the chosen logo → SVG + export set + new favicon.
3. Rebuild the homepage around the approved logo.
4. **CMS (WordPress/Elementor) is PARKED** until the new design is approved — do not start it yet.
5. Client to provide: high-res field photos/videos, testimonial videos, Live DNS access, WhatsApp Business, Workspace email.

## Meeting context
The full client meeting summary (3 Jun 2026, Alon ↔ Noam) is shared with you on Google Drive (link in the WhatsApp handoff). Noam's key points: emphasize solar **water-heating only** (not electricity), serve both private homeowners and building committees / maintenance companies, and lead with the cheap repair/rehab angle. He is strict on quality ("not less than excellent").

## Contacts
- **Alon** — strategy / project owner. Route all client-facing messages through Alon.
- **Client:** Noam Avishar (owner of Makor Hateva). Do not contact the client without coordinating with Alon.
