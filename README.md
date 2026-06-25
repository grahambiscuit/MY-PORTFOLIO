# Chezko — Full-Stack Portfolio

A single-file animated portfolio site built around a terminal / "system boot" concept. No build tools, no dependencies to install — just one HTML file you can open or deploy anywhere.

## Files

```
portfolio.html   → the entire site (HTML + CSS + JS in one file)
README.md        → this file
```

## Running it locally

Just double-click `portfolio.html`, or open it in any browser. No server, no install, no build step required.

## What's inside

- **Hero** — a live-typed boot sequence ("whoami" → checks HTML/Python/Java/JavaScript → "all systems go") that resolves into your name with a glitch reveal.
- **Ticker** — a scrolling strip of your four core languages.
- **Stack section** — four cards, one per language, each shown as a real code snippet with an animated status bar.
- **Projects section** — intentionally left empty, styled like an empty terminal directory listing, ready for you to fill in.
- **About** — a short bio block, written generically so you can edit it freely.
- **Connect** — placeholder email / GitHub / LinkedIn links and a footer.

All animations respect `prefers-reduced-motion` and the layout is responsive down to mobile.

## Things to update before publishing

| What | Where in the file | Find |
|---|---|---|
| Email / GitHub / LinkedIn links | `~/connect` section | `your.email@example.com`, `github.com/`, `linkedin.com/` |
| About text | `~/about` section | `<div class="about-content">` |
| Hero tagline | Hero section | `<p class="hero-tagline">` |
| Page title / meta description | `<head>` | `<title>` and `<meta name="description">` |

## Adding your projects

The projects section currently shows an empty-state card on purpose. To add a real project, copy this pattern (based on the `.stack-card` style already in the file) into the `<section class="projects" id="projects">` block, inside a new grid div:

```html
<div class="stack-card" data-reveal>
  <div class="card-code">my-project</div>
  <h3 class="card-name">Project Name</h3>
  <p class="card-desc">One or two lines on what it does and what you used to build it.</p>
  <div class="card-status"><span class="dot"></span> live</div>
</div>
```

Wrap your project cards in a `<div class="stack-grid">` (already styled in the CSS) so they line up in a responsive grid like the stack section does.

If you'd like, I can wire your real projects in directly — just send me the names, short descriptions, tech used, and links.

## Customizing the look

All colors, fonts, and spacing are controlled by CSS variables at the top of the `<style>` block:

```css
:root{
  --bg: #090c10;        /* page background */
  --accent: #f2b33d;    /* amber accent */
  --accent-2: #56e0c0;  /* mint accent */
  --mono: 'JetBrains Mono', ui-monospace, monospace;
  --sans: 'Sora', system-ui, sans-serif;
  ...
}
```

Change a value here and it updates everywhere it's used.

## Browser support

Built with standard CSS (Grid, custom properties, `clip-path`) and vanilla JavaScript (`IntersectionObserver`, async/await). Works in all modern browsers — Chrome, Firefox, Safari, Edge.

## Deploying

Since it's a single static HTML file, you can host it anywhere for free:
- **GitHub Pages** — push it to a repo and enable Pages
- **Netlify / Vercel** — drag-and-drop deploy
- **Any static host** — just upload `portfolio.html` (rename to `index.html`)
