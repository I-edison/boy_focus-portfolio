# Focus — Iyase Edison Portfolio

A single-page portfolio site for Iyase Edison (Focus), a graphics designer specializing in branding, social media, and football design.

## What's inside

```
focus-portfolio/
├── index.html          All markup, styles, and behavior (self-contained, no build step)
├── assets/              Real project images cropped from the original artboard (compressed to .jpg)
│   ├── favicon.svg              Browser tab icon
│   ├── profile.jpg               Portrait used in the About section
│   ├── sm1_speaking.jpg          "The Art of Public Speaking" event promo
│   ├── sm2_xiaomi.jpg            Xiaomi SU7 product promo
│   ├── sm3_photostudio.jpg       Classic Photo Studio flyer
│   ├── fb1_lamine.jpg            Lamine Yamal player edit
│   ├── fb2_doku.jpg              Doku player edit
│   └── fb3_matchday.jpg          Barcelona vs Getafe matchday graphic
└── README.md            This file
```

## How to view it

**Quickest:** double-click `index.html` to open it in any browser. Images will load fine since paths are relative to the `assets/` folder sitting next to it.

**Local server (optional, avoids any browser file-access quirks):**
```bash
cd focus-portfolio
python3 -m http.server 8000
# then open http://localhost:8000
```

## Sections

| Section | Anchor | Notes |
|---|---|---|
| Hero | `#home` | Big "Portfolio 2026" title, signature rotated toolbar illustration, niche-focused tagline |
| Profile | `#profile` | About Me + portrait |
| Skill | `#skill` | Softwares, Core Skills, Soft Skills — 3-column layout |
| Services | — | 4 service cards (Social Media, Football, Brand Identity, Motion) each with a starting price and a "Get a Quote" button |
| Projects | `#projects` | Social Media Design grid (3 projects) |
| — | — | Football Design grid (3 projects), directly below Projects |
| Process | — | 4-step "how a project runs" breakdown with turnaround times |
| Testimonials | — | Horizontal scroll-snap carousel — swipe/scroll and cards "stop" in place, with arrow buttons and dot indicators |
| Contact | `#contact` | "Let's Work Together" + WhatsApp, Twitter/X, email links |

Nav is fixed/sticky at the top of every section (shrinks and gains a background blur once you scroll), with a slide-out menu on mobile and a **Hire Me** button that opens a pre-filled WhatsApp message.

A floating WhatsApp button also appears in the bottom-right corner once you scroll past the hero, for a fast one-tap way to start a conversation from anywhere on the page.

## Customizing

- **Text/copy** — edit directly in `index.html`; all copy is plain text inside the HTML, no templating.
- **Colors** — all defined as CSS variables at the top of the `<style>` block (`--bg`, `--orange`, `--white`, `--muted`, etc.) — change once, applies everywhere.
- **Adding a project** — duplicate a `.project-card` block inside either `.project-grid`, point `src` at a new image in `assets/`, and update the alt text and label.
- **Contact links** — update the `href` values in the `.contact-links` block (WhatsApp uses `wa.me/<number>`, email uses `mailto:`).
- **Services & pricing** — edit the four `.service-card` blocks: title, description, the `₦` amount, and the WhatsApp `href` (the `?text=` part pre-fills the message, so keep it URL-encoded — spaces are `%20`).
- **WhatsApp number** — the same number is used in three places: the nav "Hire Me" button, the floating WhatsApp button, and the Contact section. Search for `2349036305571` and replace all instances if the number changes.
- **Testimonials — important:** the five cards in the testimonials carousel are **placeholders** ("Client Name," generic quote text). Replace the quote text, name, role/company, and the two-letter avatar initials in each `.testimonial-card` with real client feedback as you collect it. Real, specific testimonials (naming the project and the result) build far more trust than generic ones — even 2-3 real quotes are better than 5 placeholders.
- **Process steps/turnaround** — edit the `.process-step` blocks to reflect your actual timeline; the current copy (same-day brief, 1-2 day concept, etc.) is a reasonable default but should match how you actually work.

## Deploying

Since it's a static site (no server-side code), you can drag-and-drop the whole `focus-portfolio` folder into:
- **Netlify** (drag-and-drop deploy)
- **GitHub Pages** (push to a repo, enable Pages on the `main` branch)
- **Vercel**, **Cloudflare Pages**, or any static host

Just make sure `assets/` stays in the same folder as `index.html` — the image paths are relative.

## Notes

- Fonts (Anton for display headlines, Caveat for the script accents, Work Sans for body text) load from Google Fonts via CDN, so an internet connection is needed for them to render as designed. Without it, the browser falls back to system sans-serif/cursive fonts.
- No build tools, frameworks, or dependencies — it's plain HTML/CSS/JS.
- Respects `prefers-reduced-motion` for anyone with that OS setting on.
