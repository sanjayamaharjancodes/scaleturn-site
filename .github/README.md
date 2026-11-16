# Scaleturn

Source of https://scaleturn.com/, the site of Scaleturn, Sanjay Maharjan's software studio in Bhaktapur, Nepal: client
software, royalty-free game asset packs, and links to the two free guide sites
(https://gettingpaid.scaleturn.com/ and https://scrapetools.scaleturn.com/).

This README lives in `.github/` so the Pages build does not publish it; GitHub still shows it on the repository page.

## How it works

- **Plain static HTML and one CSS file.** No build step, no framework. The only scripts are the GoatCounter page
  counter and Google's AdSense code. Five pages: `index.html`, `game-assets.html`, `about.html`, `contact.html`,
  `privacy.html`, plus `favicon.ico`.
- **One nav and one footer, copied by hand.** Every page carries the same nav (Home, Game assets, Guides, About,
  Contact) and footer (About, Contact, Privacy). Edit all five pages when either changes.
- **`style.css`** holds design tokens first, then components, then one mobile breakpoint. `table.data` styles the
  measured-pack table on `game-assets.html`.
- **AdSense code on every page.** Each page's `<head>` carries the AdSense code snippet
  (`client=ca-pub-5554189148912369`, the id in `ads.txt`), and `index.html` also keeps the `google-adsense-account`
  meta tag. Copy both into any new page. `privacy.html` makes the AdSense disclosures (Google's cookies, other ad
  companies, opt-out links). The guide subdomains load no ad code. No forms. The site's own code sets no cookies,
  but the AdSense code can set Google cookies (such as `_gads`) on this domain. Contact is a `mailto:` link and the
  Upwork profile.

## Content rules

- Keep new content first-hand and checkable: measured, sourced and dated, not restated copy.
- `game-assets.html#measured` lists figures measured from each pack's release zip on 2026-11-15. Re-measure after a
  pack is rebuilt and update the table. Prices come from each itch.io page, which handles checkout.

## SEO basics

- `<title>`, `<meta name="description">` and `<link rel="canonical">` on every page.
- `robots.txt` and `sitemap.xml` (all five pages, with `lastmod`).
- Responsive viewport and a CSS breakpoint; no web fonts.

## Deployment

GitHub Pages serves the repository root of `main`. The apex domain `scaleturn.com` is set by the `CNAME` file and DNS
`A` records for the GitHub Pages IPs (185.199.108–111.153). Paths are root-relative.
