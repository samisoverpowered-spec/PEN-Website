# Pacific Education Network website

A single-page, mobile-friendly site for PEN. Everything (HTML, CSS, JS) lives in `index.html`, so there is no build step.

## Deploy on GitHub Pages

1. Create a repo (for example `pen-website`) and upload `index.html` and this README.
2. Go to **Settings > Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, then save.
3. The site goes live at `https://<your-username>.github.io/pen-website/` within a minute or two.
4. To keep `pen-tutoring.org`, enter it under **Settings > Pages > Custom domain** and update your DNS records as GitHub describes (an A record set for the apex domain, or a CNAME for `www`).

## Editing content

Everything you will update regularly lives in the data blocks near the bottom of `index.html`:

- `PROVINCES`: the provinces shown in every subject tab. Add one (for example Quebec) by adding a line here, then a matching course line under each subject.
- `SUBJECTS`: for each of math, science, english and french, the provincial courses (`canada`), the `ap` list and the `ib` list. Trim or add courses to match what your tutors can teach. The English tab also has the `extra` block for the international three-track program.
- `GUIDES`: one line per study guide. Name IB guides `IB <Subject> SL/HL` and standard courses by subject and grade (`Pre-Calculus 11`). `tag` is `IB`, `AP` or `Standard`; `group` is `math`, `science`, `humanities` or `skills`. For a course with several topic guides (like IB History), use `topics: [{ name, url }]` instead of `url` and they show as links under one row.
- `STATS`: empty for now, so the site shows placeholder boxes. Fill it like `{ value: "250+", label: "students tutored" }`.
- `TESTIMONIALS`: same idea, `{ quote: "...", who: "Parent of a Grade 10 student" }`.
- `TEAM`: people per tab. For photos, create `assets/team/` and set `photo: "assets/team/first-last.webp"`. Leave `photo: ""` to show initials.

### Adding the logo

Search `index.html` for `logo-slot`. There are two (header and footer). Replace each
`<span class="logo-slot" aria-hidden="true">LOGO</span>` with
`<img class="logo" src="assets/logo.png" alt="">` and put your file in `assets/`.
Also swap the favicon line near the top (marked `TODO`).

### Other things to check

- Google Form links appear in several places; search for `forms.gle` to change them all.
- Add your contact email where the `TODO` comment sits in the footer.
- The "Privacy policy" link in the footer points to `#`; replace it with your real policy page.

## Features

- Sticky header with a slide-down menu on phones
- Three quick entry points: get a tutor, use the guides, apply to teach
- Subject explorer with provincial, AP and IB courses per subject
- Searchable, filterable study-guide library
- Team section with tabs by group
- Automatic dark mode, keyboard focus styles, and reduced-motion support
