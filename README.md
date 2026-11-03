# Behind the card — static site

This folder is the QR destination. It is a complete static site: `index.html`
plus `assets/`. The page is the same one built as `../behind_the_card.html`,
wrapped for normal hosting.

## Deploy

Any static host works. The simplest:

1. Drag this `site/` folder onto **Netlify Drop** (app.netlify.com/drop).
2. Copy the public URL.
3. Generate the card QR from the project root:

```bash
.venv/bin/python showcase_materials/make_qr.py --url https://your-site.example
```

This writes `showcase_materials/output/qr.png` and `qr.svg`. Print the SVG at
about 30 × 30 mm for the card back.

Other options: Vercel, GitHub Pages, Cloudflare Pages, or any web server.
The page needs internet access only for the Google Fonts (Bodoni Moda,
Manrope, JetBrains Mono).

## Rebuild

Edit `../behind_the_card.html`, then:

```bash
.venv/bin/python showcase_materials/build_site.py
```

The wrapper script copies the two assets and writes `site/index.html`.

## What is on the page

- Hero: “This card was written by a robot.”
- Capture: the actual captured strokes, with a **Replay the strokes** button.
- Model: clickable LSTM + attention + MDN diagram.
- Two ways: exact replay vs continuing with the model.
- Arm: Dobot Magician, path, pen state, paper.
- Thank you: Radhika’s handwritten signature and the People’s Choice ask.
