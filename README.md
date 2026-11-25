# Pacific Education Network website

A mobile-friendly, multi-page site for PEN. No build step — every page is plain HTML that links to a shared `assets/styles.css` and `assets/site.js`.

## Pages

- `index.html` — Home. Hero, the three entry paths, and impact stats and testimonials.
- `tutoring.html` — Subject explorer (provincial, AP, IB courses) and "how it works" steps.
- `study-guides.html` — Searchable, filterable study-guide library.
- `team.html` — Team tabs by group.
- `about.html` — Mission, vision, and quick facts.
- `apply.html` — Request a tutor / apply to teach, plus "how it works".
- `assets/styles.css` — All shared styles (design tokens, layout, components).
- `assets/site.js` — Shared behaviour: mobile menu toggle, footer year.

Page content is plain HTML so search engines and AI assistants can read it without running scripts. Small inline scripts only add behaviour (tabs, filters, counting numbers). The exception is the team list, which is built from data in `team.html`.

## Deploy on GitHub Pages

1. Push all files (the HTML pages, `assets/`, and this README) to your repo.
2. Go to **Settings > Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, then save.
3. The site goes live at `https://<your-username>.github.io/<repo>/` within a minute or two.
4. To keep a custom domain, enter it under **Settings > Pages > Custom domain** and update your DNS records as GitHub describes (an A record set for the apex domain, or a CNAME for `www`).

## Editing content

Look for the `EDIT HERE` comments in each page.

- **Home stats, chat, and testimonials**: plain HTML in `index.html`. For a stat, change both `data-value` and the visible text.
- **Tutoring courses**: plain HTML in `tutoring.html`, one `data-panel` block per subject tab.
- **Study guides**: one `<li>` per guide in `study-guides.html`. `data-group` is `math`, `science`, `humanities` or `skills`.
- **Team**: `TEAM` near the bottom of `team.html`, grouped by tab. Photos go in `assets/team/`. Leave `photo: ""` to show initials.
- **About**: plain HTML in `about.html`.
- **Contact email and Google Form links**: search for `pen.edu45` and `forms.gle` to change them all.
- **After changing `assets/styles.css`**: raise the number in `styles.css?v=2` on every page so visitors get the new version.
- **New page**: add it to `sitemap.xml`.
- The "Privacy policy" link in the footer points to `#`; replace it with your real policy page.

## Features

- Sticky header with a slide-down menu on phones, shared across all pages
- Three quick entry points: get a tutor, use the guides, apply to teach
- Subject explorer with provincial, AP and IB courses per subject
- Searchable, filterable study-guide library
- Team section with tabs by group
- Automatic dark mode, keyboard focus styles, and reduced-motion support
