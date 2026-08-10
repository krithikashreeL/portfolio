# Krithika Lakshminarayanan — Portfolio

A single-page, static portfolio site. No build step, no framework — plain HTML, CSS, and JS.

## What's inside

```
portfolio/
├── index.html        # all content lives here
├── css/style.css      # design system + layout (light/dark themes)
├── js/script.js       # typing effect, scroll reveal, tabs, project filter, theme toggle, contact form, etc.
└── assets/
    └── Krithika_Resume.pdf   # downloadable résumé (linked from the hero "Download Résumé" button)
```

## Preview locally

Any static file server works. From this folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Updating content

Everything is in `index.html` — experience bullets, project cards, Medium articles, publications, and skills are plain markup, no CMS. To add a new project card, copy an existing `<article class="project-card">` block and give it a `data-category` matching one of the filter buttons (`ml-infra`, `genai`, `cv`, `systems`). Add a `<span class="featured-badge">Featured</span>` as the first child to highlight a card.

To swap the résumé, replace `assets/Krithika_Resume.pdf` with the same filename, or update the `href` on the "Download Résumé" button.

## Deploying

**GitHub Pages** (recommended, free, pairs naturally with your GitHub profile):
1. Create a new repo, e.g. `krithikashreeL.github.io` (this naming gives you a root domain) or any repo name + enable Pages on the `main` branch.
2. Push this folder's contents to the repo root.
3. In the repo's Settings → Pages, set the source to the `main` branch, `/ (root)`.
4. Your site is live at `https://krithikashreeL.github.io` (or `https://krithikashreeL.github.io/<repo-name>`).

**Netlify / Vercel**: drag-and-drop this folder into Netlify's deploy UI, or run `vercel` / `netlify deploy` from inside it — both detect static sites with zero config.

## Notes

- Fonts (Sora, Inter, JetBrains Mono) load from Google Fonts via CDN — needs an internet connection to render with the intended type, but falls back to system sans-serif otherwise.
- Theme preference (light/dark) is saved in the visitor's browser via `localStorage`.
- The hero background is a CSS-only animated pastel gradient (no canvas/JS), respecting `prefers-reduced-motion`.
- The contact section includes a mailto-based form (`js/script.js`) alongside the copy-email button — no backend required.
- All data (experience, projects, publications, articles) is static — update it directly in `index.html` as your work evolves.
