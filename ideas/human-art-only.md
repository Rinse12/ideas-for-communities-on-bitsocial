# Human Art Only

> An art community where AI-generated images don't get in.

**Kind:** media
**Effort:** M
**Needs:** AI-image detector (open model or paid API)

## How it works

1. Post your art as an image link.
2. A moderation bot runs an AI-generated-image detector on it. Clear human work is approved, clear AI is rejected, and anything in between goes to the mod queue.
3. Add a second link with work-in-progress shots (sketch, layers, timelapse) and you get a `process shown` flair.

## The unique part

The [image classifier bot](https://github.com/bitsocialnet/image-classifier-bitsocial-moderator-bot) turned around: instead of "only cats", it's "only humans". Process flair gives honest artists a way to prove it, and over time builds a reputation that detectors can't.

## Seed bot

Public-domain art from museum open-access APIs (the Met, Art Institute of Chicago, Rijksmuseum), posted as "From the archive". Human art by definition, with the artist and museum credited.

## Builds on

- [image-classifier-bitsocial-moderator-bot](https://github.com/bitsocialnet/image-classifier-bitsocial-moderator-bot)
- An open AI-image detector model, or a commercial one (e.g. Hive)

## Open questions

- Detectors have false positives. The mod queue and an appeal flow (reply with your process) are essential.
- Where's the line on digital tools, and on AI-assisted editing? Each community writes its own rule.
