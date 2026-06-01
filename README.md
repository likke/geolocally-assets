# geolocally-assets

Public image host for GeoLocally social media campaigns.

Images here are referenced by URL from the [buffer-toolkit](https://github.com/likke/buffer-toolkit) (private) — Buffer's API requires publicly reachable media URLs, and this repo provides them via `raw.githubusercontent.com`.

## Cards

The `/social-cards/` directory holds the 6-card narrative series rendered from the toolkit's HTML template. Pattern:

```
https://raw.githubusercontent.com/likke/geolocally-assets/main/social-cards/<id>.png
```

| ID | Theme |
|---|---|
| 01-hook | Your customers stopped Googling |
| 02-problem | Site built for the old search |
| 03-why | Clarity in five seconds |
| 04-solution | Focused page. Short video. Live in 5 days |
| 05-offer | First cohort, flat fee |
| 06-cta | 48-hour yes or no |

## Regenerating

Cards are code-rendered, not hand-designed. To change copy or styling, edit `src/cards/cards.json` + `src/cards/template.html` in the buffer-toolkit repo, then:

```bash
node bin/buffer.js render-cards
cp assets/social-cards/*.png ../geolocally-assets/social-cards/
cd ../geolocally-assets && git add . && git commit -m "Regenerate cards" && git push
```
