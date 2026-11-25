# Spike Strip Map

A single-page map for phones. It shows the Phoenix Valley tire spike locations (one-way exit spikes at lots and trailheads), sorts them by distance from you, and opens turn-by-turn directions in Apple Maps or Google Maps.

## Run it
It is a static site: `index.html` plus `data/locations.json`. You can host it anywhere, for example with GitHub Pages (Settings → Pages → deploy from this branch). Geolocation only works over HTTPS.

## Data
The app reads `data/locations.json`. It also accepts CSV and GeoJSON. Each row needs coordinates. The app recognises these column names:

| field | accepted column names |
|---|---|
| latitude  | `lat`, `latitude`, `y` |
| longitude | `lng`, `lon`, `long`, `longitude`, `x` |
| name      | `name`, `title`, `label`, `location`, `site`, `id` |
| status (colours the pin) | `status`: Confirmed = green, Mapped in OSM = blue, To verify = yellow, No spikes = grey |

Every other column shows up in the pin's popup and can be searched.

Ways to load data:
- **Replace** `data/locations.json`. It holds the 17 rows of the "Phoenix Valley Tire Spike Locations" sheet as of 2026-11-25; re-export it when the sheet changes.
- For "To verify" rows the coordinates are the place itself (peak, dam, building), not the spike, which would be at the lot entrance or exit.
- **On the phone**, tap ⇪ and pick a CSV or JSON file. The data stays on that device until you open `?reset`.
- **From a URL**: `index.html?data=https://…/file.csv` (the server must allow CORS).

## Use
- ◎ centers the map on you. The list shows the nearest locations first.
- Tap a row to zoom to that pin. Tap **Go** to navigate.
- Search filters across all fields.
