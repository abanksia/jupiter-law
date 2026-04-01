# Jupiter Law — Static Site Replica & Self-Hosting

## Project Overview
Replicate jupiter.law (Squarespace) as a clean static site and deploy to Cloudflare Pages.

**Site:** https://www.jupiter.law/ (may be offline — Squarespace subscription ended)
**Domain registrar:** GoDaddy
**Hosting target:** Cloudflare Pages (free tier)

## About Jupiter Law
- Australian law firm based in the Northern Rivers region
- Practice areas: Employment, Commercial, Property
- ABN: 85 670 096 143
- Contact: (02) 8529 5010 / hello@jupiter.law
- Postal: 4 Starling Street, Burleigh Heads QLD 4220
- Booking: https://calendar.app.google/cuDabTL9LMwgVfsM7

## Design Specs (from screenshots of live site)

### Colors
- Page background: #F9F8F4 (warm off-white/cream)
- Content background: #FFFFFF (white, used on legal pages body)
- Text: #1A1A1A (near-black)
- Accent purple: #5B5BEA (used for page titles on legal pages)
- Accent green: #5BF0A5 (mint green, used for CTA button)
- Borders/dividers: #D9D9D9

### Typography
- Body font: Inter (or system sans-serif)
- Page titles (Privacy Policy, Terms of Use): DM Serif Display in purple
- Section headings: Inter, bold/semibold, ~1.35rem
- Body text: Inter, regular weight, ~0.95rem

### Layout
- **Landing page**: Logo (circle icon + "JUPITER LAW" text) at top left. Two-column layout below with vertical divider: left = description + practice areas (centered), right = contact info + green CTA button. Footer with thick black top border.
- **Legal pages**: Cream header area with small "JUPITER LAW" logo top-left, "Back to Home" link top-right, large purple serif title, date. White body area with two-column grid: section heading on left (300px), body text on right. Horizontal dividers between sections.

### Logo
The logo consists of two parts:
1. A circular icon with horizontal color stripes (greys, mauves, pinks, green)
2. "JUPITER LAW" in large bold uppercase text

The circle icon image needs to be saved from the original site as `images/logo-icon.png`.

## Site Structure (3 pages)
1. **index.html** — Landing page
2. **privacy.html** — Privacy policy (11 sections)
3. **terms.html** — Terms of use (14 sections)

## Files
- `index.html`, `privacy.html`, `terms.html` — Replica pages (ready to use)
- `original-index.html`, `original-privacy.html`, `original-terms.html` — Raw Squarespace source (reference)
- `images/logo-icon.png` — Logo circle icon (save from original site)
- `images/hero.png` — Hero illustration (if used)

## How to Edit Text
All text is plain HTML. To change anything:
1. Open the file in VS Code
2. Find the text (Cmd+Shift+F to search across all files)
3. Edit and save
4. Redeploy with `npx wrangler pages deploy .`

Example: to update the phone number, search for `8529 5010` and change it everywhere.

## Deployment
1. **Preview locally**: `python3 -m http.server 8000` or VS Code Live Server extension
2. **Deploy to Cloudflare Pages**:
   - `npm install -g wrangler`
   - `wrangler login`
   - `npx wrangler pages deploy . --project-name=jupiter-law`
3. **Point domain (GoDaddy)**:
   - Add CNAME: `@` → `jupiter-law.pages.dev`
   - Or move nameservers to Cloudflare

## Future Improvements (noted by owner)
- The current design feels "uninspiring" / template-y — owner wants to eventually refresh
- Liked the editorial design style of Folk's Gilbert+Tobin case study: https://www.folk.com.au/work/gilbert-tobin-sharpening-up-australia-s-most-advanced-law-firm
- Wants warm & approachable vibe, not generic law firm template
- For now: faithful replica first, redesign later
