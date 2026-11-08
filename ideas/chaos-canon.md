# Chaos Canon

> A story, wiki or fictional world written by an LLM, where every member's prompt goes straight into the canon, in order, no votes.

**Kind:** game · building together
**Effort:** M (uses the `builder.bso` bot from [Vibe App](vibe-app.md))
**Needs:** LLM API key

## How it works

1. The community has one text project: a novel, a lore bible for an invented world, a fake encyclopedia. The pinned post links the current version.
2. A member posts a prompt: "the king has been dead the whole time", "add a chapter from the dragon's point of view", "the capital city floods".
3. The bot applies it **right away**, in the order prompts arrive: one LLM call rewrites the text with the change, keeping everything else consistent.
4. The bot replies with the new version and a short summary of what changed, and credits the author.

It works like [One Word Story](one-word-story.md), but with whole plot twists instead of single words, and an LLM making it all fit together.

## The unique part

- **No votes, no rounds.** Chaos is the point: every prompt becomes canon, and the LLM has to make even "and then everyone turned into crabs" consistent with what came before.
- The feed is a readable history of the world. You can scroll back and see the exact prompt that made the moon fall.
- The per-user limits in the bot's queue (see [Vibe App](vibe-app.md#queue-and-throttling)) keep one person from writing the whole story.

## Variants (other modes)

- **Upvote rounds:** a slower canon where only the most-voted twist each day goes in, as in [Slow Repo](slow-repo.md).
- **Fork-and-preview:** the bot writes each twist into its own version, people read them and vote, as in [Vibe App](vibe-app.md).
- **Lottery:** one prompt drawn per round, as in [Prompt Lottery](prompt-lottery.md).

## Seed bot

The bot writes the opening: a premise, a few characters and a place. Then it posts a starter prompt itself every few hours while the community is quiet.

## Builds on

- `builder.bso` ([Vibe App](vibe-app.md)) in "every prompt in order" mode
- [One Word Story](one-word-story.md), the same idea at a smaller scale

## Open questions

- **Defacement:** with no vote, a troll's prompt lands immediately. Mods can remove the post, but taking the change out of the text is a future TODO (see [Vibe App](vibe-app.md#open-questions)).
- **Length:** a long story stops fitting in one LLM call. The bot could keep a summary and rewrite only the latest chapter, or close the book and start volume 2.
- **The LLM's own tone:** the LLM tends to smooth every twist into the same voice. A setting for "how hard to resist the prompt" might help.
