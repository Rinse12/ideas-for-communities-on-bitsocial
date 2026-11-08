# Prompt Lottery

> One shared image or song that evolves one edit at a time, and each round's edit is drawn at random from the members' prompts, provably fairly.

**Kind:** game · building together
**Effort:** M (uses the `builder.bso` bot from [Vibe App](vibe-app.md))
**Needs:** image-edit or music model API, a public Ethereum RPC

## How it works

1. The community has one artifact: a painting, a pixel-art city, a song. The pinned post links the current version.
2. During the round, members post prompts: "add a lighthouse", "make it night", "add a saxophone solo".
3. When the round closes, **one prompt is drawn at random**. The bot applies it with an image-edit or music model, which takes the previous version as input.
4. The bot posts the new version (uploaded to IPFS, catbox as fallback) next to the old one, and credits the winner.

After a hundred rounds there's a picture or a song nobody planned, with a visible history of every edit.

## The unique part: a draw anyone can check

1. **When the round opens**, the bot posts: "This round closes at 18:00 UTC. The winner will be drawn from Ethereum block #N", choosing a block that will be mined a few minutes after the close.
2. **When the round closes**, the bot posts the frozen entry list: the CIDs of every eligible prompt, sorted. Nobody knows block N's hash yet, including the bot.
3. **When block N is mined**, the winner is `blockhash mod entryCount`. Anyone can recompute it with a public RPC or a block explorer. No wallet or gas is needed.

The bot can't pick a friend or quietly redraw until it likes the result.

**Variant:** [drand](https://drand.love), the League of Entropy's public randomness beacon, works the same way ("drawn from drand round #N") with no chain at all.

How the bot installs, queues, throttles and stores state is described once in [Vibe App](vibe-app.md#the-unique-part-the-builderbso-bot).

## Variants (other modes)

- **Upvote rounds:** the top-voted prompt wins, as in [Slow Repo](slow-repo.md). This rewards popularity over luck.
- **Fork-and-preview:** render every prompt and vote on the images, as in [Vibe App](vibe-app.md). Image models make this expensive.
- **Every prompt in order:** every prompt is applied as it comes, as in [Chaos Canon](chaos-canon.md). This gives fast, chaotic evolution, which is fun with a cheap model.

## Seed bot

The bot starts with a blank canvas or a four-bar loop, and a few example prompts.

## Builds on

- `builder.bso` ([Vibe App](vibe-app.md)) in lottery mode
- An image-edit model, or a music model that can extend or alter a track
- Any public Ethereum RPC (Bitsocial names already resolve on chain), or drand

## Open questions

- **Leaving entries out:** the bot could drop a prompt from the frozen list. That would be visible, since anyone can compare the list with the community's posts, but it isn't prevented.
- **Drift:** image models lose detail after many edits. The bot might need to re-render from a description every so often.
- **One entry each:** the per-user queue limit (default one waiting prompt) keeps the draw one-person-one-ticket, as far as the owner's challenges stop sock puppets.
- **Mod removals (TODO):** undoing a merged edit is not designed yet (see [Vibe App](vibe-app.md#open-questions)).
