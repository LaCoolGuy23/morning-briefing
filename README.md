# Morning Briefing — News & Kathmandu Weather

A responsive, installable Progressive Web App (PWA) for your chosen news topics and Kathmandu forecast.

## Features
- Topic filters: Technology & AI, Business & economy, Nepal politics & society, Personal finance, Insurance.
- Google News RSS search results via RSS2JSON proxy, linking to original publishers.
- Kathmandu weather and five-day forecast from Open-Meteo.
- Save topic preferences and bookmarked headlines in the browser on this device.
- Installable on supported mobile/desktop browsers when served over HTTPS.

## Run locally
Because the app fetches external feeds, serve it over HTTP rather than opening the file directly. With Python installed:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 in the browser from this folder.

## Publish it free with GitHub Pages
1. Create a GitHub repository named `morning-briefing`.
2. Upload `index.html`, `manifest.webmanifest`, `sw.js`, and `icon.svg` to the repository root.
3. In the repository, open **Settings → Pages**.
4. Under build and deployment, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish; your app will have a public HTTPS URL. Open it on your phone and use the browser menu → **Add to Home screen** or **Install app**.

## Data and limitations
- Weather: Open-Meteo forecast API, coordinates for Kathmandu (27.7172, 85.3240). Weather alerts are heuristic based on precipitation probability/current weather code, not an official emergency-warning feed.
- News: Google News RSS query feeds are accessed through the public RSS2JSON endpoint. Availability/rate limits can change; this prototype does not guarantee complete coverage or editorial verification. Always open and assess the original publisher.
- Topic preferences and saved headlines are stored in the browser's local storage and do not sync between devices.
- This is a static web app; it does not send scheduled push notifications or email briefings. Those require additional infrastructure/services.
