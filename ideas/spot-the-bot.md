# Spot the Bot

> A human and an LLM answer the same questions side by side. Vote in secret which one is the machine, find out tomorrow.

**Kind:** game
**Effort:** M
**Needs:** LLM (one model per round, swappable)

## How it works

1. Each round is one post. A volunteer human and an LLM are the two contestants, shown only as **A** and **B** (assignment random per round).
2. Members reply with a question. The bot relays it to both contestants: the LLM by API, the human through the challenge (they open the thread and, when they post, the challenge shows them the pending questions and takes their answers privately). The bot then posts both answers under the question, as A and B.
3. Any time during the round, a member casts a secret vote through the challenge: "A is the bot" or "B is the bot". One vote per address, changeable until close.
4. After 24 hours the bot reveals, posts the vote split, and updates two leaderboards: **detectors** (how often you were right, Brier-scored if the vote includes a confidence) and **impostors** (humans ranked by how many voters they fooled).

## The unique part

The old Turing test as a daily game, and the private challenge does the two things a forum can't: it collects votes nobody can see (so no herding once someone confident says "obviously B"), and it relays the human's answers without the human needing an account or a DM channel. The human just posts in the thread like anyone else, and the challenge turns that post into a private answer sheet instead of publishing it.

Rotate models between rounds and tag the reveal with the model name. Over time the leaderboards double as an informal benchmark: which models are hardest to spot, and which questions catch them.

## Seed bot

Fully bot-run once a human volunteers; the bot runs the round, relays, reveals and scores. A standing "volunteer" post collects sign-ups (a reply "me" through the challenge, kept private so the list of recent volunteers doesn't give the game away). Bot-vs-bot rounds fill in when nobody volunteers, revealed as such.

## Builds on

- The private-vote pattern from [Sealed Predictions](sealed-predictions.md)
- [AI Moderation Challenge](https://bitsocial.net/apps) for the LLM plumbing
- The private relay is a small extension of the challenge: it returns data to the user (the pending questions) as well as collecting it

## Open questions

- Latency gives it away: the LLM answers in seconds, the human in hours. Batch both answers and post them together at fixed intervals.
- Style gives it away: prompt the LLM with the human's earlier answers, or let the human see the model's answer first and vice versa. Both make it harder and more interesting.
- The volunteer's address posts in the thread, so a careful observer could notice which address never asks questions. Have volunteers use a fresh address, or have the challenge accept the answers through any community the bot also runs.
