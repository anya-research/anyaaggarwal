# Repository Guide

## What this repository is

This is Anya Aggarwal's personal portfolio website. It is a statically prerendered SvelteKit site deployed to GitHub Pages at `https://anya-research.github.io/anyaaggarwal/`.

The site contains:

- the portfolio homepage with personal, project, work, and contact sections.

## Stack and package management

- Svelte 5 and SvelteKit 2
- TypeScript with strict checking
- Tailwind CSS 4 and DaisyUI
- `@sveltejs/adapter-static`, with output written to `build/`
- pnpm only; `pnpm-lock.yaml` is the canonical lockfile

Do not create, update, or commit `package-lock.json`. Do not commit generated `build/`, `.svelte-kit/`, or `node_modules/` content.

## Repository map

- `src/routes/+page.svelte` — all portfolio homepage content and the ordered lists of projects and work experience.
- `src/routes/+layout.svelte` — global styles, favicon, SEO metadata, Open Graph tags, and Person JSON-LD.
- `src/routes/+layout.ts` — site-wide prerendering.
- `src/lib/components/` — reusable `Card`, `Project`, `WorkExperience`, and link wrappers.
- `src/lib/assets/` — portfolio profile picture and company logos.
- `src/app.css` — global Tailwind/DaisyUI setup and JetBrains Mono font.
- `.github/workflows/deploy.yml` — GitHub Pages build and deployment on pushes to `master`.

## Editing conventions

- Keep homepage content in `src/routes/+page.svelte`; extend the existing components instead of duplicating their markup.
- Preserve the order of portfolio sections and project cards unless reordering is explicitly requested.
- Treat project names, descriptions, technology tags, and destination URLs as exact public copy. Verify changed public URLs before publishing.
- Use the existing Tailwind/DaisyUI visual language, including light/dark styles and responsive `md:` behavior. Check visual changes at desktop and narrow mobile widths.
- Follow the local component style when making a small edit.
- Use tabs, single quotes, no trailing commas, and the 100-column Prettier configuration in `.prettierrc`.

## Commands

Run commands from the repository root:

```sh
pnpm install
pnpm run dev
pnpm run check
pnpm run lint
pnpm run build
pnpm run preview
```

`pnpm run lint` is a Prettier check; there is no separate ESLint configuration or automated test suite.

For a normal change, run at least:

```sh
pnpm run check
pnpm run lint
pnpm run build
```

## Deployment

Every push to `master` triggers `.github/workflows/deploy.yml`, which installs with pnpm, builds the static site, uploads `build/`, and deploys it to GitHub Pages.
