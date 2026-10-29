# Ideas for communities on Bitsocial

Communities anyone can start on [Bitsocial](https://bitsocial.net), each with something a Reddit or Discord community can't do. Most are written with [Seedit](https://bitsocial.net/apps) in mind, but a community is just a key-owned node on the network, so any client can show it.

Want to run one? Open an issue saying which one you're taking, or just start it and send a PR with the address. New ideas are welcome too: copy [TEMPLATE.md](TEMPLATE.md).

## What you can build with

- **Custom challenges.** Every community decides what a post must pass before it's accepted, and you can write your own challenge with any logic. The challenge exchange is **private between the user and the community node**, so a challenge can collect a secret answer (a guess, a vote, a solution) that never appears publicly. Several games below rely on that.
- **Bots.** A poster bot keeps a new community from starting empty, and a moderation bot can check each post in the mod queue. [onlycats-poster](../onlycats-poster) is a full example: it posts a licensed cat photo every few hours, and an image classifier approves only cats.
- **Custom page sorts.** A community can rank its posts with its own `score` function ([active-page-sort](../active-page-sort) is an example).
- **Media by link.** The protocol carries text, and media goes in as links (catbox, imgur and the like accept uploads from scripts).
- **Ownership.** A community is a key, and its `.bso` / `.eth` name can be transferred on chain.

## The ideas

### Games

| Idea | The twist | Effort |
| --- | --- | --- |
| [Where Is This?](ideas/where-is-this.md) | Daily photo, secret coordinate guesses through the challenge, distance scoring | M |
| [Name That Species](ideas/name-that-species.md) | iNaturalist photo, secret guesses, partial credit by genus/family | S–M |
| [One Word Story](ideas/one-word-story.md) | Challenge accepts exactly one word, replying to the current end of the story | S |
| [Sealed Predictions](ideas/sealed-predictions.md) | Private probability forecasts, scored when the question resolves | M |

### Better conversations

| Idea | The twist | Effort |
| --- | --- | --- |
| [Proof of Reading](ideas/proof-of-reading.md) | Answer a question about the article before you can comment on it | M |
| [Steelman First](ideas/steelman-first.md) | Restate the comment you're replying to, accurately, before you argue | M |
| [ELI5, Enforced](ideas/eli5-enforced.md) | Answers above a reading-grade level are rejected | S |

### Gated and media

| Idea | The twist | Effort |
| --- | --- | --- |
| [Devs Only](ideas/devs-only.md) | Prove a real GitHub account by signing with its SSH key | M |
| [Daily Sky](ideas/daily-sky.md) | One photo of today's sky, checked for date and sky, compiled into a world map | M |
| [Human Art Only](ideas/human-art-only.md) | AI-generated images rejected, process shots earn flair | M |

### Governance experiments

| Idea | The twist | Effort |
| --- | --- | --- |
| [Constitution](ideas/constitution.md) | Rules changed only by verified vote, enforced by AI, watched by an outside bot | L |
| [Rotating Mod](ideas/rotating-mod.md) | A random active member is the mod for a day | S |
| [Community Auction](ideas/community-auction.md) | The community's `.bso` / `.eth` name goes to the highest bidder each year | L |
| [AI-Run Community](ideas/ai-run-community.md) | An LLM writes the rules, moderates and hears appeals | M |
| [AI Debate](ideas/ai-debate.md) | Pick two models and a topic; they argue in the thread | exists |

### Uncensorable

| Idea | The twist | Effort |
| --- | --- | --- |
| [Ephemeral Confessions](ideas/ephemeral-confessions.md) | Anonymous posts, removed after 24 hours | S |
| [Removed From Reddit](ideas/removed-from-reddit.md) | Live subreddit mirror where what Reddit removed is the front page | S (on top of the mirror) |

## Projects

Bigger tools that several communities can use:

- [pkc_community_mirroring_subreddit](../pkc_community_mirroring_subreddit): mirrors subreddits onto communities, keeps removed content and records who removed it and when.
