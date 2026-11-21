# Blindwalk
See businesses around you with the help of GPS.

`index.html` is a one-file prototype for Safari on iPhone.

- **Stroll mode (step one):** tap Start and walk. Each shop is announced once as you pass it, for example "Bakery, on your left." The screen stays awake while stroll mode is on, where Safari allows it (iOS 16.4 or later, not in Low Power Mode).
- **Ask about a place (step two):** type or speak a question such as "Is that bakery open?" The app looks up the shops you just passed in Google Places (hours, rating, reviews) and Claude answers in one spoken sentence.

## Setup

1. Host the file over HTTPS. Safari only allows location on secure pages. This repo is set up for GitHub Pages: Settings, Pages, deploy from this branch, root folder.
2. Open the page on your iPhone and open **Settings: API keys**.
3. Enter your Google Maps key (Places API (New) enabled) and your Claude key, then tap **Save keys**.

The keys are saved only in Safari on that phone. They are never in the code, so the public repo and the public page contain no keys. If you clear Safari's website data, you will need to enter them again.

## Cost and safety

- Each question makes up to 3 Google Place Details calls that include reviews. That is a pricier Google tier than the nearby search, so check Google's pricing page.
- Each question also makes one Claude call.
- In Google Cloud, restrict the Google key to your Pages address (`https://waywellnanna-hue.github.io/*`).
- Set a monthly spend limit in the Claude Console.
- Anyone else who opens the page can use it only with their own keys. Before giving this to other people, the Claude call should still move behind a small server, so they do not need a Claude key.

## Third-party code

The Claude SDK (`@anthropic-ai/sdk` 1.4.0) is copied into `vendor/` instead of loaded from a CDN, so the page only runs code from this repo. Licenses for it and its bundled dependencies are in `vendor/THIRD_PARTY_LICENSES.txt`.
