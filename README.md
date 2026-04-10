[README.md](https://github.com/user-attachments/files/26632439/README.md)
# Anson Wong — Technical Writing Portfolio

A single-page technical writing portfolio built to mirror the look and feel of API documentation. Hosted on GitHub Pages.

**Live site:** _add your GitHub Pages URL here_

## About

This is the portfolio of **Anson Wong**, a technical writer based in Richmond Hill, Ontario. Anson spent three years at [PheedLoop](https://pheedloop.com) (event management SaaS), where he led and grew the Knowledge Base to over 500 articles across five separate sites. He holds a journalism degree from the University of Toronto and has been published in Yahoo Finance and the Financial Post. He is currently focused on technical writing roles in Ontario, with an emphasis on API documentation.

- **LinkedIn:** <https://www.linkedin.com/in/anson-wong-3294021b2/>
- **Email:** Ansonwong474@gmail.com

## The Site

A deliberately minimal, dependency-free site that uses a three-column layout — left navigation, middle commentary panel, right content panel — to mirror the visual conventions of modern API documentation (think Stripe, Twilio). The commentary column lets Anson narrate the writing decisions behind each article alongside the article itself.

### Tech stack

- Plain **HTML**, **CSS**, and **JavaScript** in a single `index.html` file
- No frameworks, no build step, no dependencies
- Hosted on **GitHub Pages**

### Features

- Three-column documentation-style layout on desktop
- Mobile responsive: hamburger nav drawer; commentary collapses into a toggle (expanded by default so readers don't miss it)
- Click-to-expand image lightbox (click outside or press <kbd>Esc</kbd> to close)
- About Me page loads by default

## Repository structure

```
/
├── index.html          # The entire site
├── images/             # Screenshots, GIFs, and bio photo
│   ├── anson.jpg
│   ├── reg-categories-step-01.png
│   ├── zapier-step-03.gif
│   └── ...
└── README.md
```

## Content

The site contains **15 items** organized into seven navigation sections:

- **OpenAPI** — PheedLoop OpenAPI specification (featured showcase piece demonstrating OpenAPI specification authoring)
- **Registration** — Creating registration categories; Creating registration ticket types
- **Onsite & Printing** — Setting up rented Epson printers; Epson printer troubleshooting
- **Integrations** — Integrating Zapier; Setting up Moneris; Using Wild Apricot with PheedLoop
- **Developer** — Setting up webhooks; Why was my webhook disabled?
- **Experiences** — Sessions channels feature; Preparing to white label your app; Translating text, buttons & labels
- **Internal** — Style guide & copywriter role; Keyword Framework 2.0

The PheedLoop Knowledge Base articles each link back to the original published source. The Internal samples (Style Guide, Keyword Framework) have no external link.

## Article data structure

Each article is defined as an entry in the `A` object inside `index.html`:

```js
'article-id': {
  c: { eyebrow, title, tags, intro, body, annotation, decisions, url },
  content: { type, title, blocks: [] }
}
```

Each block in `content.blocks` follows this shape:

```js
{ label, badge: { text, type }, heading, body, list, table: { headers, rows }, img }
```

Badge types: `tip` (green), `note` (blue), `warning` (amber), `purple`.

## Image conventions

- All images live in `images/` next to `index.html`
- Naming: `{article-id}-{step-label}.png` — for example, `reg-categories-step-01.png`
- GIFs are supported (e.g. `zapier-step-03.gif`)
- Images are embedded inside a block's `body` string as `<img src="images/filename.png" alt="description" />`
- Profile photo: `images/anson.jpg`

## Running locally

No build step. Clone the repo and open `index.html` in a browser, or serve the folder with any static server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Pushes to the default branch are published automatically via GitHub Pages.

## License & usage

**All rights reserved.** This repository is published publicly so prospective employers and collaborators can view Anson Wong's technical writing portfolio. It is **not** open source, and nothing in this repository is licensed for reuse.

Please do not, without prior written permission from Anson Wong:

- Copy, republish, or redistribute any of the writing samples, commentary, annotations, or other written content found on this site or in this repository
- Reuse the site's HTML, CSS, or JavaScript code in your own projects
- Use any of the screenshots, images, or the bio photo (`images/anson.jpg`)
- Train machine learning models on the contents of this repository
- Present any of this work as your own in a portfolio, application, or published work

The PheedLoop Knowledge Base articles linked from this site remain © PheedLoop and are reproduced here in portfolio form with attribution and links back to the original sources. The internal samples (Style Guide, Keyword Framework) and the PheedLoop OpenAPI specification are original work by Anson Wong.

If you'd like to reference, quote, or reuse anything here, please reach out first: **Ansonwong474@gmail.com**.
