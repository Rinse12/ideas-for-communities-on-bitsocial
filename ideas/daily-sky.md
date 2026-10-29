# Daily Sky

> One photo of your sky, today. Every day the bot puts them all on a world map.

**Kind:** media
**Effort:** M
**Needs:** small vision model or LLM

## How it works

1. Post a photo link of the sky where you are, with your city or region in the title.
2. The challenge checks the photo was taken today and that it shows the sky.
3. At midnight UTC the bot posts "Today's sky from 41 places": a world map with every photo pinned, uploaded as an image.

## The unique part

A custom challenge (or a mod-queue bot like [image-classifier-bitsocial-moderator-bot](../../image-classifier-bitsocial-moderator-bot)) that:

- reads EXIF `DateTimeOriginal` when the host keeps it (catbox does, imgur strips it), and otherwise asks for a timestamp
- has a vision model confirm it's an outdoor sky photo, not a screenshot or an old wallpaper
- runs a perceptual-hash check so the same photo can't be posted twice

The compiled map is the community's real product: a daily snapshot of the planet's weather, made by people.

## Seed bot

Public-domain webcam stills or NASA/NOAA imagery for days with few posts, clearly labelled as bot posts.

## Builds on

- Image classifier bot pattern
- A static map renderer (e.g. a tile map plus markers, rendered to PNG)

## Open questions

- "Today" can't be proven without EXIF. Accept that it's honour-based with a vision check on top.
- Location privacy: geocode the city name, never use exact EXIF GPS on the map.
