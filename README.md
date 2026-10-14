# Francisco Bravo — Personal Branding Site

Personal portfolio and resume site built with [Astro](https://astro.build), [Tailwind CSS](https://tailwindcss.com), and [DaisyUI](https://daisyui.com). It renders a dynamic landing page and a fully-generated resume page sourced directly from a YAML file.

**Live site:** [personalwebpage.fly.dev](https://personalwebpage.fly.dev)

---

## Features

- **Dynamic Resume** — `src/pages/cv.astro` reads `../resumee/francisco-bravo.yml` at build time and renders a professional, printable resume
- **Print-to-PDF Support** — dedicated print styles hide the sidebar and convert everything to clean black & white for easy PDF export
- **Modern Landing Page** — impact stats, engineering highlights, tech stack grid, career timeline, and a call-to-action section
- **Responsive Sidebar Layout** — DaisyUI drawer component with mobile hamburger menu and desktop persistent sidebar
- **Dark Theme** — uses the `night` DaisyUI theme for a premium dark aesthetic
- **View Transitions** — smooth page transitions via Astro's built-in `<ViewTransitions />`
- **SEO Ready** — Open Graph, Twitter Cards, meta tags, and auto-generated sitemap

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | Astro 4 |
| Styling | Tailwind CSS 3 + DaisyUI 4 |
| Animations | Custom CSS keyframes |
| Icons | Inline SVG |
| Resume Data | YAML (js-yaml) |
| Deployment | Docker → Fly.io |

---

## Project Structure

```
├── src/
│   ├── components/          # Reusable Astro components
│   │   ├── cv/TimeLine.astro
│   │   ├── SideBar.astro
│   │   ├── SideBarMenu.astro
│   │   └── ...
│   ├── content/
│   │   └── config.ts        # Astro content collections schema
│   ├── layouts/
│   │   └── BaseLayout.astro # Root HTML shell with sidebar drawer
│   ├── pages/
│   │   ├── index.astro      # Landing / home page
│   │   └── cv.astro         # Resume page (reads YAML)
│   ├── styles/
│   │   └── global.css       # Print styles + animations
│   └── config.ts            # Site title & description
├── public/                  # Static assets (profile image, favicon, etc.)
├── astro.config.mjs
├── tailwind.config.cjs
├── Dockerfile
└── fly.toml
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- npm (or pnpm)

### Install

```bash
npm install
```

### Run Development Server

```bash
npm run dev
```

Open [http://localhost:4321](http://localhost:4321).

### Build for Production

```bash
npm run build
```

Static output is written to `dist/`.

### Preview Production Build

```bash
npm run preview
```

---

## Updating Your Resume

1. Edit the YAML file in the sibling `resumee` repository:
   ```
   ../resumee/francisco-bravo.yml
   ```
2. Rebuild the site — `cv.astro` pulls the latest data at build time:
   ```bash
   npm run build
   ```

No manual HTML editing required.

---

## Print / Save as PDF

Open the **Resume** page and click the **Print / Save PDF** button (top right). The page will render in a clean, sidebar-free layout optimized for printing.

---

## Deployment

The site is containerized with Docker and deployed to [Fly.io](https://fly.io).

```bash
fly deploy
```

See `fly.toml` and `Dockerfile` for configuration.

---

## License

MIT — feel free to fork and adapt for your own portfolio.
