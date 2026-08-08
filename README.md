# 🌴 Hacker House Goa 2026 — Builder Studio

A client-side **Builder Ticket / Team Pass generator** for Hacker House Goa 2026. Upload a photo, fill in a few details, and get a branded, ticket-style badge back in seconds — no login, no backend, no signup wall.

**[Live Demo →](#)** <!-- TODO: replace with your deployed link -->

![Preview](./preview.png)
<!-- TODO: add a screenshot of the tool here -->

---

## What it does

- **Solo Pass** — a single Builder Ticket: your photo, name, stack/role, and a generated "builder class"
- **Team Pass** — one ticket combining 2–3 teammates under a shared crew name
- Drag-and-drop or camera photo upload (JPG, PNG, HEIC)
- Drag-to-reposition and zoom on the uploaded photo for off-center crops and any aspect ratio
- A "Currently Shipping" status line and a "Builder Class" field, both with a shuffle button for fun auto-generated options
- Live preview that updates instantly as you type
- One-click **PNG download** at 1000×1500
- **Share to X** with a pre-filled caption (`#FrameInGoa`) — attaches the image directly via the Web Share API on supported browsers, with a download-and-compose fallback on desktop

## Design

The ticket layout includes a photo frame, pill-style info fields, a shipping-status banner, tag chips, a dashed perforation line with punched notches, and a decorative QR/barcode strip in the stub. The QR and barcode patterns are **visual only** — they are not functional scan codes, just texture to sell the ticket feel.

## Why it's fast

Everything — photo compositing, text layout, ticket rendering — happens in the browser using the HTML5 Canvas API. There's no upload to a server, no processing queue, and no loading screen. The photo never leaves the user's device until they choose to download or share it.

## Tech stack

- Vanilla JavaScript (no framework, no build step)
- HTML5 Canvas for the ticket rendering
- SVG for the ocean-gradient backdrop
- Single self-contained `index.html` file

## Running locally

No install, no dependencies. Just open the file:

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
open index.html      # macOS
# or just double-click index.html / drag it into a browser
```

For a local dev server (optional, useful for testing on mobile via LAN):

```bash
npx serve .
```

## Deploying

This is a static site — one HTML file, no build step. Any of these work:

- **Netlify Drop** — drag `index.html` onto [app.netlify.com/drop](https://app.netlify.com/drop)
- **GitHub Pages** — enable Pages on this repo, pointing at the root/`main` branch
- **Vercel** — `vercel deploy` from this directory

## Project structure

```
.
├── index.html      # everything: markup, styles, canvas rendering, share logic
└── README.md
```

## Customization / before you submit

This repo currently ships with **placeholder branding** — colors, wordmark, and event dates are not final. Before submitting:

- [ ] Replace the color tokens in the `:root` CSS block (`--navy`, `--teal`, `--terracotta`, `--sun`, etc.) with the official Hacker House Goa 2026 palette
- [ ] Replace the text-based wordmark in the `drawHeader()` JS function with the real logo (swap `ctx.fillText(...)` calls for `ctx.drawImage(...)`)
- [ ] Confirm the event dates shown in the header (currently a placeholder: `28–31 OCT 2026`)
- [ ] Replace the demo photo in the screenshot/preview above with a real one
- [ ] Update the `#FrameInGoa` hashtag / site URL if these change

## License

<!-- TODO: pick one, e.g. MIT -->
MIT
