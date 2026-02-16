# CLAUDE.md

## Project Overview

**Flor de Tango** is a static website for a tango dance association based in Grasse, France. The site is a single-page design showcasing the association's courses (Argentine tango, milonga, waltz), teachers (Céline Bacquet and Edouard Paco), and contact information.

- **Language:** French (all content is in French)
- **Contact:** contact@flordetango.fr

## Repository Structure

```
.
├── index.html                     # Entire website (HTML + embedded CSS)
├── README.md                      # Brief project description
├── CLAUDE.md                      # This file
└── .github/
    └── workflows/
        └── static.yml             # GitHub Pages deployment workflow
```

This is a minimal project — there are no build tools, dependencies, JavaScript, or backend components.

## Tech Stack

- **HTML5** with semantic sections (nav, sections for hero/about/courses/teachers/contact, footer)
- **CSS3** embedded in a `<style>` block within `index.html`
- **Google Fonts:** Playfair Display (headings) and Lato (body text)
- **No JavaScript**
- **No package manager or build system**

## CSS Conventions

All styles live inside `index.html` in a single `<style>` block. The design uses CSS custom properties defined on `:root`:

| Variable    | Value     | Usage            |
|-------------|-----------|------------------|
| `--rouge`   | `#8B1A1A` | Burgundy/red     |
| `--or`      | `#C9A84C` | Gold accent      |
| `--noir`    | `#0E0E0E` | Dark background  |
| `--creme`   | `#FAF6EF` | Light text/bg    |
| `--gris`    | `#3a3a3a` | Gray text        |

### Naming conventions

- Class names use a BEM-inspired kebab-case pattern: `nav-logo`, `hero-subtitle`, `cours-card`, `prof-avatar`
- Section IDs are in French: `#apropos`, `#cours`, `#professeurs`, `#contact`

### Responsive design

- Mobile breakpoint at `max-width: 768px`
- Grids collapse to single column on mobile
- Navigation links are hidden on mobile (`display: none`)

## Deployment

The site deploys to **GitHub Pages** via the workflow in `.github/workflows/static.yml`:

- **Trigger:** Push to `main` branch or manual dispatch
- **Process:** Checkout → Configure Pages → Upload artifact (entire repo) → Deploy
- **No build step required** — the repo is deployed as-is

## Development Workflow

1. Edit `index.html` directly — all markup and styles are in this single file
2. Open `index.html` in a browser to preview changes locally
3. Push to `main` to trigger automatic deployment to GitHub Pages

### Key guidelines

- Keep all CSS in the embedded `<style>` block (no external stylesheets)
- Maintain the existing color scheme via CSS custom properties
- All user-facing text must be in French
- Preserve responsive behavior for mobile devices
- Use Playfair Display for headings and Lato for body text
- Follow the existing class naming pattern (kebab-case, section-prefixed)

## Testing

There is no automated test suite. Verify changes by:

- Opening `index.html` in a browser
- Checking responsive layout at various viewport widths
- Validating HTML structure (W3C validator)

## Linting / Formatting

No linting or formatting tools are configured. Maintain consistency with the existing code style:

- 2-space indentation in HTML
- CSS properties on single lines within the `<style>` block for compactness
- Inline styles used sparingly for section-specific overrides
