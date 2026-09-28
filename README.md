# kodahpip.com

The Tune Everything site. Built with Astro, hosted on Cloudflare (free plan).

## Change things yourself

| To change | Edit this file |
| --- | --- |
| Email, Calendly, form, newsletter, social links | `src/site.config.ts` |
| Homepage copy | `src/pages/index.astro` |
| Speaking topics and formats | `src/pages/speaking.astro` |
| About page (and portrait) | `src/pages/about.astro` |
| Essays | `src/pages/writing/` — one `.md` file per essay |
| Colors and fonts | `src/styles/global.css` (top of the file) |

**Add an essay:** copy `src/pages/writing/tune-everything.md`, rename it (the file name becomes the URL), and change the title, date and summary between the `---` lines. It appears on the homepage and the Writing page automatically.

**Add your portrait:** put the photo in `public/` (for example `public/kodah.jpg`) and set `const portrait = '/kodah.jpg';` at the top of `src/pages/about.astro`.

Or open this folder in Claude Code and just ask.

## Before launch

1. **Contact form.** Make a free form at [formspree.io](https://formspree.io) and paste its ID into `formspreeId` in `src/site.config.ts`. Until then, the form opens a pre-filled email.
2. **Newsletter.** Paste your Substack or Beehiiv signup link into `newsletterUrl`.
3. **Read every word.** The essay and the About page are drafts in your language. Rewrite anything that isn't exactly you.

## Hosting on Cloudflare

The site is fully static, so it runs on Cloudflare's free plan with unlimited bandwidth. `wrangler.jsonc` is the hosting config, and `public/_redirects` keeps the old Wix `/blog` and `/post/...` links working.

**Every push to `main` deploys automatically.** To preview locally the way Cloudflare serves it: `npm run build`, then `npx wrangler dev`.

**First-time setup** (already done for kodahpip.com; repeat for any new site):

1. At [dash.cloudflare.com](https://dash.cloudflare.com), go to **Workers & Pages → Create → Import a repository** and pick this GitHub repo.
2. Build command: `npm run build`. Deploy command: `npx wrangler deploy`. Leave the rest as is.
3. Add the domain to Cloudflare (**Add a domain**, Free plan) and set its nameservers at the registrar to the two Cloudflare shows.
4. In the Worker, open **Settings → Domains & Routes → Add → Custom domain** and add `www.kodahpip.com` and `kodahpip.com`.

## Leaving Wix safely

1. Find where kodahpip.com is registered (Wix, GoDaddy, Google/Squarespace…).
2. If any email uses @kodahpip.com, keep its **MX** records exactly as they are when you change DNS.
3. Export any Wix blog posts you want to keep.
4. Point the domain to Cloudflare (step 3 above) and confirm the site, form and email work for a few days.
5. If Wix is the registrar, transfer the domain out first. Then cancel the Wix plan.

## Commands

| Command | What it does |
| --- | --- |
| `npm install` | Install dependencies (first time only) |
| `npm run dev` | Local preview at http://localhost:4321 |
| `npm run build` | Build the production site into `dist/` |
| `npx wrangler dev` | Preview the built site exactly as Cloudflare serves it |
