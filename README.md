# Meridian Pulse — Shipment Tracker Explainer

A live, in-browser data-visualization video concept built for a fictional global shipping brand, **Meridian**, showing its real-time container-tracking platform in action. Made as a portfolio piece for marketing/content roles in the shipping & logistics industry.

**[View the live demo →](https://hwushyam2005.github.io/Meridian_Pulse_2/)** *(add your GitHub Pages link here once deployed)*

---

## What this is

A 30-second explainer concept structured the way real supply-chain visibility content is built by logistics marketing teams:

**Title → animated shipping route across four real ports → live ETA tick → predictive delay alert → trust stats → call to action.**

The centerpiece is a **dot-matrix world map** — continents rendered as clusters of dots (the same visual style used by companies like Stripe) — with a shipping route plotted at the **real geographic coordinates** of four major ports:

| Port | Longitude | Latitude |
|---|---|---|
| Shanghai | 121.47°E | 31.23°N |
| Singapore | 103.85°E | 1.35°N |
| Suez | 32.55°E | 29.97°N |
| Rotterdam | 4.48°E | 51.92°N |

These were converted to map coordinates using an **equirectangular projection** (`x = (lon+180)/360`, `y = (90-lat)/180`), so the route between them is geographically accurate even though the continent shapes themselves are simplified for a clean, stylized look rather than survey-accurate coastlines.

A small ship marker continuously travels the route (SVG `<animateMotion>`), port markers pulse to signal "live" tracking, and the rest of the scene (alert card, stats, CTA) cycles in on a loop — all in plain CSS, so it plays instantly with no build step or dependencies.

## Built with HyperFrames

This concept's real, renderable video source was authored for **[HyperFrames](https://github.com/heygen-com/hyperframes)** — an open-source framework by HeyGen that turns plain HTML/CSS into deterministic MP4 video, rendered via headless Chrome + FFmpeg. It's designed so both humans and AI coding agents can write videos as code instead of using a timeline editor.

- HyperFrames repo: <https://github.com/heygen-com/hyperframes>
- License: Apache 2.0
- Relevant workflow: `/faceless-explainer` (data/concept-driven explainer, no product URL or footage needed) combined with the `data-chart` / map catalog blocks

**Why this page isn't the HyperFrames file itself:** a real HyperFrames composition only animates when scrubbed frame-by-frame by the HyperFrames CLI (`npx hyperframes preview` / `render`) — opening it in a plain browser shows nothing. This repo's HTML/CSS page is a lightweight, browser-native **simulation** of that same composition's structure and timing, built so the concept can be viewed instantly by anyone (recruiters included) without installing anything. The actual `.mp4` deliverable would come from running the equivalent composition through the HyperFrames CLI.

## Files

| File | Purpose |
|---|---|
| `index.html` | Page structure and content. |
| `style.css` | All visual styling, the dot-matrix map generation output, and the CSS `@keyframes` animations driving the loop. |

Split for readability — `index.html` stays focused on content/structure, `style.css` holds all presentation and animation logic. The HTML links to the stylesheet with a plain relative path (`<link rel="stylesheet" href="style.css">`), so **both files must sit in the same folder**.

## Viewing locally

Open `index.html` directly in any browser — double-click it, or drag it into a browser tab. No build step, server, or install required.

