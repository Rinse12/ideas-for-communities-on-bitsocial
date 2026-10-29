# Nonce in Frame

> The challenge gives you a code. Write it on paper, put it in the photo. The photo is fresh and yours, or it doesn't post.

**Kind:** gated · media
**Effort:** M
**Needs:** a vision model (local OCR plus a small VLM, or a hosted one)

## How it works

1. You start a post. The challenge answers with a short code, say `KW7-42`, and a time limit of ten minutes. Nothing is published yet.
2. You write the code on paper (or a whiteboard, or your hand), take the photo with the code in frame, upload it to an image host, and submit the link as your answer.
3. The challenge fetches the image, finds the code with a vision model, checks it matches and that the photo isn't an existing image with text pasted on (the model is asked whether the code is handwritten and physically in the scene). Pass, and the post goes up with a `verified fresh` flair.
4. Without a code, the post can still go up, unflaired, or be rejected, as the community prefers.

## The unique part

This is proof that a photo was taken **after the challenge was issued, by the person posting**. No stock photo, no reverse-image-search find, no AI render, no repost of someone else's work. It needs no EXIF, no account, no hardware attestation. It only works because the challenge exchange is private: the code is known to the node and to you, so a photo containing it could not have existed before.

It's a reusable primitive rather than one community. Communities that want it:

- **Show Your Desk** / **Battlestations**: the setup in the photo is really yours.
- **Today's Meal**, **Garden Progress**, **Gym Check-in**: streak flair that can't be faked.
- **Sold As Seen**: a marketplace board where the item photo is provably current.
- **Human Art Only** ([existing idea](human-art-only.md)): a process shot with the code next to the work in progress is stronger evidence than any AI detector.
- **Where Is This?** submissions: a member-submitted location photo that is actually new.

## Seed bot

Not for the verified stream, by definition. A bot can post the weekly theme ("this week: your view from the window") and the leaderboard of streaks.

## Builds on

- The one-code-per-author, time-limited storage shape from [Where Is This?](where-is-this.md), issued by the node instead of collected
- image-classifier-bitsocial-moderator-bot for fetching and classifying linked images
- A VLM that can read handwriting in a scene (any current small multimodal model does this well)

## Open questions

- Editing the code into a photo is the obvious attack. The model is asked about physical plausibility (lighting, shadow, perspective of the paper), which stops casual edits. A determined forger with ten minutes and an image editor can get through, which is the same bar as every other proof-of-photo scheme without hardware.
- Ten minutes is long enough to photograph, short enough that generating and compositing an image is a hassle. Tune per community.
- Accessibility: some people can't write or hold paper. Accept the code typed on a screen in frame as a weaker tier.
- Image hosts strip nothing the check needs, since nothing depends on metadata.
