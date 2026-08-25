# Your Portfolio — Setup & Hosting Guide

A single-file, dark-themed portfolio built for a Data Engineer / Data Scientist.
No build tools, no dependencies to install — it's one `index.html` file with
CSS and JS inline, plus Google Fonts loaded from a CDN.

## 1. Customize it first

Open `index.html` in any text editor and update these placeholders:

| What | Where to find it |
|---|---|
| Name & role | `<title>`, hero `<h1>`, `#roleText` cycling list in the `<script>` at the bottom |
| Bio / about text | `#about` section |
| Skills | `#skills` section — edit the `<span class="tag">` items |
| Work history | `#experience` section — one `.tl-item` per job |
| Projects | `#projects` section — one `.project-card` per project |
| Email / GitHub / LinkedIn | `#contact` section |
| Résumé | Replace `resume.pdf` links with your actual resume file, or remove them |
| Favicon / page title | `<title>` tag in `<head>` |

The accent colors, fonts, and layout are controlled by the CSS variables at the
top of the `<style>` block (`--bg`, `--accent`, `--accent-2`, etc.) if you want
to adjust the palette later.

Add a real `resume.pdf` file into the same folder as `index.html` if you want
the résumé buttons to work (or replace them with a link to a hosted PDF).

## 2. Preview it locally

Just double-click `index.html` to open it in your browser — no server needed.

## 3. Hosting options (all free)

### Option A — GitHub Pages (recommended, free custom domain support)

1. Create a GitHub account if you don't have one: https://github.com
2. Create a new repository, e.g. `your-username.github.io` (using this exact
   name gives you a live site at `https://your-username.github.io` with zero
   extra config).
3. Upload `index.html` (and `resume.pdf` if you have one) to the repo — you can
   drag and drop files directly on the GitHub website (Add file → Upload files).
4. Go to the repo's **Settings → Pages**, set the source branch to `main` and
   folder to `/ (root)`, then save.
5. Your site will be live at `https://your-username.github.io` within a
   minute or two.

If you name the repo something other than `your-username.github.io`, your
site will live at `https://your-username.github.io/repo-name` instead.

### Option B — Netlify (drag-and-drop, fastest)

1. Go to https://app.netlify.com/drop
2. Drag the whole `portfolio` folder (containing `index.html`) onto the page.
3. Netlify instantly gives you a live URL like `random-name.netlify.app`.
4. Optional: create a free account to set a custom subdomain or connect your
   own domain name.

### Option C — Vercel

1. Go to https://vercel.com and sign up (free).
2. Click **Add New → Project → Deploy without Git** (or connect a GitHub repo
   containing this file).
3. Vercel deploys it and gives you a live URL like `your-project.vercel.app`.

### Option D — Cloudflare Pages

1. Go to https://pages.cloudflare.com
2. Create a project, choose "Upload assets", and upload `index.html`.
3. You get a live URL like `your-project.pages.dev`.

## 4. Using a custom domain (optional)

Once hosted on any of the above, you can point a domain you own (e.g. from
Namecheap, Google Domains, or Cloudflare Registrar) at it:

- **GitHub Pages**: add a `CNAME` file with your domain, then set your DNS
  provider's A/CNAME records per GitHub's docs.
- **Netlify / Vercel / Cloudflare Pages**: add the domain in the project's
  dashboard under "Domains" — they'll show you exactly which DNS records to
  add.

All four hosts issue free HTTPS certificates automatically.

## 5. Keeping it updated

- **GitHub Pages**: edit the file on GitHub (or push via `git`) and the site
  redeploys automatically within a minute.
- **Netlify Drop**: re-drag the folder onto https://app.netlify.com/drop to
  redeploy (or connect a GitHub repo for automatic redeploys on every push).
- **Vercel / Cloudflare Pages**: connect a GitHub repo for automatic
  redeploys on every push, which is the most convenient long-term setup.

**Recommended path:** put the folder in a GitHub repo from the start (Option
A), even if you deploy through Netlify or Vercel by connecting that repo —
you get free hosting, automatic redeploys, and version history all at once.
