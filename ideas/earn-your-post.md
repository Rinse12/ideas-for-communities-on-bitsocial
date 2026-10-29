# Earn Your Post

> Reply first, post later. Your first ten approved replies unlock top-level posts.

**Kind:** gated
**Effort:** S
**Needs:** nothing

## How it works

1. Anyone can reply to existing posts, subject to the community's normal challenge.
2. A top-level post is accepted only if the author already has N approved replies in this community (10 by default), and fewer than M removed ones.
3. Until then the challenge explains the rule and shows your count: "7 of 10 replies, 2 more to go."
4. Authors over the threshold get a flair. The count is from the community node's own database, so nothing external is needed.

## The unique part

Karma gating without karma. The community node already knows every reply it published and every one a mod removed, per address, so the check is a database query inside the challenge. No votes to game, no cross-platform reputation, and the threshold is per community, so a cooking community and a security community can set different bars.

It also makes drive-by posting expensive in the one currency that matters here: time spent in the community before talking to it.

## Seed bot

Any poster bot keeps the front page alive while early members are still earning their first post.

## Builds on

- The community node's database (published and removed comments per author)
- Optionally the voucher challenge as a bypass: a vouched newcomer skips the count

## Open questions

- Ten one-word replies pass the count. Add a minimum length, or count only replies that got a reply themselves.
- Members who were posting before the rule turned on should be grandfathered in by the bot.
- Whether removed replies subtract or just block: a member with 10 approved and 3 removed should probably wait.
