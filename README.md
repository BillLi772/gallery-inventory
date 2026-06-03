# Bruno David Gallery — Inventory

Static single-page inventory site for Bruno David Gallery. The browser loads
artwork data live from a public Google Sheet on every page load, so updating
the sheet is all that's needed to update the website.

## How it works

- `index.html` is a self-contained page (HTML + CSS + JS, no build step).
- On load, it fetches the inventory CSV from a Google Sheet (`SHEET_ID` near
  the top of the `<script>` block).
- The sheet must be shared as **Anyone with the link → Viewer**.

## Sheet schema (row 1 headers)

```
artist | title | year | media | medium | width | height | depth | price | colors | image_url
```

- `media` — one of: Painting, Print, Photograph, Sculpture, Work on Paper, etc.
  (drives the Media filter chips)
- `medium` — descriptive (e.g. "Acrylic on canvas")
- `width` / `height` / `depth` — numbers in inches (depth optional)
- `price` — number; leave blank to show "Contact for price"
- `colors` — comma-separated color ids from the color list in the script
- `image_url` — direct URL (Squarespace CDN, etc.)

## Deploy

Hosted on Cloudflare Pages via GitHub integration — every push to `main`
auto-deploys.

## Local preview

Just open `index.html` in a browser. No server required.
