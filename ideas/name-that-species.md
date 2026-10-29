# Name That Species

> A photo of a living thing. Name it. Partial credit if you get the genus right.

**Kind:** game
**Effort:** S–M
**Needs:** no keys (iNaturalist API)

## How it works

1. A few times a day the bot posts a research-grade iNaturalist observation: the photo, the continent, nothing else.
2. You reply, and the challenge asks for your guess privately: a common or scientific name.
3. At reveal the bot posts the answer, the observer's credit and a link to the observation, plus everyone's score.

## The unique part

A custom challenge that resolves your guess to an iNaturalist taxon (through its autocomplete API) and scores by **how close in the tree of life** you were: species 10, genus 5, family 3, order 1. "Some kind of heron" gets something, "Grey Heron" gets everything.

Like [Where Is This?](where-is-this.md), the guess is private, so the first expert to reply doesn't spoil the round.

## Seed bot

iNaturalist observations with CC0 / CC BY photos, filtered to research grade. Themed days work well: *Fungi Friday*, *Bug Monday*, a "your continent" round.

## Builds on

- iNaturalist API (observations, taxa)
- [onlycats-poster](../../onlycats-poster) for scheduling

## Open questions

- iNaturalist's own computer-vision model can answer for you. Fine: it's a learning community, and the leaderboard is for fun.
- Allow members to submit their own photos as rounds (they know the answer and are excluded from scoring)?
