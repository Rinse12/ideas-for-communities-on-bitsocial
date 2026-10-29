# Proof of Reading

> You can only comment on an article you've actually read.

**Kind:** conversation
**Effort:** M
**Needs:** LLM (Haiku-class per comment), with a no-LLM fallback

## How it works

1. Posts are links to articles: news, essays, papers.
2. When you reply, the challenge asks you one question about the article, different for each person: "What reason does the author give for…?"
3. A correct answer gets your comment through. A wrong one gets a hint and another try.

## The unique part

A custom challenge that fetches the article once per post (readability extraction, cached), has an LLM write a question for each commenter and grade the answer. The best place for this is a news community, where most comments respond to the headline.

**No-LLM fallback:** "Type the 4th word of the 2nd paragraph." Crude, but it makes people open the page.

## Seed bot

Link posts from quality long-form RSS feeds (title + link, nothing copied), or arXiv for a science version.

## Builds on

- [AI Moderation Challenge](https://bitsocial.net/apps) as a starting point for the LLM plumbing
- A readability library for article extraction

## Open questions

- Paywalled links: require a readable source, or let the poster paste a summary that the questions are drawn from.
- Cost: one short LLM call per comment, cached questions per article would cut it.
