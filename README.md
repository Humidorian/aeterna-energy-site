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
Everything editable lives in **one place**: the `SITE` object at the top of the
`<script>` block in `index.html` (look for the `SITE DATA` banner comment).
Change a value there and it updates everywhere it appears — no hunting
through copies:

- **Brand** — logo text + hero badge tagline
- **Contact** — email, phone, address, hours, city placeholder (updates the
  contact cards, footer and enquiry form all at once)
- **Stats** — counters bar + hero trust badges
- **Warranty** — years shown on the About image card
- **Calculator** — cost per kW (residential/commercial), units per kW per
  day, slider ranges & defaults, caption
- **FAQ** — the `faq` array (question/answer pairs)
- **Images** — paths for the 5 photos in `assets/`

Other things to edit in place:
- **Colors** — the `:root` variables at the top of the `<style>` block.
- **Marketing copy** — headlines and paragraphs are plain HTML, right where
  they appear in the page.

## Notes
- The enquiry form opens a **pre-filled email** (`mailto:`) — no backend
  needed. For a form that actually saves/inboxes submissions, swap it for
  Netlify Forms, Formspree, or similar (add the endpoint to the form action).
- Fonts load from the Google Fonts CDN. To fully self-host, download
  Inter + Sora and replace the <link> tags with local @font-face rules.
- After deploying, add a social-share image to the <head>:
  `<meta property="og:image" content="https://aeternaenergy.in/assets/hero.jpg">`
