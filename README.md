# Birma AI Audit

A process/workflow compliance auditing tool — define expected process steps, log what CCTV/egocentric footage shows against them, and get AI-assisted efficiency analysis and downloadable reports.

## Structure

- `index.html` — the app (self-contained, no build step)
- `privacy-policy.html`, `terms.html` — legal pages (⚠️ templates — have these reviewed before going live, and replace the `[placeholders]`)
- `robots.txt`, `sitemap.xml` — replace `[your-domain.example]` with your real domain once you know it
- `404.html` — custom error page

## Deploying with GitHub Pages

1. Push this folder to a GitHub repo (see steps below)
2. In the repo, go to **Settings → Pages**
3. Under "Build and deployment", set **Source: Deploy from a branch**
4. Set **Branch: main**, folder **/ (root)**, then **Save**
5. GitHub gives you a URL like `https://[username].github.io/[repo-name]/` — usually live within a minute or two

## Known limitation when self-hosted

The **Auto-Analyze Footage** tab's AI judgment calls Claude directly through the claude.ai artifact runtime, which only exists inside claude.ai chat. On GitHub Pages (or any external host), that tab will show "isn't available in this view" until it's connected to your own backend that calls the Anthropic API with your own key (never put an API key in this client-side file). Everything else — Workflows, Clients, Run Audit, Dashboard, reports — works fully on GitHub Pages, with data saved per-visitor via browser local storage.
