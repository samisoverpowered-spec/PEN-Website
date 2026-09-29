# Pacific Education Network website

A mobile-friendly, multi-page site for PEN. No build step — every page is plain HTML that links to a shared `assets/styles.css` and `assets/site.js`.

## Pages

- `index.html` — Home. Hero, the three entry paths, and impact stats/testimonials (placeholders for now).
- `tutoring.html` — Subject explorer (provincial, AP, IB courses) and "how it works" steps.
- `study-guides.html` — Searchable, filterable study-guide library.
- `team.html` — Team tabs by group.
- `about.html` — Mission, vision, and quick facts.
- `apply.html` — Request a tutor / apply to teach, plus "how it works".
- `assets/styles.css` — All shared styles (design tokens, layout, components).
- `assets/site.js` — Shared behaviour: mobile menu toggle, footer year.

Each page also has its own small inline `<script>` block for the data specific to that page (subjects, guides, team, stats).

## Deploy on GitHub Pages

1. Push all files (the HTML pages, `assets/`, and this README) to your repo.
2. Go to **Settings > Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, then save.
3. The site goes live at `https://<your-username>.github.io/<repo>/` within a minute or two.
4. To keep a custom domain, enter it under **Settings > Pages > Custom domain** and update your DNS records as GitHub describes (an A record set for the apex domain, or a CNAME for `www`).

## Editing content

- **Home stats/testimonials** — `STATS` and `TESTIMONIALS` near the bottom of `index.html`. Empty arrays show placeholder boxes; fill like `{ value: "250+", label: "students tutored" }` or `{ quote: "...", who: "Parent of a Grade 10 student" }`.
- **Tutoring subjects** — `PROVINCES` and `SUBJECTS` near the bottom of `tutoring.html`. `SUBJECTS` holds, per subject, the provincial courses (`canada`), the `ap` list and the `ib` list. The English subject also has an `extra` block for the international three-track program.
- **Study guides** — `GUIDES` near the bottom of `study-guides.html`. One entry per guide. Name IB guides `IB <Subject> SL/HL` and standard courses by subject and grade (`Pre-Calculus 11`). `tag` is `IB`, `AP` or `Standard`; `group` is `math`, `science`, `humanities` or `skills`. For a guide with several parts (like IB History), use `topics: [{ name, url }]` instead of `url`.
- **Team** — `TEAM` near the bottom of `team.html`, grouped by tab. For photos, create `assets/team/` and set `photo: "assets/team/first-last.webp"`. Leave `photo: ""` to show initials.
- **About** — mission, vision, and facts list are plain HTML directly in `about.html`.

### Adding the logo

Search each page for `logo-slot` (there's one in the header, one in the footer, on every page). Replace
`<span class="logo-slot" aria-hidden="true">LOGO</span>` with
`<img class="logo" src="assets/logo.png" alt="">` and put your file in `assets/`.
Also swap the favicon `<link rel="icon" ...>` line near the top of each page (marked `TODO`).

### Other things to check

- Google Form links appear on several pages; search for `forms.gle` to change them all.
- Add your contact email where the `TODO` comment sits in each page's footer.
- The "Privacy policy" link in the footer points to `#`; replace it with your real policy page.

## Features

- Sticky header with a slide-down menu on phones, shared across all pages
- Three quick entry points: get a tutor, use the guides, apply to teach
- Subject explorer with provincial, AP and IB courses per subject
- Searchable, filterable study-guide library
- Team section with tabs by group
- Automatic dark mode, keyboard focus styles, and reduced-motion support
