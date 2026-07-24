# Scaleturn

Single-page company landing site for Scaleturn — Sanjay Maharjan's software
studio (AI-assisted delivery of automation, document processing, and web
engineering). Track-2 owned asset for MyAgentOrganization.

## How it works

- **Plain static HTML + one CSS file.** No build step, no framework, no
  JavaScript. `index.html` is the entire site — one page, anchor-linked
  sections (`#services`, `#work-with-us`, `#resources`).
- **`style.css`** reuses the design tokens (colors, spacing, type scale) from
  the sibling `getting-paid-nepal` guide site for visual consistency across
  Scaleturn properties, but is otherwise a fresh, lean stylesheet — no
  affiliate-banner, disclaimer-box, or table components carried over, since
  this page doesn't need them.
- **No forms, no cookies, no analytics, no tracking.** The page only links
  out (Upwork profile, `mailto:`, the guide site). Because it collects
  nothing, there's no privacy policy page — the footer says so directly
  instead of shipping a stub legal page with nothing behind it.
- **Contact routes are external, not embedded.** "Work with us" links to the
  Upwork profile and a `mailto:` address — no contact form, no email
  collection on this domain.

## Sections

1. Hero — one-line positioning statement.
2. Services — three fixed-scope service categories (AI/LLM integration,
   document & back-office automation, legacy migration & web engineering).
3. Work with us — Upwork profile link + `mailto:` link.
4. Resources — link out to `gettingpaid.scaleturn.com`, the free guide site.
5. Footer — copyright, location, no-data-collected note.

## SEO basics in place

- `<title>` and `<meta name="description">`.
- `<link rel="canonical">`.
- `robots.txt` + `sitemap.xml` (single URL — this is a one-page site).
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

No CMS — edit `index.html` directly. If the page grows past one screen's
worth of sections, reconsider before adding a second page; the "single-page
landing" framing is a deliberate scope choice, not an MVP shortcut to later
expand without reconsidering.
