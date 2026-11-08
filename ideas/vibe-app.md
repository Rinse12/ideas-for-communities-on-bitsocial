# Vibe App

> A community that vibe codes one web app or game together: every post is a prompt, every prompt gets a live preview, and the community votes on which one ships.

**Kind:** game · building together
**Effort:** L (the `builder.bso` bot below is shared by [Slow Repo](slow-repo.md), [Chaos Canon](chaos-canon.md), [Prompt Lottery](prompt-lottery.md) and [Seasons](seasons.md))
**Needs:** LLM API key, IPFS node (bitsocial-cli already runs one)

## How it works

1. The community has one project: a single HTML file (a game, a toy, a tool). The pinned post links the current version.
2. A member writes a top-level post with a prompt: "add a high-score table", "make the enemies faster when you're winning", "dark mode".
3. The bot replies with its status: queued, building, then a **preview link** to that member's version of the app.
4. Everyone clicks the previews and votes. People vote on what the change actually produced, not on how good the prompt sounds.
5. When the round closes (24h by default), the top-scoring preview is merged. The bot posts the new version, credits the prompt's author, and opens the next round.

### Rounds

- Every preview in a round is built on the **same main version**, so the winning build is exactly what ships. No rebuilding, and no surprises after the vote.
- Losing prompts don't carry over. Their authors repost them in the next round if they still want them, now built on the new main.
- How votes are counted is a setting. The default is score (upvotes − downvotes), read from the community's pages when the round closes, with ties going to the earliest post.

### Variants (other modes)

- **Every prompt in order:** no voting. Each prompt is applied to main as soon as it is built, as in [Chaos Canon](chaos-canon.md). This is fun for a toy and fatal for anything that has to keep working.
- **Upvote rounds without previews:** vote on the prompt text, then build only the winner, as in [Slow Repo](slow-repo.md). It costs one LLM call per round instead of one per prompt.
- **Lottery:** one prompt per round is drawn at random from a verifiable source, as in [Prompt Lottery](prompt-lottery.md).

## The unique part: the `builder.bso` bot

A new third-party bot, installed the same way as [@askwise](https://github.com/Rinse12/askwise-bot), but built for a different job. Askwise answers questions and keeps no state. The builder keeps a project, its versions and a queue.

### Installing

- Like askwise: the owner adds challenge excludes for `builder.bso` (for replies only), so the bot isn't stopped by the community's own challenges. Then the owner registers the community in the bot's registry community, and the bot checks that consent before it starts watching.
- The operator pays for the LLM. An owner who wants their own key and limits can run their own copy of the bot.
- **Sybil resistance is up to the owner.** The bot doesn't require any challenge. A casual community can leave posting open, and a community worried about prompt spam can add mintpass or a voucher.

### Prompts

- In an installed community, **every top-level post is a prompt**, and replies are discussion. The owner can switch on a **mention-only** setting so that only posts mentioning `@builder` count, for communities that mix normal posts with building.
- How a prompt becomes a change depends on the kind of project:
  - **single file** (web app, story page, lyrics): one LLM call that gets the current file plus the prompt and returns the whole new file
  - **repo** ([Slow Repo](slow-repo.md)): a coding agent in a throwaway sandbox checkout, with a limit on turns and cost
  - **image or song** ([Prompt Lottery](prompt-lottery.md)): an image-edit or music model that takes the previous version as input

### Queue and throttling

Every number is an owner setting. Global fairness is the operator's setting.

- **Per user:** at most N prompts waiting at once (default 1) and M per day. Extra prompts get a reply like "queued, you're #4" or "limit reached, try after 14:00".
- **Per post:** one build, plus at most K re-rolls requested by the author.
- **Per community:** a cap on builds per hour and on spend per day. When a community hits its cap, its prompts wait for the next window and are not dropped.
- **Global:** round-robin between communities, so one busy community can't starve the others.
- **Order:** first come, first served within a community. Each prompt gets a status reply (queued → building → preview link, or failed with a reason).

**Optional `builder-quota` challenge.** Normally a prompt over the limit is published and then answered with "limit reached". An owner can add a small custom challenge that asks the bot whether the author has a free slot, and reject the post before it's published. This keeps the feed clean but ties the community node to the bot's uptime, so it's off by default.

### State and history

- The bot keeps its working copy, round state and queue **on local disk**.
- Every merged version is a **bot post** containing a content-addressed link (IPFS CID) to the artifact and a link to its parent version. The community feed is the version history, and the bot's local state can be rebuilt from it.
- The bot pins every CID on its own IPFS node. Catbox is the fallback for media.

### Sandbox

A community-prompted app runs in strangers' browsers, so "add a wallet connect button that sends to 0x…" or a hidden miner is a real risk.

- By default, every build is served in a sandboxed iframe with a CSP that blocks all network access (`connect-src 'none'`, no external scripts). The app can't send data out or load a phishing page.
- An AI moderation pass reviews each diff before the preview link is posted.
- The sandbox is a setting. An owner can allowlist domains, for example an API the community runs for an online leaderboard.

### Credit

- Every merged version's post names the author of the prompt that produced it.
- A **contributors** page sort ranks members by merged prompts.

## Seed bot

The bot opens the first round with a starter app (a blank canvas with a title, or a tiny game) and a few example prompts, so the first visitors have something to click on and something to change.

## Builds on

- [@askwise](https://github.com/Rinse12/askwise-bot): its install, exclude and registry pattern
- LLM API (Claude or any other)
- IPFS pinning through the bitsocial-cli node
- [AI moderation](https://bitsocial.net) challenge for the diff review

## Open questions

- **Mod removals (TODO):** when a mod removes a prompt that was already merged, the change should probably come out of the artifact. The plan is a revert of that version's diff at the head, the way `git revert` works, with the LLM resolving conflicts with later changes. Not designed yet: for now a removal only hides the post.
- **Cost:** fork-and-preview means one LLM call for every prompt in a round, not one per round. The per-community spend cap keeps it bounded, but a popular round gets expensive.
- **Single-file ceiling:** after enough rounds the file gets too big for one LLM call to rewrite reliably. At that point the project graduates to [Slow Repo](slow-repo.md) or ships, as in [Seasons](seasons.md).
- **Vote brigading:** whoever brings friends wins the round. That's the owner's call, through whatever challenge they put on votes.
