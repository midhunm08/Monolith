# Monolith v2.5 — personal dashboard (online version)

Upload this folder to GitHub Pages (or any static host) and open `index.html`.
It also works offline once loaded. Free, no paid services.

## What's new in v2.5

- **Quick Notes Advanced editor, FIXED** — formatting (bold, italic, font,
  size, bullets) silently did nothing before: tapping a toolbar button
  blurred the editor and killed the selection first. The toolbar now keeps
  the selection, saves/restores it, and formats with the browser's own
  command. Advanced is now only what was asked for: font, bold, italic,
  font size, bullets. Also fixed: reopening a saved rich note used to strip
  all its formatting — it keeps it now. Simple mode is unchanged.
- **Second Brain rebuilt touch-first** — the old map hid everything behind a
  fragile long-press and a hover-only connect handle, and an accidental
  double-tap could dim the whole map to 14% with no way out (that is what
  your screenshot showed). Now: tap a note and a visible action bar appears
  above the canvas with Edit, Add child, Add sibling, Add main branch,
  Connect, Colour, Collapse, Focus, Delete. The toolbar sits above the
  canvas in normal page flow (no more invisible overlay). Double-tap a note
  edits it (never focuses it); double-tap empty space adds a note; drag a
  note onto another note to move it there, with a visible highlight.
  Connect = tap Connect, then tap two notes. Focus never persists across
  reloads, tapping empty space unfocuses, faded notes stay readable, and
  every node has a solid background in light mode too. Your existing map
  (all 7 notes from the screenshot, including the empty ones) loads with
  everything visible and editable.
- **Unlimited wallpapers** — 30 photos are gone as a limit. Every day the
  app fetches a new photo from Openverse (free, no key, millions of CC
  photos), cached once a day; Shuffle fetches a different one. If Openverse
  fails or you're offline, the curated Unsplash list is the fallback and
  the info sheet says which source the photo is from, with the
  photographer's name.

Everything from v2.0–v2.4 is still here: theme/wallpaper overhaul, weather
with visible errors + Retry, habit weekday maths with counts, market with
five fallback sources, journal 10×10 mood grid, world clock, folder todos,
habits, reminders, plans, news (latest headlines, refresh on open), money
with categories + charts + export, journal Year→Month folders + diary
export, focus/sleep/water trackers, quick notes, Second Brain radial mind
map, weekly review PDF, tab order in Settings, single-device login,
Supabase sync.

## Setup

1. Upload the whole folder to your GitHub repository (e.g. `monolith/`) and
   enable GitHub Pages, or open `index.html` directly.
2. Create an account inside the app (username + password, min 8 characters).
   Your data syncs to your Supabase project; it also works offline.
3. **Single-device login (optional, once):** in Supabase → SQL Editor, run
   `monolith-single-device.sql` from this folder. Until then, sign-in works
   as before. If you already ran it for v2.2/v2.3/v2.4, do not run it again.

## Files

- `index.html` — the app (open this)
- `monolith-v2.5.html` — identical copy of the app
- `monolith-single-device.sql` — one-time Supabase setup for single-device login
- `README.md` — this file

## Notes

- Weather: Open-Meteo (free, no key). Wallpaper: Openverse daily (free, no
  key) + Unsplash fallback + your own uploaded photo. News: Google News via
  rss2json. Market: Yahoo Finance (delayed) via proxies + Stooq.
- Your uploaded wallpaper is local-only: it is not synced to Supabase and
  does not travel to another device; that device falls back to Openverse.
- Previous build (v2.4) is kept as a fallback in `monolith-online-v2.4/`.
