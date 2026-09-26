# primedentalpk.com — Prime Dental website

Static site for Prime Dental, served by GitHub Pages at **https://primedentalpk.com**.

## Before it goes live

Open `index.html` and edit the two lines just after `<body>`:

```js
var WHATSAPP_NUMBER = "923001234567";  // REPLACE — country code first, digits only
var YOUTUBE_ID      = "";              // 11-char id from the YouTube link
```

`WHATSAPP_NUMBER` is currently a **placeholder** and must be replaced before sharing
the link — every CTA on the page reads from it. The video section stays a labelled
placeholder until `YOUTUBE_ID` is filled in.

## Publishing

1. Push this folder to a public GitHub repo.
2. Settings -> Pages -> Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
3. Settings -> Pages -> Custom domain: `primedentalpk.com` (the `CNAME` file already sets this).
4. Tick **Enforce HTTPS** once the certificate is issued.

## DNS (Cloudflare)

Add these, and set every one to **DNS only** (grey cloud, NOT the orange proxy) — with
proxying on, GitHub can never validate the domain and the HTTPS certificate silently
fails to issue.

| Type  | Name | Value                  |
|-------|------|------------------------|
| A     | @    | 185.199.108.153        |
| A     | @    | 185.199.109.153        |
| A     | @    | 185.199.110.153        |
| A     | @    | 185.199.111.153        |
| CNAME | www  | <username>.github.io   |

## Images

`img/` holds the screenshots, captured from the real app running seeded, fabricated
demo data — no real patient information appears anywhere on this site. To reshoot,
import `PrimeDental-DEMO-SEED.json` into a clean install first.

`img/og-card.jpg` (1200x630) is the WhatsApp / Facebook link preview card. It is
referenced by absolute URL in the `og:image` tag — relative paths are ignored by
those scrapers.

## Clinic vs software

This domain serves the **software**. If the clinic ever needs its own page, put it on
`clinic.primedentalpk.com` as a separate repo with its own `CNAME`, rather than mixing
two audiences on one site.
