# Aeterna Energy — Solar EPC & PPA Website

Static website for **aeternaenergy.in**. Plain HTML + CSS + vanilla JS —
no frameworks, no backend, no hosting lock-in. Runs on any static web server.

## Contents
- `index.html` — the entire site (styles & scripts inline)
- `assets/` — the 5 photographs (hero, team, residential, commercial, utility)
- `favicon.svg` — browser tab icon

## Preview locally
Just open `index.html` in a browser — or serve the folder:
- `python3 -m http.server` or `npx serve .`

## Deploy to aeternaenergy.in
Any static host works. Easiest options:

1. **Netlify** — drag & drop this folder onto app.netlify.com/drop, then
   Settings → Domain management → add `aeternaenergy.in` (point your domain's
   DNS at the nameservers / A record Netlify gives you).
2. **Vercel** — vercel.com → New Project → import this folder, then
   Settings → Domains → add `aeternaenergy.in`.
3. **GitHub Pages** — push the folder to a repo, enable Pages, and add a
   CNAME record pointing `aeternaenergy.in` → `<user>.github.io`.
4. **Own server / cPanel** — upload the files to `public_html` and add the
   domain in cPanel. No PHP, no database needed.

## Editing
- **Contact details / phone** — search for `hello@aeternaenergy.in` and
  `+91 98765 43210` in index.html.
- **Stats** (35+ MW, 140+ projects …) — the
  `<b class="counter" data-target="…">` elements.
- **Calculator assumptions** — `costPerKW`, `55000`, `42000`,
  `units per kW per day` in the <script> section.
- **FAQ** — the `faqData` array in the <script> section.
- **Colors** — the `:root` variables at the top of the <style> block.
- **Photos** — replace the JPGs in `assets/` with real project photos
  (same filenames, or update the `src=` in index.html).

## Notes
- The enquiry form opens a **pre-filled email** (`mailto:`) — no backend
  needed. For a form that actually saves/inboxes submissions, swap it for
  Netlify Forms, Formspree, or similar (add the endpoint to the form action).
- Fonts load from the Google Fonts CDN. To fully self-host, download
  Inter + Sora and replace the <link> tags with local @font-face rules.
- After deploying, add a social-share image to the <head>:
  `<meta property="og:image" content="https://aeternaenergy.in/assets/hero.jpg">`
