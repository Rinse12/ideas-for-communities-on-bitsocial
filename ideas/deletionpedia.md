# Deletionpedia

> Every Wikipedia article nominated for deletion, saved here before it goes.

**Kind:** uncensorable
**Effort:** S–M
**Needs:** no keys (MediaWiki API)

## How it works

1. The bot watches Wikipedia's deletion queues: articles for deletion (AfD), proposed deletion (PROD) and the speedy categories it's allowed to mirror.
2. When an article is nominated, the bot fetches its current text, converts it to markdown, and posts it with the nomination reason, a link to the deletion discussion, and the list of contributors.
3. When the discussion closes, the bot updates the flair: `Deleted`, `Kept`, `Merged`, `Redirected`.
4. Readers discuss whether the deletion made sense, and a custom page sort puts the most-argued ones on top.

## The unique part

Wikipedia deletes a few hundred articles a day, and once they're gone the text is only visible to admins. The old [Deletionpedia](https://en.wikipedia.org/wiki/Deletionpedia) did this as a website and went dark. Here the mirror is a community anyone can run or fork, and the content is replicated by whoever reads it.

It's also a feed of things that are *almost* notable: new bands, small companies, local politicians, neologisms. More interesting than the front page.

## Seed bot

Fully bot-run. Wikipedia text is CC BY-SA 4.0, so each post credits the contributors and links the article history (captured at save time, since the history disappears with the article).

## Builds on

- MediaWiki API (`categorymembers` on the deletion categories, `parse` for the text)
- pkc_community_mirroring_subreddit (not on GitHub yet), for the mirror-and-flair pattern

## Open questions

- Some speedy-deletion criteria exist for good reasons and shouldn't be mirrored: attack pages (G10), copyright violations (G12), pure vandalism (G3), and unsourced biographies of living people. The bot skips those, and removes a post if the article is later suppressed (oversighted).
- Volume: AfD alone is 50 to 100 nominations a day. One community per language, and maybe one per topic area, using Wikipedia's deletion sorting lists.
- Also mirror the deletion discussion itself, or only link it?
