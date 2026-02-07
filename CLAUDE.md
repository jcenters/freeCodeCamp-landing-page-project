# CLAUDE.md

Guide for AI assistants working on this repository.

## Project Overview

This is a **static HTML/CSS landing page** built as a freeCodeCamp Responsive Web Design certification project. It is a product landing page for the book *Take Control of Notes* by Josh Centers.

There are **no build tools, no package manager, no JavaScript framework, and no dependencies** — just plain HTML5 and CSS3 served as static files.

## Repository Structure

```
freeCodeCamp-landing-page-project/
├── landing-page.html    # Single-page HTML (entry point)
├── styles.css           # All styling (responsive, mobile-first)
├── images/
│   └── TCoNotes-cover.png  # Book cover image
└── CLAUDE.md            # This file
```

## Tech Stack

- **HTML5** — semantic markup (`<header>`, `<nav>`, `<main>`, `<form>`)
- **CSS3** — flexbox layout, media queries for responsiveness
- **No JavaScript** (except the FreeCodeCamp test bundle loaded via CDN)
- **No build system** — files are served directly as-is

## Key Conventions

### HTML
- Semantic elements used throughout (`<header>`, `<nav>`, `<main>`, `<form>`)
- IDs used for page sections and anchor navigation (`#about`, `#toc`, `#author`, `#contact`)
- IDs also used for FreeCodeCamp test requirements (`#header`, `#header-img`, `#nav-bar`, `#video`, `#email`, `#submit`, `#form`)
- External stylesheet linked in `<head>`; no inline styles

### CSS
- **Mobile-first responsive design** with two breakpoints:
  - Small screens: `200px–799px`
  - Large screens: `800px+`
- **Flexbox** for layout (header, nav, images)
- Naming: kebab-case for classes and IDs (`nav-link`, `header-img`, `nav-bar`)
- Primary brand color: `#1085B7` (blue)
- Font: Helvetica, sans-serif fallback
- Fixed navbar on desktop; stacked column layout on mobile

### File Organization
- Flat structure — all code in the project root
- Single HTML file, single CSS file
- Assets in `images/` directory

## FreeCodeCamp Test Requirements

The project includes the FreeCodeCamp test bundle (`bundle.js` via CDN) which validates required elements and IDs. **Do not remove or rename** the following IDs, as they are tested:

- `#header`, `#header-img`, `#nav-bar` — header/navigation
- `.nav-link` — navigation link class (must exist on anchor elements inside `#nav-bar`)
- `#video` — embedded video iframe
- `#form`, `#email`, `#submit` — email signup form
- `#about`, `#toc`, `#author`, `#contact` — section anchors

The form action must point to `https://www.freecodecamp.com/email-submit`.

## Development Workflow

### Running Locally
Open `landing-page.html` directly in a browser. No server or build step needed.

### Testing
Open the page in a browser and use the FreeCodeCamp test suite widget (loaded via the CDN script) to run the "Product Landing Page" tests.

### No Linting/Formatting Tools
There are no configured linters, formatters, or pre-commit hooks. Maintain consistency with the existing code style manually:
- 2-space indentation in HTML
- Tab indentation in some CSS media query blocks (mixed — match surrounding code)
- No trailing semicolon on the last property in some CSS rule blocks (see `styles.css:101`)

## Git Conventions

- **Main branch:** `master`
- **Commit style:** short imperative descriptions (e.g., "Delete .DS_Store", "Final draft of code, passes all tests.")
- No `.gitignore` is present — avoid committing OS files (`.DS_Store`, `Thumbs.db`, etc.)

## Known Issues

- `styles.css:101` — missing trailing semicolon on `width: 80%` (cosmetic, does not affect rendering)
- `styles.css:24` — `align-items: left` is not a valid value; `align-items` accepts `flex-start`, `center`, etc. (no visible effect since `<p>` is not a flex container)
- `styles.css:115` — contains an invisible zero-width space character at the end of the file
- The `<script>` tag for the FreeCodeCamp test bundle is placed after `</body>` but before `</html>`, which is technically invalid placement (should be inside `<body>`)
