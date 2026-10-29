# Time Capsule

> Write something today that nobody can read until the date you choose, with public proof that you wrote it today.

**Kind:** feed
**Effort:** S–M
**Needs:** nothing

## How it works

1. You post with a title and a reveal date (`reveal: 2027-10-29`). The challenge asks for the capsule text privately.
2. The node encrypts the text with a fresh key, and the bot replies to your post with the ciphertext and a hash of the plaintext. The post itself shows only the title and the date.
3. On the reveal date the bot replies again with the key and the plaintext. Anyone can decrypt the ciphertext from step 2 and check the hash.
4. The front page is sorted by reveal date, so you can see what's opening this week.

## The unique part

A commitment scheme on a forum. The ciphertext and hash are in the public record from day one, timestamped by the post, so when the capsule opens nobody can say you wrote it after the fact. The text itself never crosses the public network until then, because it went through the private challenge.

Uses that come up on their own: letters to your future self, predictions you'd rather not defend for a year, "I called it" receipts for product launches, sealed answers to a riddle you post elsewhere.

## Seed bot

The bot opens one capsule from the public domain each week: letters and predictions from a hundred years ago (Project Gutenberg, Wikisource), posted with a reveal date so they show up in the same feed.

## Builds on

- The private-answer pattern from [Sealed Predictions](sealed-predictions.md); this is the free-text version with a chosen date
- A custom page sort by reveal date

## Open questions

- If the node is lost, unopened capsules' keys go with it. The node should back up keys somewhere the operator trusts, or let the author hold a copy of the key too (the challenge could show it once).
- Maximum length and maximum date (ten years?), and whether the author can open a capsule early.
- Someone could put something unpleasant in a capsule that opens long after anyone is watching. The reveal goes through the mod queue like any post.
