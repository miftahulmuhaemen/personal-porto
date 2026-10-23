# Technical Portfolio - Miftahul Muhaemen

Engineering portfolio and production case studies for Miftahul Muhaemen (Software & Data Engineer). Deployed on [Cloudflare Pages](https://pages.cloudflare.com/) at [muhaemen.my.id](https://muhaemen.my.id).

---

## 1. Overview & Architecture

Built with [Astro](https://astro.build) using static site generation (SSG) for fast edge delivery, semantic markup, and zero client-side JavaScript overhead where possible.

- **Framework**: Astro 5 (Static Site Generation)
- **Language**: TypeScript 5.9
- **Content Engine**: Astro Content Collections (`src/content/posts/`, `src/content/about/`)
- **Styling**: Scoped CSS with CSS variables for light/dark mode transitions, typography driven by Inter (sans) and Besley (serif)
- **Asset Processing**: Sharp for automated WebP image conversion and responsive dimensions
- **Math & Media**: KaTeX math rendering, custom remark/rehype plugins for embedded media and syntax highlighting
- **Deployment & Edge**: Cloudflare Pages with custom DNS, CAA validation, and edge-level bot protection policies via Cloudflare CLI (`cf`)

---

## 2. Content Standards

All project breakdowns and articles adhere to the [Technical Portfolio Writing Standards](.agent/rules/writing_style.md):

- **Evidence Over Adjectives**: Mechanics, architecture diagrams, data models, and measurable trade-offs rather than generic adjectives.
- **Anti-Slop Copywriting**: Zero marketing fluff, zero machine-generated filler words, and zero decorative emojis in headers and copy.
- **Standardized Hierarchy**: Frontmatter metadata, operational status checklists, architecture breakdowns, data integrity optimizations, and testing/observability notes.

---

## 3. Project Structure

```
├── .agent/rules/           # Writing and technical portfolio guidelines
├── public/                 # Static assets, favicon, resumes, videos
│   ├── resumes/            # Verified Fullstack & No-Code resume PDFs
│   └── videos/             # Architecture and platform demo screencasts
├── src/
│   ├── components/         # Modular Astro UI components
│   │   ├── layout/         # BaseHead, Header, Footer, Transitions
│   │   ├── ui/             # ThemeToggle, ThemeManager, LinkCard, ImageOptimizer
│   │   └── widgets/        # PostList, About, FormattedDate
│   ├── content/
│   │   ├── about/          # Profile intro & resume markdown
│   │   └── posts/          # Case studies, certifications, work history
│   ├── data/
│   │   └── quotes.ts       # Curated quotes dataset with client-side randomizer
│   ├── layouts/            # IndexLayout, PostLayout, BaseLayout
│   ├── plugins/            # Remark and Rehype build plugins
│   └── styles/             # Global CSS variables, fonts, post typography
└── astro.config.ts         # Astro pipeline integrations and Vite configurations
```

---

## 4. Development & Build

### Prerequisites

- Node.js 20+ (LTS recommended)
- pnpm 9+

### Commands

```bash
# Install dependencies
pnpm install

# Start local dev server (default: http://localhost:4321)
pnpm dev

# Build static production bundle to dist/
pnpm build

# Preview production build locally
pnpm preview

# Run linter
pnpm lint

# Format codebase with Prettier
pnpm format

# Scaffold a new post / case study
pnpm new "<post-title>"
```

---

## 5. Deployment

Production builds are triggered automatically upon pushing to the `master` branch. Cloudflare Pages executes `pnpm build` and serves static assets from `dist/` across the Cloudflare global network.

---

## 6. License

MIT
