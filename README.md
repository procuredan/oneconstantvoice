# oneconstantvoice.org

Volunteer-recruiting lead site for CASA (Court Appointed Special Advocates).
Mission-forward landing page → captures interested volunteers → procure-lead-engine → procure-leads D1 → crm.procuremedia.com.

First market: **Idaho's 4th Judicial District** (Family Advocates — Ada, Boise, Elmore, Valley Counties).
Built to roll out nationally: change the `CONFIG` block in `index.html` per program.

## Files
- `index.html` — landing page (form posts to `procure-lead-engine/submit`, `lead_source=oneconstantvoice.org`)
- `thank-you.html` — conversion page (fires GA4 `generate_lead` + Google Ads conversion)
- `privacy-policy.html`, `terms.html` — TCPA-aware legal
- `sitemap.xml`, `robots.txt`
- `SITES-entry.txt` — paste into the procure-lead-engine `SITES` object, then redeploy the worker

## Before going live (TODO)
1. Replace `G-XXXXXXXXXX` (GA4) and `AW-XXXXXXXXXX` + conversion label in `index.html` and `thank-you.html`.
2. Confirm `engine_url` (`procure-lead-engine.dan-fda.workers.dev`) and add the `SITES-entry.txt` block to the worker.
3. Swap the hero image / quote / local stats for real Family Advocates assets + a real volunteer story.

## Deploy (Cloudflare Pages)
```bash
npx wrangler pages deploy . --project-name oneconstantvoice-org --branch main
```
Then add custom domains `oneconstantvoice.org` + `www` in the Pages dashboard.
