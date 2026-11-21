# Blindwalk
See businesses around you with the help of GPS.

`index.html` is a one-file prototype for Safari on iPhone.

- **Stroll mode (step one):** tap Start and walk. Each shop is announced once as you pass it, for example "Bakery, on your left." The screen stays awake while stroll mode is on, where Safari allows it (iOS 16.4 or later, not in Low Power Mode).
- **Ask about a place (step two):** type or speak a question such as "Is that bakery open?" The app looks up the shops you just passed in Google Places (hours, rating, reviews) and Claude answers in one spoken sentence.

## Setup

1. Put your Google Maps key (Places API (New) enabled) in `API_KEY`.
2. Put your Claude API key in `ANTHROPIC_API_KEY`.
3. Host the file over HTTPS (GitHub Pages or Netlify). Safari only allows location on secure pages.

## Cost and safety

- Each question makes up to 3 Google Place Details calls that include reviews. That is a pricier Google tier than the nearby search, so check Google's pricing page.
- Each question also makes one Claude call.
- **Both keys sit in the page.** Anyone who opens the page can copy them. The Google key can be locked to your site's address; the Claude key cannot. Keep the link private, set a monthly spend limit in the Claude Console, and move the Claude call behind a small server before sharing this with anyone.
