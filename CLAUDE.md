# What's Good — website · context for Claude Code

The public website for What's Good, an evening gratitude app for iPhone (the app lives in the private repo `mikkemakka/whatsgood`; its docs are the source of truth for the product, tokens and copy).

## What's here
```
index.html            the landing page: hero, the phones, three features, values, closing call to action
privacy.html          the privacy policy (same wording as the app's Settings › Privacy)
support.html          help and contact
style.css             every style; tokens on :root, dark mode by prefers-color-scheme
assets/fonts/         Literata (OFL), self-hosted: no Google Fonts requests
assets/*.png          icon, favicon, apple-touch-icon, og.png (the link preview)
vercel.json           headers for Vercel
```
Plain HTML and CSS. No framework, no build step, no JavaScript unless a feature needs it.

## Addresses that must never change
The site is served from **GitHub Pages** (`https://mikkemakka.github.io/whatsgood-site/`) and **Vercel** (`https://whatsgoodapp.vercel.app/`; also `whatsgood-site.vercel.app`, the project's own name. Not `whatsgood.vercel.app`: that's someone else's site). `privacy.html` and `support.html` are in App Store Connect, and the app's Settings links to `support.html`: never rename or move them. Every link and asset path is **relative** (no leading `/`), so the same files work under `/whatsgood-site/` and at a domain's root.

## Rules
- **The page's one job:** show the app and get people to join the beta (later: download it). Privacy and support are secondary.
- **Look like the app:** tokens mirror `whatsgood/docs/design-tokens.md` (change them there first, then in `style.css`). Literata for headings and the user's words, the system font for UI. One accent gesture: the soft-yellow highlight behind a word. Hairlines instead of boxes, no gradients. Light and dark both work.
- **Copy:** plain, warm, non-saccharine; for sceptics. No streaks, scores or guilt. Wellness only: never a treatment or mental-health claim.
- **Privacy is part of the product:** no analytics, no cookies, no third-party requests (fonts, scripts, embeds). If that ever changes, the privacy page changes in the same PR.
- **The privacy page** says the same as `whatsgood/WhatsGood/Features/Settings/PrivacyView.swift` (plus a section on the website itself); change both together, with the date. Miklos approves every wording change to privacy and support.
- **Accessibility:** 44 pt targets, visible focus, alt text or `role="img"` labels on the drawn phones, no horizontal scroll at 390 px.
- **Placeholder to replace:** `https://testflight.apple.com/join/XXXXXXXX` (every Join the beta button, on every page).
- **The App Store badge** only once the app is live (Apple's badge rules).

## How we work
- One issue → one branch → one PR; Miklos reviews and merges. Never commit to `main` directly.
- Before a PR: open the page at 1440 and 390 px, light and dark; attach screenshots.
- Deploys: GitHub Pages and Vercel both publish `main`; Vercel also builds every PR as a preview.
