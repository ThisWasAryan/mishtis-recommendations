# Mishti's Recommendations

Mishti's Recommendations is a single-page, map-based web app for sharing curated place recommendations with quick at-a-glance details.

## What it does

- Displays recommendation markers on an interactive Leaflet map.
- Shows a sidebar with ratings, review notes, pros, cons, and a Google Maps link.
- Supports light and dark themes.
- Lets you drop up to two custom measurement pins on the map and calculates the distance between them.
- Includes a clear action to remove custom pins and reset distance output.

## Tech stack

- HTML, CSS, and vanilla JavaScript
- [Leaflet](https://leafletjs.com/) for map rendering
- OpenStreetMap map tiles (via Leaflet defaults)

## Run locally

Because the app is a static site, you can run it with any local web server.

### Option 1: Python

```bash
python3 -m http.server 8000
```

Then open:

- `http://localhost:8000`

### Option 2: VS Code Live Server

- Open the repository in VS Code.
- Start the **Live Server** extension from `index.html`.

## Project structure

- `index.html` — complete application UI, styles, and client-side logic.
- `README.md` — project documentation.

## Notes

- No backend or database is required.
- Recommendation data is currently defined directly in `index.html`.

## Future improvements

- Move recommendation data into a separate JSON file.
- Add basic automated browser smoke tests for interactions.
- Add search and filter capabilities for faster discovery.
