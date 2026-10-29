# One Word Story

> A story written by everyone, one word at a time.

**Kind:** game
**Effort:** S
**Needs:** optional LLM for chapter titles

## How it works

1. The bot opens a new story every day with a first sentence.
2. Each reply adds exactly **one word**, replying to the current last word. The story reads down the reply chain.
3. At the end of the day the bot posts the full text as "Chapter N", gives it a title, and opens the next one.

## The unique part

A custom challenge enforces the rules at publish time, so no moderator is needed:

- the content is one word (punctuation allowed: `dragon.` `"Run!"`)
- it replies to the **current end** of the chain. If someone else got there first: "someone added a word, refresh and try again"
- you can't add two words in a row

## Seed bot

The bot writes each day's opening sentence (LLM or a list of public-domain first lines) and posts the compiled chapters.

## Builds on

- A small custom challenge, nothing else

## Open questions

- Chains of one-word replies nest deep. Seedit may need a "flat" view for this community, or the bot's chapter post becomes the readable version.
- Variants: six-word stories, haiku only (5-7-5 enforced), sentence-at-a-time.
