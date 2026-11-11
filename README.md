# HanuVerse Enterprises website

A single-page static site for M/S HanuVerse Enterprises (event production, decor and management, Jaipur). No build step: it is plain HTML, CSS and JavaScript in `index.html`, with images in `img/`.

## Run it locally

```bash
python -m http.server 5180
```

Then open http://localhost:5180.

## Before going live

Contact details (phone, WhatsApp and email) appear in `index.html` (contact section and footer) and in the contact block of `privacy.html` and `terms.html`. Update all of them together if they change.

Also:

- `og:image` in the `<head>` uses a relative path. Once the domain is known, change it to the full URL (for example `https://yourdomain.in/img/og.jpg`) so link previews work on WhatsApp and social apps.
- Add a `sitemap.xml` and a `<link rel="canonical">` once the domain is known.
- Have a lawyer review `privacy.html` and `terms.html`, then update the "Last updated" date if anything changes.
- Get a quick written OK from Dream Stream Events and The Wedding Toli for the photos under the **Partner Work** tab.
- Some HanuVerse photos are Instagram reel cover frames and may not match their labels (for example "Sangeet Night"). Swap in original photos where you can.

## Editing content

All gallery content lives near the top of the `<script>` block in `index.html`:

- `EVENTS`: HanuVerse's own events. Each has a category `c`, a name `n`, a description `d` and an image path `img`.
- `PARTNERS` and `PARTNER_WORK`: partner photos, shown under the **Partner Work** tab and credited with a link in the full-size view.
- `STATS`: leave empty until you have real, verifiable numbers (for example `{n:"40+", l:"Events delivered"}`). The section stays hidden while it is empty.

Keep photos under about 1400 px on the long edge so the page stays fast.

## Deploying

Any static host works: Vercel, Netlify, GitHub Pages or Cloudflare Pages. Point it at the repository root; there is no build command and the output directory is the root.
