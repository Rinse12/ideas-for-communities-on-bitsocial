# Delisted

> The URLs someone asked Google to remove from search results, and who asked.

**Kind:** uncensorable
**Effort:** S–M
**Needs:** Lumen database API (free token on request)

## How it works

1. The [Lumen database](https://lumendatabase.org) receives copies of the removal requests sent to Google, Bing, Twitter and others: court orders, defamation claims, government requests, copyright notices.
2. The bot posts the interesting ones: the sender, the stated reason, the URLs asked to be delisted, and a link to the notice. Flairs by type: `court order`, `government`, `defamation`, `trademark`.
3. The bot checks whether the URL still appears in search and whether the page is still up, and updates the post.
4. Readers discuss whether the request was reasonable. Often it is. Sometimes it's a company burying a bad review.

## The unique part

Google publishes the counts in its transparency report, Lumen publishes the notices, and almost nobody reads either. A community turns the stream into something with comments, and it can't itself be asked to delist anything: there is no company to send the notice to.

## Seed bot

Fully bot-run. The notice text is already public on Lumen. The bot posts the notice, not the content of the delisted pages.

## Builds on

- Lumen database API and its notice types
- Google's transparency report for the running counts

## Open questions

- Volume and signal: bulk copyright notices from anti-piracy firms are thousands a day and all the same. The bot skips the `DMCA` type by default and keeps court orders, government requests, defamation and "other".
- Requests about private individuals (right-to-be-forgotten style, revenge content) are the ones Lumen already redacts. The bot skips anything redacted and anything naming a private person in the URL.
- Per-country versions: requests from a given government, which are the ones people in that country most want to see.
