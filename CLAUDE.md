# CLAUDE.md

Company website for **Surviving Pixels**, a one-person indie game studio from Tampere, Finland. The current focus is the mobile game **Sparks**. It's a small static marketing site with four pages: Home, About, Portfolio (the developer's personal portfolio) and Contact.

## Stack

- **Nuxt 4** (`app/` source directory) + **Vue 3**, plain JavaScript (no TypeScript in `.vue` files, no `lang="ts"`).
- Modules: `@nuxt/a11y`, `@nuxt/content`, `@nuxt/eslint`, `@nuxt/fonts`, `@nuxt/hints` (configured in `nuxt.config.js`).
- `@vueuse/core` for browser utilities (`useThrottleFn`, `useWindowSize`, etc.).
- npm (`package-lock.json` is committed), so use `npm`, not pnpm/yarn/bun.
- No `content/` directory exists yet. `@nuxt/content` and `better-sqlite3` are installed but unused.

## Commands

- `npm run dev`: dev server at http://localhost:3000
- `npm run build` / `npm run generate`: production / static build (output in `.output/`; `dist` is a symlink to `.output/public`)
- `npm run preview`: preview the production build
- `npx eslint .`: lint (config extends the Nuxt-generated `.nuxt/eslint.config.mjs`; needs `nuxt prepare` / `npm install` first)

No tests exist.

## Structure

```
app/
  app.vue                 # Root layout: <Head> font links, <AppHeader/>, <main><NuxtPage/></main>, <AppFooter/>
  assets/styles/main.css  # ALL global styles (imported once from app.vue)
  assets/images/          # Raster images, referenced as ~/assets/images/...
  assets/svg/             # SVGs (logo filename has spaces: "Surviving Pixels Logo.svg")
  components/             # Auto-imported, kebab-case files → PascalCase tags
  pages/                  # File-based routes: index, about, portfolio, contact
public/                   # favicon.ico, robots.txt (served at site root)
```

No `layouts/`, `composables/`, `server/` or `plugins/` dirs. Don't add them unless a feature actually needs one.

## Conventions

### Components and pages
- **File names are kebab-case** (`app-header.vue`, `game-section.vue`); use them in templates as **PascalCase** (`<AppHeader />`, `<GameSection>`). Rely on Nuxt auto-imports; don't import components manually.
- Block order: `<script setup>` → `<template>` → `<style scoped>`. Purely presentational components have no script block.
- Use `<script setup>` (Composition API) only. No Options API.
- Pages are template-only and wrap text content in `<NarrowPage>` (40rem centered column). The home page lays out games with `<GameSection>`.
- `GameSection` uses **named slots**: `#splash-image`, `#title`, `#description`. Add new games by adding another `<GameSection>` block in `pages/index.vue`.
- Each page has exactly one `<h1>`. Section headings are `<h2>`.
- Internal links use `<NuxtLink>`. External/mail links use plain `<a>` (`mailto:` for emails).
- **External links always open in a new tab** so visitors stay on the site: `target="_blank" rel="noopener noreferrer"`. Internal `<NuxtLink>`s and `mailto:` links don't get this.
- Always give `<img>` a meaningful `alt` (the a11y module checks this).
- **Images are WebP**, resized to about 2× their displayed width (splash images ≤800px wide, screenshots ~420px, quality 80). The host rejects large uploads, so keep the whole build small. The old site zip was ~285 KB and the current one ~333 KB. Convert new PNG/JPG images before adding them.

### Styling
- **Plain CSS** only. No Tailwind, no preprocessors. Native CSS nesting (`nav { a { ... } }`) and nested `@media` are used and fine.
- Global/element styles go in `app/assets/styles/main.css`. Component-specific styles go in `<style scoped>`.
- Class names: BEM-ish kebab-case prefixed with the component name (`.main-footer`, `.main-footer-section`, `.game-section-title`, `.main-nav-links`).
- **Units: `rem`** for everything. Root font-size is `24px`, so `1rem = 24px`. Single breakpoint so far: `@media screen and (max-width: 800px)`.
- Layout uses CSS grid (`grid-template` areas) and flexbox with `gap` / `flex-wrap`.
- **Palette** (hard-coded hex values, no CSS variables yet):
  - `#dbfb27`: lime/yellow, all text and links
  - `#aa4513`: rust orange, hover and active link (`.router-link-active`)
  - `#210101`: very dark red, body, nav and footer background
  - `#000`: `<main>` content background
- **Font:** "Jersey 10" (pixel font from Google Fonts) applied globally to `*`. Headings use `font-weight: normal`. Don't introduce other fonts unless asked.
- `#app` (Nuxt `rootId: "app"`) is a 3-row grid: header / main (1fr) / footer.

### Code style
- Double quotes, semicolons, 2-space indent (Prettier-like formatting).
- Comments are sparse. Keep it that way.

## Content facts (keep consistent across header, footer and contact page)
- Company: Surviving Pixels. Business ID **3547078-2**. Location **Tampere, Finland**.
- Emails: `info@survivingpixels.fi`, `surviving.pixels86@gmail.com`.
- Contact info is duplicated in `components/app-footer.vue` and `pages/contact.vue`. Update both when it changes.
- Copy is written in first person by the solo developer, in a casual, honest tone.
- The developer deliberately writes the first-person pronoun as lowercase **"i" in the middle of a sentence**, out of modesty (not putting oneself above others): "and then i decided…". Normal capitalisation still applies: **a sentence or paragraph starting with the pronoun uses "I"** ("I grew up…", "I'm stubborn…"). Never "correct" a mid-sentence "i" to "I", and follow this rule when writing new first-person copy.

## Reference docs
- `docs/portfolio-source.md` (**local only, gitignored, never commit**): notes captured from the old Google Sites portfolio, including verbatim text, links and YouTube IDs. Use it when building or editing the portfolio page.
- The GitHub repo is **public**. Never commit local PC paths, usernames or personal info. Copy only what the website needs into the project, and ask before committing anything privacy-sensitive.

## Known issues (pre-existing; fix only when asked or when touching that code)
- `app/app.vue` line 1 has a stray `import type { svg } from 'property-information';` outside any `<script>` block. It should be removed.
- `app-header.vue`: nav links use relative paths `to="about"` / `to="contact"` (should be `/about`, `/contact`), and `.main-nav-links` declares `gap` twice.
- `pages/index.vue` ends with an empty `<section class="game-section"></section>` placeholder.
- `app-footer.vue` imports `onMounted`/`ref` explicitly but uses auto-imported `watch`, so the import style is mixed.
- Typo in the copy: "Bussiness ID" (footer + contact).
- `README.md` has a short intro, but below it is still the default Nuxt starter text.
