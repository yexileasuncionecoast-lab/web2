# web2

Static login page, served by Cloudflare Workers (static assets), auto-deployed from this GitHub repo.

## Structure
- `public/index.html` — the login page (self-contained: HTML + CSS + JS, no build step)
- `wrangler.jsonc` — tells Cloudflare to serve everything in `public/` as static assets

## Why the last build failed
The Cloudflare Worker is connected to this GitHub repo, but the repo was empty — there was nothing for it to build or serve. Adding these files fixes that.

## Next steps
1. Upload these files to the `yexileasuncionecoast-lab/web2` GitHub repo (root of the repo, keeping the `public/` folder).
2. Cloudflare will pick up the push automatically and redeploy.
3. Once the build succeeds, enable a URL for the Worker under **Domains** (or add a custom domain) so you can view it live.
4. The sign-in form is currently a placeholder — it doesn't check real credentials yet. When you're ready to add real authentication (e.g. Cloudflare D1 for a user table, or an auth provider), let me know and I'll wire that up.
