# Photosynthesis Lab Website

A minimal, static academic lab website inspired by [fluidlab.nl](https://www.fluidlab.nl/).
No build tools, no backend, no dependencies beyond a Google Font loaded via CDN.

## Structure

```
index.html       — Home (hero, research cards, news feed, affiliations)
research.html    — Detailed research themes
team.html        — PI, postdocs, PhD students, alumni, open positions
news.html        — Publications, awards, events (reverse chronological)
contact.html     — Address, email, map placeholder
css/style.css    — All styles (edit CSS variables at the top to restyle)
```

## Editing content

Every section is marked with a comment block like:

```html
<!-- ═══════════════════════════════════════════════════════
     NEWS ITEMS — reverse chronological order
     ...
     ═══════════════════════════════════════════════════════ -->
```

**Adding a news item** — copy an `<li class="news-item">` block in `news.html`
and adjust the date, badge class, headline, and body text.

Badge classes: `badge-pub` · `badge-award` · `badge-news` · `badge-event`

**Adding a team member** — copy an `<article class="member">` block in `team.html`,
update the name, role, and topic. Replace the SVG placeholder with an `<img>` tag.

**Changing colors** — edit the CSS custom properties at the top of `css/style.css`:

```css
:root {
  --text:        #111111;
  --text-muted:  #666666;
  --accent:      #2d6a4f;   /* main colour — change this to rebrand */
  --border:      #e2e2dc;
  ...
}
```

## Hosting

Because this is pure static HTML it can be hosted for free on:

| Platform | How |
|---|---|
| **GitHub Pages** | Push to a repo, enable Pages in Settings → Pages → `/ (root)` |
| **Netlify** | Drag & drop the folder on netlify.com/drop, or connect the repo |
| **Vercel** | `vercel deploy` or connect repo — framework preset: *Other* |
| **Cloudflare Pages** | Connect repo, no build command, output directory `/` |
| **Any web host** | Upload files via FTP — no server-side software required |

### GitHub Pages (quickest)

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USER/YOUR_REPO.git
git push -u origin main
# Then go to repo Settings → Pages → Source: Deploy from branch → main / (root)
```

The site will be live at `https://YOUR_USER.github.io/YOUR_REPO/`.

## Adding real photos

Replace the SVG placeholder inside `.member-photo` / `.pi-photo` with:

```html
<img src="images/person-name.jpg" alt="Name" style="width:100%;height:100%;object-fit:cover;">
```

Keep photos square (1:1) for best results. Recommended minimum: 400 × 400 px.

## Adding a Google Maps embed

In `contact.html` replace the placeholder `<div>` with:

```html
<iframe
  src="https://maps.google.com/maps?q=Science+Park+904+Amsterdam&output=embed"
  width="100%" height="320"
  style="border:0; border-radius:6px; display:block;"
  allowfullscreen loading="lazy">
</iframe>
```
