# Removed From Reddit

> A live mirror of a heavily moderated subreddit, where everything Reddit removes is the front page.

**Kind:** uncensorable
**Effort:** S once [pkc_community_mirroring_subreddit](../../pkc_community_mirroring_subreddit) exists
**Needs:** a Redlib instance or Reddit's `.json` endpoints

## How it works

1. The mirror copies every post and reply from one subreddit as it happens.
2. When Reddit removes a post **or a reply**, the copy stays up with a flair (`Removed by mods on Reddit`, `Removed by Reddit admins`, …) and a note saying when, e.g. "removed between 14:00 and 14:10 UTC, 3 h after posting".
3. Removed posts sort first. Every thread also keeps a running count: "14 of 230 comments removed on Reddit so far".
4. Bitsocial users reply natively next to the mirrored comments. When the Reddit thread is locked, the conversation can continue here.

## The unique part

- A **custom page sort** (`removed-first`) built on pkc-js configurable page sorts, so Seedit shows removed content at the top without any UI change. A `reddit-hot` sort ranks everything else by its Reddit score.
- Moderation becomes **visible**: what gets removed, how fast, and by whom.
- The mirror bot has its own flair, so mirrored posts are easy to tell apart from native ones.

## Which subreddit?

Any heavily moderated subreddit with a lot of controversy. One community per subreddit. The same tool can also bring back **subreddits Reddit already banned**, from archives.

## Builds on

- [pkc_community_mirroring_subreddit](../../pkc_community_mirroring_subreddit), which does all the work
- A custom page sort (see [active-page-sort](../../active-page-sort) for the pattern)
