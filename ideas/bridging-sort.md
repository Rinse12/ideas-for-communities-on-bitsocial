# Bridging Sort

> The front page ranks what people who usually disagree both upvoted. Built for science communities, where the loudest camp shouldn't own the thread.

**Kind:** conversation
**Effort:** M–L
**Needs:** nothing (a custom page sort over the node's own vote data)

## How it works

1. The community looks and posts like any other. The difference is the default sort.
2. The node keeps every vote with its author address (it already does). From that it computes, per author, a position on the community's main axis of disagreement, using the same matrix-factorisation idea as Community Notes: voters who tend to upvote the same things cluster together.
3. A comment's score is not its net votes but its **bridging score**: how much it is upvoted *after* removing what's explained by each voter's camp. A comment upvoted mainly by one cluster scores low even with a thousand votes. A comment upvoted across clusters scores high even with thirty.
4. The sort exposes the number next to each comment, and a small badge: `bridging`, or `one-sided` for the high-vote, low-bridge ones.

## The unique part

On Reddit, a science subreddit with a live controversy (nutrition, nuclear power, a contested paper) turns into two voting blocs, and whichever bloc is bigger decides what's visible. Mods compensate with heavy removal. A **bridging page sort** changes the incentive instead: the way to reach the top is to write something the other side can also upvote, which in a science community means the careful comment that cites the limitation, not the dunk.

This needs no challenge and no LLM. It is a `score` function with access to the vote table, which is exactly what a community node has and a Reddit moderator never gets. The community can also publish the per-cluster breakdown of a thread ("this comment: 90% cluster 1, 4% cluster 2") as a bot reply, which is a stronger "controversial" flag than vote ratio.

## Seed bot

Link posts from arXiv, PubMed or journal RSS feeds, as in a [Proof of Reading](proof-of-reading.md) science variant. The sort only matters once there are votes, so pair it with a community that already argues.

## Builds on

- [active-page-sort](https://github.com/pkcprotocol/active-page-sort) for the custom `score` function shape
- The [Community Notes algorithm](https://github.com/twitter/communitynotes) (open source, well documented)
- The community node's vote table

## Open questions

- Cold start: with few voters the factorisation is noise. Fall back to net votes until a thread has N distinct voters, and say so in the sort name.
- One axis is usually enough for a single controversy, but a general science community has several. Compute per-post or per-flair, or use two factors.
- Sybil voting: one person with many addresses can fake a second cluster. Mintpass or [Invite Tree](invite-tree.md) membership as a vote-eligibility gate limits that.
- Publishing per-author cluster positions would be a privacy problem. Publish only aggregate per-comment numbers.
