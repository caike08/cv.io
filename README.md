# cv.io — Carlos Henrique Motta's CV

Static, dependency-free CV site for Carlos Henrique Motta, deployed with GitHub Pages at
https://caike08.github.io/cv.io/.

## Preview locally

```sh
python3 -m http.server 8080
# open http://localhost:8080
```

(Any static server works; opening `index.html` directly in a browser also works.)

## Structure

```
index.html             — the whole CV (content, meta tags, JSON-LD structured data)
assets/css/            — styles-3.css (layout/theme) + variables.css (design tokens)
assets/images/         — profile photo (WebP first, JPEG fallback)
favicon.svg / .png     — favicons
```

## Making changes

- **Content** (text, jobs, projects, skills): edit `index.html` directly — it is the single
  source of truth.
- **Colors, spacing**: tweak the custom properties (design tokens) in `assets/css/variables.css`.
- **Meta / SEO**: `og:` tags and the JSON-LD `Person` block live in `<head>` of `index.html`.
  Canonical and `og:image` URLs assume the GitHub Pages project URL
  (`https://caike08.github.io/cv.io/`); update them if the site moves to another domain.
- **Profile photo**: digit one photo, keep both formats updated (`profile.jpg` used as
  `<img>` fallback and social image, `profile.webp` served first). 480×480 is plenty — the
  photo renders at 240 CSS px in the sidebar.

## Useful built-in features

- **Save as PDF** button (sidebar) uses a dedicated `@media print` stylesheet that collapses
  the two-column layout into a clean, single-column document with expanded URLs.
- No JavaScript libraries and no build step — the page is fully static.

## Accessibility notes

- Decorative icons are inline SVG with `aria-hidden="true"`.
- Muted colors keep ~4.5:1+ contrast (WCAG AA).
- Keyboard focus rings via `:focus-visible`.

## Credits

Originally based on the free "Orbit" resume template by
[Xiaoying Riley / 3rd Wave Media](http://themes.3rdwavemedia.com/), licensed under
[Creative Commons Attribution 3.0](https://creativecommons.org/licenses/by/3.0/). The
attribution link is retained in the page footer as required by the license. The template
dependence (Bootstrap 3, jQuery, Font Awesome) has since been removed in favor of plain HTML/CSS.
