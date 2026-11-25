# Spike Strip Map

A single-page map for phones. It shows spike strip locations, sorts them by distance from you, and opens turn-by-turn directions in Apple Maps or Google Maps.

## Run it
It is a static site: `index.html` plus `data/locations.json`. You can host it anywhere, for example with GitHub Pages (Settings → Pages → deploy from this branch). Geolocation only works over HTTPS.

## Data
The app reads `data/locations.json`. It also accepts CSV and GeoJSON. Each row needs coordinates. The app recognises these column names:

| field | accepted column names |
|---|---|
| latitude  | `lat`, `latitude`, `y` |
| longitude | `lng`, `lon`, `long`, `longitude`, `x` |
| name      | `name`, `title`, `label`, `location`, `site`, `id` |
| status (colours the pin) | `status`: available/ready = green, deployed/in use = orange, maintenance/damaged/missing = red |

Every other column shows up in the pin's popup and can be searched.

Ways to load data:
- **Replace** `data/locations.json` (it currently holds 3 SAMPLE rows).
- **On the phone**, tap ⇪ and pick a CSV or JSON file. The data stays on that device until you open `?reset`.
- **From a URL**: `index.html?data=https://…/file.csv` (the server must allow CORS).

## Use
- ◎ centers the map on you. The list shows the nearest locations first.
- Tap a row to zoom to that pin. Tap **Go** to navigate.
- Search filters across all fields.
