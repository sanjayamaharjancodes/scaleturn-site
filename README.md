# Scaleturn

Single-page company landing site for Scaleturn — Sanjay Maharjan's software
studio (AI-assisted delivery of automation, document processing, and web
engineering). Track-2 owned asset for mandala.

## How it works

- **Plain static HTML + one CSS file.** No build step, no framework, no
  JavaScript (apart from the GoatCounter snippet). Five pages: `index.html`,
  `game-assets.html`, `about.html`, `contact.html`, `privacy.html`. Every page
  carries the same nav (Home, Game assets, Guides, About, Contact) and the
  same footer (About, Contact, Privacy); edit all five when either changes.
- **`style.css`** reuses the design tokens (colors, spacing, type scale) from
  the sibling `getting-paid-nepal` guide site for visual consistency across
  Scaleturn properties, but is otherwise a fresh, lean stylesheet — no
  affiliate-banner or disclaimer-box components carried over. It has one
  small `table.data` style for the measured-pack table on `game-assets.html`.
- **No forms, no cookies, no ads on this domain's pages.** The page only
  links out (Upwork profile, `mailto:`, the guide site) and counts views with
  GoatCounter. `privacy.html` covers this domain and the AdSense disclosure
  Google requires for the guide subdomains.
- **Contact routes are external, not embedded.** "Work with us" links to the
  Upwork profile and a `mailto:` address — no contact form, no email
  collection on this domain.

## Sections

1. Hero — one-line positioning statement.
2. Services — three fixed-scope service categories (AI/LLM integration,
   document & back-office automation, legacy migration & web engineering).
3. Work with us — Upwork profile link + `mailto:` link.
4. Game assets — three product cards; the full list is `game-assets.html`.
5. Guides (`#guides`) — deep links into `gettingpaid.scaleturn.com` and
   `scrapetools.scaleturn.com`, the two free guide sites.
6. Footer — About/Contact/Privacy links, copyright, location, no-data note.

`game-assets.html` has a "Measured from the release files" table (#measured).
Every figure in it was measured on 2026-11-15 from each pack's release zip
(`<pack repo>/out/dist/*.zip`) by `measure_packs.py`, kept with the md-004
proof in the org memory repo. Re-run it after a pack is rebuilt and update the
table; prices come from each itch.io page.

## SEO basics in place

- `<title>` and `<meta name="description">`.
- `<link rel="canonical">`.
- `robots.txt` + `sitemap.xml` (all five pages, with `lastmod`).
- Mobile-friendly (responsive viewport meta, CSS breakpoint).
- No JS, no web fonts, no blocking render — fast by default.

## Deployment

Hosted on GitHub Pages, served from the repo root of the `main` branch
(legacy Pages build, plain HTML/CSS, no Jekyll processing needed).

Custom domain: `scaleturn.com` (apex domain) via a `CNAME` file at the repo
root + DNS `A` records pointing at the four GitHub Pages IPs
(185.199.108–111.153). This is a GitHub **user/org-independent project
site at the domain root** — unlike a `github.io/<repo>` project-page
subpath, all paths here are already root-relative by nature of the apex
domain, so no path-rewriting concerns apply.

Live URL: https://scaleturn.com/

## Updating content

No CMS — edit the `.html` files directly. The site grew from one page to
five on 2026-11-15 (task md-004), so the domain itself shows what Scaleturn
does. Keep new content first-hand and checkable (measured, sourced, dated),
not restated copy.
