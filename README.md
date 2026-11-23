# EAMStack

A modern, hybrid-light/dark static website for Enterprise Asset Management knowledge, architecture and resources. Built with Astro and deployed to GitHub Pages.

## Requirements

- Node.js 20.3.0 or later (Node.js 22 LTS recommended)
- Git
- A GitHub account

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Astro (normally http://localhost:4321).

## Build and preview

```bash
npm run build
npm run preview
```

The generated static site is written to `dist/`.

## Publish using GitHub Pages

1. Create a GitHub repository named `eamstack` (or use `<your-username>.github.io` for a user site).
2. Upload/push the contents of this project to the repository's `main` branch.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment → Source**, select **GitHub Actions**.
5. The workflow at `.github/workflows/deploy.yml` builds Astro and publishes `dist/` automatically after each push to `main`.
6. Wait for the workflow to finish. For a project repository, the default URL is `https://<your-username>.github.io/eamstack/`. For a user-site repository named `<your-username>.github.io`, the URL is `https://<your-username>.github.io/`.

The workflow detects the repository name and sets the correct Astro base path automatically.

## Add your own content

- Edit the homepage: `src/pages/index.astro`
- Update the About page: `src/pages/about.astro`
- Update technology descriptions: `src/pages/technologies.astro`
- Add knowledge articles: create a new `.astro` page under `src/pages/knowledge/` and link it from `src/pages/knowledge/index.astro`.
- Update email and social links in `src/components/SiteFooter.astro`.
- Replace `public/favicon.svg` and `public/images/` assets with your own branding.

## Custom domain (optional)

1. Register a domain with your preferred registrar.
2. In **Repository → Settings → Pages → Custom domain**, enter the domain.
3. Configure the DNS records recommended by GitHub Pages.
4. Add a `CNAME` file in `public/` containing the domain name (for example `www.example.com`).
5. Update `site` in `astro.config.mjs` or set `SITE_URL` in the workflow.
6. Enable **Enforce HTTPS** after DNS validation.

## Notes

- This is a static site: no database, server-side runtime, CMS or contact-form backend is included.
- The contact page uses an email link. Replace the placeholder address before publishing.
- Content is starter copy. Review technical claims, add your own articles and confirm branding before making the site public.
