# Where Is This?

> A photo from somewhere on Earth every day. Guess where it is, privately, and get scored on how close you were.

**Kind:** game
**Effort:** M
**Needs:** no keys (Wikimedia Commons, Nominatim)

## How it works

1. Every day the bot posts a geotagged photo with no caption.
2. You reply to it. The community's custom challenge asks for your guess (`48.85, 2.35` or a place name). The reply itself can say anything: "no idea, looks Nordic".
3. After 24 hours the bot replies with the answer, a map, and everyone's distance and points. A weekly post shows the leaderboard, and the week's winner gets flair.

## The unique part

**The guess travels in the challenge exchange, not the reply.** The challenge is private between you and the community node, so nobody can see earlier guesses and copy them. That is something no ordinary forum can do: on Reddit, the first right answer spoils the round for everyone else.

The custom challenge geocodes place names with Nominatim, stores one guess per author per round, and scores by great-circle distance (5,000 points at 0 km, falling off with distance, GeoGuessr-style).

## Seed bot

Fully bot-run: geotagged photos from Wikimedia Commons (e.g. `Category:Quality images` with coordinates, or street-level photos from Mapillary, CC BY-SA). The bot crops out obvious giveaways (signs, captions) with a quick LLM check and credits the photographer in the reveal.

## Builds on

- [onlycats-poster](../../onlycats-poster) for the Commons pool, scheduling and crediting
- Nominatim for geocoding

## Open questions

- Reverse image search finds Commons photos. Mapillary street-level images or lesser-known categories make that harder. Or accept it: cheaters only cheat themselves on a points board.
- Difficulty tiers: one easy (famous place) and one hard round a day?
