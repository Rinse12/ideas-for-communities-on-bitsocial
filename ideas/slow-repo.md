# Slow Repo

> An open-source project steered entirely by posts: each round, the community's top-voted feature request gets built by a coding agent and merged.

**Kind:** building together
**Effort:** L (uses the `builder.bso` bot from [Vibe App](vibe-app.md))
**Needs:** LLM API key, a sandbox for the coding agent, a git host to mirror to

## How it works

1. The community has one repo: a CLI tool, a library, a small site, anything with more than one file. The pinned post links the current version and the git mirror.
2. A member posts a prompt: a feature, a bug report, "rewrite the parser, it's slow".
3. People vote on the **prompts themselves** during the round (24h by default). Nothing is built yet.
4. When the round closes, the bot builds the top-scoring prompt: a coding agent works in a throwaway sandbox checkout, runs the tests, and the result is merged.
5. The bot posts the new version (IPFS CID, parent version, a summary of the diff, test results) and credits the prompt's author. The merge is also pushed to a git mirror, so anyone can clone it.

It's open source in slow motion: one feature a day, chosen by the people who use it.

## The unique part

- **Only the winner is built**, so a round costs one agent run however many prompts there are. That matters because an agent run on a repo costs far more than one LLM call on a single file.
- The agent has a limit on turns and cost per build. If it can't make the tests pass within that limit, the bot posts the failure and the round's runner-up is built next.
- The community feed is the changelog: every merged version is a post naming the prompt and its author.

How the bot installs, queues, throttles and stores state is described once in [Vibe App](vibe-app.md#the-unique-part-the-builderbso-bot).

## Variants (other modes)

- **Fork-and-preview:** build *every* prompt and vote on the results, as in [Vibe App](vibe-app.md). Better decisions, but N agent runs per round.
- **Every prompt in order:** each prompt is built and merged as it comes. A repo will rot quickly this way, which might be the fun of it.
- **Lottery:** a verifiable random draw picks the prompt to build, as in [Prompt Lottery](prompt-lottery.md).

## Seed bot

The bot creates the initial repo from a one-line pitch in the community's description, with a README, a test setup and a working "hello world", and posts a few starter feature requests.

## Builds on

- `builder.bso` ([Vibe App](vibe-app.md))
- A coding agent SDK (e.g. the Claude Agent SDK) in a container
- A git host for the mirror (GitHub, Codeberg, self-hosted)

## Open questions

- **Voting on text:** people vote on how good a prompt sounds, not on what it produces. A vague prompt can win and come out as a mess.
- **Security of the code itself:** unlike the sandboxed web app, people will *run* this code. Each diff needs an AI review, and the README should say plainly that it's community-prompted code.
- **Mod removals (TODO):** same as [Vibe App](vibe-app.md#open-questions): reverting a merged prompt is not designed yet.
- **Licence:** what licence the repo uses, and who holds copyright on agent-written code prompted by many people.
