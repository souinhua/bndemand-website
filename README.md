# BN Demand

One-page marketing site for **BN Demand**, a done-for-you organic LinkedIn demand system. Chris builds and runs the system for executives, founders, and B2B teams in the US, Canada, and Australia. There is one program, priced at $5,000 USD a month, with no LinkedIn ads on top.

The page is static HTML styled with Tailwind CSS v4 in the browser, so the class names can be edited and refreshed without a build step. The brand blue is Tailwind `blue-500`, `#3b82f6`.

## What’s on the page

The layout follows the October 2026 single-page wireframe.

1. **Hero** — video placeholder (Chris, 1:30, captions on), the offer, a call booking link, the free checklist, and two proof figures: $80K/mo in appointment value and +$35K/mo in revenue.
2. **The problem** — posting without buyers, random outreach, and no time to run LinkedIn properly.
3. **What you get** — six parts of one system: profile, content, Sales Navigator, post and group mining, profile-viewer follow-up, and outreach.
4. **How it works** — what changes from month 1 through months 6–12, plus industry benchmarks.
5. **Results and founder** — the two client results and a short note from Chris.
6. **Pricing** — $5,000 USD/month, 6-month minimum, and everything included.
7. **Checklist** — work-email capture for the free 10-point LinkedIn demand checklist.
8. **FAQ** — ads, who it’s for, price, time required, and when results show up.
9. **Book a call** — company website and what they sell. Until a calendar is embedded, this opens the visitor’s email app.

## Open it locally

Open `index.html` in a browser. Tailwind and the fonts load from the network, so the page needs an internet connection.

```bash
python3 -m http.server 8765
```

Then visit `http://127.0.0.1:8765/`.

## Edit the brand

In `index.html`, the `@theme` block sets the tokens:

- `--color-primary: #3b82f6` — buttons, prices, checks, and the radial orbs on dark sections
- `--color-primary-dark: #1d4ed8` — hover
- `--color-ink: #101828` — dark sections
- `--font-display` — Bricolage Grotesque
- `--font-sans` — Figtree

Dark blocks (video frame, headshot, pricing panel, closing section, footer) use soft blue radial orbs. The scrollbar is the browser default.

## Before launch

These are still placeholders, marked with HTML comments:

- The 1:30 explainer video and Chris’s headshot
- Real LinkedIn and YouTube URLs
- A Calendly or Cal.com embed on the booking section (keep the two questions: company website, and what they sell)
- The checklist form, which currently opens a `mailto:` to `hello@bndemand.com`. Point it at an email tool before relying on it.
- The footer domain. The wireframe uses `bndemand.com`. Confirm that against the domain registered at Hostinger.

`CONTACT_EMAIL` at the bottom of `index.html` is the address both forms use.

## Deploy

The site is a single HTML file and deploys to **Cloudflare Pages** on the free plan. Keep the domain at Hostinger and point DNS at Pages.

1. Create a project at [Cloudflare Pages](https://pages.cloudflare.com/) and connect this repository, or use Direct Upload.
2. There is no build command. The output is the repository root, and the entry file is `index.html`.
3. Add the custom domain in the Pages project.
4. In Hostinger DNS, add the records Cloudflare shows (typically a CNAME for `www`, and the apex record they specify). HTTPS is issued automatically.

Do not upload `.venv`. It is only a local tool used while reading the wireframe PDF, and it is gitignored.
