# kodahpip.com

The Tune Everything site. Built with Astro, hosted on Vercel.

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

## Go live on Vercel (about 10 minutes)

1. Install Node.js from [nodejs.org](https://nodejs.org) (the LTS version), if you don't have it.
2. In Terminal, from this folder: `npm install`, then `npm run dev` to see the site at http://localhost:4321.
3. Put this folder on GitHub (GitHub Desktop is easiest: File → Add Local Repository → Publish).
4. At [vercel.com](https://vercel.com), choose **Add New → Project**, import the GitHub repo, and click **Deploy**. Vercel detects Astro on its own.
5. Upgrade the Vercel team to **Pro** ($20/month). The free Hobby plan is for non-commercial use only.
6. In the Vercel project, open **Settings → Domains**, add `kodahpip.com` and `www.kodahpip.com`, and follow the DNS instructions it shows.

## Leaving Wix safely

1. Find where kodahpip.com is registered (Wix, GoDaddy, Google/Squarespace…).
2. If any email uses @kodahpip.com, keep its **MX** records exactly as they are when you change DNS.
3. Export any Wix blog posts you want to keep.
4. Point the domain to Vercel (step 6 above) and confirm the site, form and email work for a few days.
5. If Wix is the registrar, transfer the domain out first. Then cancel the Wix plan.

## Commands

| Command | What it does |
| --- | --- |
| `npm install` | Install dependencies (first time only) |
| `npm run dev` | Local preview at http://localhost:4321 |
| `npm run build` | Build the production site into `dist/` |
