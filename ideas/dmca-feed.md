# DMCA Feed

> Every takedown notice GitHub receives, posted as it lands: who sent it, which repositories went dark, and what they claimed.

**Kind:** feed · uncensorable
**Effort:** S
**Needs:** nothing (GitHub's public `dmca` repository)

## How it works

1. GitHub publishes every DMCA takedown and counter-notice it acts on as a markdown file in [github/dmca](https://github.com/github/dmca), redacted of personal details.
2. A bot watches that repository's commits. Each new notice becomes a post: title from the filename (date and sender), body with the claimed work, the list of affected repositories, and the sender's stated reason, plus a link to the notice file.
3. Flair by kind: `takedown`, `counter-notice`, `retraction`, `reinstated`. When a counter-notice or retraction references an earlier takedown, the bot replies in the original thread and updates its flair.
4. Members discuss under each notice: whether the claim is sound, whether the code is mirrored elsewhere, which forks survived.

## The unique part

GitHub's transparency repo is a dump of thousands of files with no discussion, no notifications and no way to follow a sender. As a community it becomes a **live feed with threads**: the youtube-dl and Nintendo waves would have been visible as they happened, each notice gets a place to talk about it, and the whole archive lives on a network where no notice can take it down. It is [Delisted](delisted.md) for code, and the two bots are nearly the same program pointed at different sources.

Useful sorts: by sender (a pinned post per frequent sender, updated by the bot with a count), by number of repositories hit, and by whether the takedown was later reversed.

## Seed bot

The entire community is the bot. Backfilling the full history gives it years of posts on day one; from then on it's a commit poller.

## Builds on

- [github/dmca](https://github.com/github/dmca) via the GitHub API or a plain `git pull` on a schedule
- The mirror-and-flair pattern from [Delisted](delisted.md) and [Deletionpedia](deletionpedia.md)

## Open questions

- Volume is bursty: one anti-circumvention sweep can be hundreds of notices in a day. Group by sender-and-day into one post with the list in the body when a burst exceeds a threshold.
- Other sources with the same shape: Lumen (already [Delisted](delisted.md)), GitLab's and Hugging Face's transparency reports if they publish per-notice, and npm/PyPI package removals.
- The notices name repositories that may have been reuploaded. Linking to live forks is a judgement call the community should make explicitly in its rules.
