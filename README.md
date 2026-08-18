# puljic.ch — Personal Portfolio

Personal portfolio and freelancing site for Domagoj Puljić, backend/cloud engineer based in
Zurich, Switzerland.

## Stack

- **[Astro](https://astro.build)** — content-first framework, ships ~0 JS by default.
- **Tailwind CSS v4** — utility-first styling via `@tailwindcss/vite`.
- **Content collections** (`src/content/`) — case studies live as Markdown in
  `src/content/projects/*.md`; a `blog` collection is scaffolded (`src/content/blog/`) for future
  posts and needs no refactor to activate — just drop `.md`/`.mdx` files in.

## Project structure

```
src/
  components/     ProjectCard.astro, SkillGroup.astro
  content/
    projects/     one .md file per case study (frontmatter: title, stack, outcome, order)
    blog/         empty for now, wired up for future posts
  layouts/        Base.astro (shared <head>, dark theme shell)
  pages/          index.astro (the entire single-page site)
public/
  cv.pdf          redacted CV served for download — regenerate via the redaction process
                  below, never commit an unredacted CV
```

## Local development

```sh
npm install
npm run dev       # http://localhost:4321
npm run build      # production build to ./dist/
npm run preview   # preview the production build locally
```

## Adding or updating content

- **New case study**: add a `.md` file to `src/content/projects/` following the frontmatter shape
  in any existing file (`title`, `stack`, `outcome`, `order`). No component changes needed.
- **Skills**: edit the `skillGroups` array in `src/pages/index.astro` (category name + skill list
  with a 1–4 proficiency level, rendered by `SkillGroup.astro`).
- **CV**: `public/cv.pdf` must stay redacted — no home address, phone number, date of birth, or
  marital status. Keep permit status and citizenship (career-relevant, not personal-safety
  sensitive).

## Deployment

Deployed on **Vercel**, connected to this GitHub repo for git-push deploys (no manual server
steps). Custom domain **puljic.ch** is managed via **Hosttech DNS** (DNS-only — Hosttech is not
the hosting target), pointed at Vercel with the A/CNAME records Vercel's domain settings specify.

To deploy a change: push to `main` — Vercel builds and deploys automatically. To update DNS,
change records directly in the Hosttech control panel.
