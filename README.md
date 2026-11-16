# Mayak — static site

Plain HTML/CSS/images. No build step or server runtime; open `index.html`
directly. All links are relative — they work locally, on GitHub Pages
project paths (`/REPOSITORY/` prefix), and on a custom domain.

## Structure

- `index.html` — language redirect: picks `ru/` or `en/` from
  `navigator.languages`, falls back to English; `noscript` meta-refresh to `en/`.
- `ru/index.html`, `en/index.html` — homepage.
- `ru/privacy/`, `en/privacy/` — privacy policy.
- `ru/support/`, `en/support/` — support.
- `assets/` — shared CSS and images.
