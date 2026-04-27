# Gainer — marketing site (static)

A single static page for **Gainer** (workout tracker & training intelligence) so people can find the app on the web. This folder is **not** the iOS/Next app — deploy it as its own Vercel project.

## Use as its own repository

1. Create a new empty repo on GitHub (e.g. `gainer-site`).
2. From this machine, in the `gainer-site` directory:

   ```bash
   cd gainer-site
   git init
   git add index.html robots.txt sitemap.xml README.md
   git commit -m "Initial marketing page"
   git branch -M main
   git remote add origin https://github.com/YOUR_USER/gainer-site.git
   git push -u origin main
   ```

3. Vercel: [New Project](https://vercel.com/new) → import `gainer-site` → **Deploy** (Hobby is free for personal use).

4. When you have a stable URL (e.g. `https://gainer-site.vercel.app` or a custom domain), **replace** every `https://gainer-site.vercel.app/` in:
   - `index.html` (`<link rel="canonical">`, `og:url`)
   - `robots.txt` (`Sitemap:` line)
   - `sitemap.xml` (`<loc>`)

5. In `index.html`, replace the generic `https://apps.apple.com/` button `href` with your real **App Store** product URL (includes your app id).

## Custom domain (later)

1. Vercel project → **Settings** → **Domains** → **Add** your domain.
2. Add the DNS records Vercel shows (A for apex, or CNAME for `www`). See: [Add a custom domain](https://vercel.com/docs/domains/working-with-domains/add-a-domain).
3. Update the three URLs in step 4 above to use your new domain.

## What this is not

- It does not host the full web app. If you need the marketing URL to show this page only, use a **separate** Vercel project linked only to this repo (or this folder as its own repo), not the app repo.
