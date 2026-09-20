# france-luxury-treks

A private page for our twentieth anniversary — Chamonix, September 2027.

Published at <https://jvichhi.github.io/france-luxury-treks/> (login required).

## What's on the page

- **How it's going** — the trip we chose. Chamonix Basecamp: seven nights at
  the Résidence Le Cristal de Jade, six self-guided day hikes straight from the
  door, no guide, no packing in the mornings. The day-by-day itinerary runs
  Day 0 → Day 8, with the practical bits (flights, restaurants, what to see)
  below it.
- **How it started** *(collapsible)* — the eight other French itineraries we
  priced and vetted before deciding, plus the two side-by-side comparison
  tables and the trip checklist. Collapsed by default.

## Notes for whoever edits this next

- Everything is a single self-contained `index.html` — no build step, no
  dependencies. Open it directly or serve it with any static server.
- Prices render in **C$** via the FX widget at the top. Each price carries
  `data-cur` (original currency) and `data-v` (original amount) attributes; the
  script converts them live from rates stored in `localStorage`, so adding a
  price is just a new `<span class="px" data-cur="EUR" data-v="45–60">`. Use a
  literal en dash in `data-v` for ranges — the parser splits on it.
- The collapsible archive's nav pills open their own `<details>` before jumping,
  so in-page links aren't dead while it's closed.

## Route maps

Any hiking day can carry a click-to-open Leaflet map. Tracks live in `maps/` as
simplified polylines (`[[lat, lon], ...]`, 5 dp, Douglas-Peucker at about 8 m)
and are fetched only when a map is opened. Leaflet itself is loaded lazily on
the first open, so a reader who opens no map downloads nothing extra.

Source tracks are kept in `.research/gpx/` — re-run the converter if a route
changes. Provenance: **Asters / CEN 74** (Geotrek) for Passy, the **Contamines
tourist office via APIDAE** for the Contamines options, and **OpenStreetMap
relation 5329763** for the Grand Balcon Nord. Tiles are OpenStreetMap, whose
licence requires the credit that renders in the map corner — leave it visible.

## Caveats

Prices are do-it-yourself estimates (flights, hotels, transfers, lift tickets)
and move with season, fuel surcharges and demand — re-verify before booking.
Guided tours appear only as clearly-labelled comparison benchmarks. Three
regions (Alsace, Dordogne, Brittany) are marked as partially vetted.
