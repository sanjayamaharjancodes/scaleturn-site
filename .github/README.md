# Scaleturn

Source of https://scaleturn.com/, the site of Scaleturn, Sanjay Maharjan's software studio in Bhaktapur, Nepal: client
software, royalty-free game asset packs, and links to the two free guide sites
(https://gettingpaid.scaleturn.com/ and https://scrapetools.scaleturn.com/).

This README lives in `.github/` so the Pages build does not publish it; GitHub still shows it on the repository page.

## How it works

- **Plain static HTML and one CSS file.** No build step, no framework. The only scripts are the GoatCounter page
  counter and Google's AdSense code. Five site pages: `index.html`, `game-assets.html`, `about.html`, `contact.html`,
  `privacy.html`, plus `favicon.ico`.
- **One product landing page, `ats-job-feed/index.html`** (served at `/ats-job-feed/`). It keeps its own inline styles
  and has no site nav; its footer links Home, About, Contact and Privacy and carries the GoatCounter and AdSense line.
  Its head and counter follow the rules below.
- **One nav and one footer, copied by hand.** Every page carries the same nav (Home, Data, Game assets, Guides, About,
  Contact) and footer (About, Contact, Privacy). Edit all five pages when either changes.
- **The home page leads with original data** (`#data`, since 19 Nov 2026, task ct-004): one card per report on
  scrapetools.scaleturn.com that is measured from Scaleturn's own job index, with its date, a summary and links to
  the report and its CSV. Every figure in a card is copied from that report's short answer; when a report is rebuilt,
  update its card. The ScrapeTools repository's `ct-004/check_live.py` checks the figures against the report pages.
- **`style.css`** holds design tokens first, then components, then one mobile breakpoint. `table.data` styles the
  measured-pack table on `game-assets.html`; `.data-card` the home page's data cards.
- **AdSense code on every page.** Each page's `<head>` carries the AdSense code snippet
  (`client=ca-pub-5554189148912369`, the id in `ads.txt`), and `index.html` also keeps the `google-adsense-account`
  meta tag. Copy both into any new page. `privacy.html` makes the AdSense disclosures (Google's cookies, other ad
  companies, opt-out links, Google's EU consent requirement). Both guide subdomains, ScrapeTools and Getting Paid
  Nepal, load the same AdSense code since 19 Nov 2026 (task ct-004); this site's `ads.txt` covers them. No forms. The site's own code sets no cookies,
  but the AdSense code can set Google cookies (such as `__gads`) on this domain. Contact is a `mailto:` link and the
  Upwork profile.

## Content rules

- Keep new content first-hand and checkable: measured, sourced and dated, not restated copy.
- `game-assets.html#measured` lists figures measured from each pack's release zip on 2026-11-15. Re-measure after a
  pack is rebuilt and update the table. Prices come from each itch.io page, which handles checkout.

## SEO basics

- `<title>`, `<meta name="description">` and `<link rel="canonical">` on every page.
- `robots.txt` and `sitemap.xml` (every page, with `lastmod`).
- Responsive viewport and a CSS breakpoint; no web fonts.

## Deployment

GitHub Pages serves the repository root of `main`. The apex domain `scaleturn.com` is set by the `CNAME` file and DNS
`A` records for the GitHub Pages IPs (185.199.108–111.153). Paths are root-relative.
