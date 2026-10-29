# Steelman First

> Before you argue with someone, show you understood them.

**Kind:** conversation
**Effort:** M
**Needs:** LLM

## How it works

1. Every reply starts with a restatement of the comment it's answering, in your own words, then your argument:

   ```
   Steelman: You think rent control helps current tenants but discourages new building, so it hurts renters long-term.
   Reply: The building effect is real, but…
   ```

2. The challenge checks that the restatement is fair. If not, it says what you missed and you try again.

## The unique part

A custom challenge where an LLM compares your steelman with the parent comment and accepts only a faithful one: no strawmen, no "so you're saying…" twisting. People keep disagreeing, but they disagree with what was actually said.

Optional: the parent's author can mark a steelman `nailed it`, which gives the replier flair over time.

## Seed bot

Daily debate prompts (LLM-generated, or questions from public debate datasets) so there's always something to argue about.

## Builds on

- [AI Moderation Challenge](https://bitsocial.net/apps) patterns

## Open questions

- Short replies ("thanks!", "source?") are a nuisance under this rule. Exempt replies under N words, or only enforce on top-level answers to the post.
- LLM judges can be argued with. Keep the bar at "fair", not "perfect".
