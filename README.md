# TravelFlow AI

A live travel-discovery map and drag-and-drop day-itinerary builder. Search a
destination (or use your GPS), pick the categories you care about, and build a
single ordered itinerary that stays in sync between the list and the map.

## Features

- **Live POI discovery** — pulls nearby places from OpenStreetMap (Overpass),
  with Wikipedia + Nominatim fallbacks, classified into categories (food,
  museums, beaches, viewpoints, tours, parks, etc.).
- **Category buckets in selection order** — the order you pick categories sets
  the order of the buckets in your itinerary.
- **One global itinerary** — a single continuous numbering (#1 → #2 → #3 …)
  across all categories. The numbers are your real travel flow, never reset per
  bucket.
- **Drag-and-drop** — reorder places within or across buckets; the list and the
  numbered map pins update instantly.
- **Interactive map** — numbered pins with name labels, a connecting route line,
  and two-way highlight (click a list item to highlight its pin, click a pin to
  highlight and scroll to its list item).
- **Time schedule** — a time-aware view with start times, durations, and travel
  legs between stops.
- **Save trips** (optional) — sign-in and per-user trip storage via Supabase.

## Running it

This is a single, self-contained HTML file — no build step, no install.

- **Easiest:** double-click `index.html` to open it in your browser.
- It loads React, Leaflet, Babel, and the Supabase client from CDNs, so an
  internet connection is required.

## Optional: enable saving trips (Supabase)

Trip saving and sign-in are off until you add Supabase credentials.

1. Create a project at https://supabase.com → **Settings → API**.
2. In `index.html`, find the config block near the top and set:
   - `SUPABASE_URL` → your **Project URL**
   - `SUPABASE_ANON` → your **anon public** key
3. Run the SQL shown in the comment block at the top of `index.html` once in the
   Supabase SQL editor to create the `trips` table and row-level-security policy.

Affiliate links (Booking.com, GetYourGuide) are also placeholders — see
`BOOKING_AFFILIATE_ID` / `GYG_AFFILIATE_ID` in `index.html`.

## Tech

Single-file React (via Babel standalone) · Leaflet + CartoDB tiles ·
OpenStreetMap data · Supabase (optional).

## Data & credits

Place data © OpenStreetMap contributors. Distances are straight-line estimates.
