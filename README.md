# SEED Lab — UCLA Semel Institute

Website for the **SEED Laboratory** (Signatures of Early Emergence and Divergence), led by Brittany Wolff, Ph.D., at the UCLA Jane & Terry Semel Institute for Neuroscience and Human Behavior.

A static site: plain HTML, CSS and JavaScript. No build step. Open `index.html` or serve the folder.

```bash
# local preview
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Pages

| File | Page |
| --- | --- |
| `index.html` | Home — animated "divergence field" hero, the acronym, the central question, six methods, PI, publications, news, get involved |
| `research.html` | Research question, model diagram, six modalities, current projects, funders |
| `team.html` | PI feature, filterable member grid with bio drawer, alumni |
| `publications.html` | Searchable, filterable list grouped by year |
| `news.html` | Featured story and news list |
| `join.html` | Participate / Join the lab tabs, FAQ, open positions, contact form |

## Editing content

**People, publications and news live in one file: `assets/js/data.js`.**

- **Add a team member:** copy an object in `TEAM`, edit `name`, `role`, `group` (`pi`, `postdoc`, `grad`, `staff`, `undergrad`), `bio`, and so on.
  - Add a photo by putting it in `assets/img/team/` and setting `photo: 'assets/img/team/name.webp'`. Leave `photo: ''` to keep the generated placeholder portrait.
- **Add a publication:** copy an object in `PUBLICATIONS`. Wrap lab members in `**double asterisks**` to show them in bold. `type` creates the filter chips automatically.
- **Add news:** copy an object in `NEWS`. The first item becomes the featured story.

**Page text** (headlines, paragraphs, research descriptions) is in each `.html` file. Search for "placeholder" or "lorem" to find text that still needs replacing.

**PI portrait:** on `index.html`, search for `PI portrait · replace`. On the team page, set `photo` for Dr. Wolff in `data.js`.

**Group photo:** the team page uses `assets/img/royce-arcade.webp`. Replace that file or change the `src`.

## Design system

- **Colors** are CSS variables at the top of `assets/css/style.css` (`--ink`, `--paper`, `--ember`, `--sprout`). Change `--ember` to re-theme the accent.
- **Fonts:** Boska (display, Fontshare), Switzer (body, Fontshare), JetBrains Mono (labels, Google Fonts).
- **Motion:** GSAP + ScrollTrigger + Lenis smooth scroll (bundled in `assets/vendor/`). Respects `prefers-reduced-motion`.
- **Dark mode:** the moon/sun toggle in the header. The choice is saved in the browser.

## Logo

Files are in `assets/logo/`:

- `seed-mark.svg` / `seed-mark.png`: the mark (transparent background)
- `seed-mark-light.svg`: the mark for dark backgrounds
- `seed-lab-logo.png`: full lockup, transparent, for light backgrounds
- `seed-lab-logo-dark.png`: full lockup on forest-black
- `favicon.svg`, `favicon-512.png`: app and browser icons
- `seed-lab-og.png`: social share image (1200×630)

**The concept:** a seed silhouette split by a forked path. The left half is solid (resilience). The right half is drawn as trajectory lines (divergence, the "signatures"). The ember top is the emerging sprout, and the dot marks the point where paths diverge.

## Deploying (free hosting + a cheap domain)

1. **Push to GitHub:** create a repo, then run `git remote add origin <url>` and `git push -u origin main`.
2. **Host it for free.** Any of these works with zero config, because it's a static site:
   - **GitHub Pages:** go to Settings → Pages, choose "Deploy from branch", then `main` / root.
   - **Cloudflare Pages** or **Netlify:** connect the repo, leave the build command empty, and set the output directory to `/`.
3. **Domain:** buy one from a low-markup registrar (e.g. Cloudflare Registrar or Porkbun), then point it at the host using that host's custom-domain instructions. Note that UCLA may also offer an official `*.ucla.edu` subdomain through the department.

## Image credits

All photography comes from [Unsplash](https://unsplash.com) under the Unsplash License (free to use). The files are stored locally in `assets/img/` as optimized WebP.
