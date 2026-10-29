# Assigned Sides

> A debate club where you don't choose your side. The challenge assigns it, and checks that you argued it.

**Kind:** conversation
**Effort:** M
**Needs:** LLM

## How it works

1. The bot posts a motion: "This house would abolish daylight saving time."
2. You reply. The challenge tells you privately which side you're on for this motion, drawn from your address and a secret the node holds, so it's random but fixed: you get the same side every time you come back to that thread.
3. An LLM reads your reply and checks it argues your side. If it doesn't, the challenge tells you which side you have and you rewrite.
4. The bot flairs each published reply `for` or `against`, so readers see who's arguing what. After a week the thread closes and the bot posts which side people found more convincing, from a private vote.

## The unique part

You can't pick the easy side, and you can't pick the side you believe. Half the time you're writing the best case for something you disagree with, in public, which is the whole exercise. The assignment is private so nobody can shop for a thread where they got lucky, and it's deterministic so you can't retry until you get the side you wanted.

The LLM check is the same shape as [Steelman First](steelman-first.md): one Haiku-class call per reply with the motion, the side and the text.

## Seed bot

Motions from a curated list, one a day. Policy questions with real arguments on both sides (speed limits, zoning, school uniforms, tabs vs spaces), not questions about anyone's rights or dignity. The LLM can draft motions and a human approves the list.

## Builds on

- AI moderation challenge, with a per-thread prompt
- Private vote collection from [Sealed Predictions](sealed-predictions.md) for the "more convincing" poll

## Open questions

- Some people will refuse to argue a given side. An opt-out per motion ("skip this one") is fine; they just can't post in that thread.
- Replies to other people's replies: same side as your assignment for the motion, so cross-examination stays in character.
- Scoring debaters over time: votes on persuasiveness, split by whether the voter agreed beforehand.
