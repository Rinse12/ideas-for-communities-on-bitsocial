# Seasons

> A community that builds one thing at a time with an LLM (a game, a repo, a story, a song), ships it, then votes on what to build next.

**Kind:** building together
**Effort:** M on top of the `builder.bso` bot from [Vibe App](vibe-app.md)
**Needs:** whatever the current season's kind needs

## How it works

1. Each season has one project, of any of the four kinds:
   - a web app or game ([Vibe App](vibe-app.md))
   - a repo ([Slow Repo](slow-repo.md))
   - a story or wiki ([Chaos Canon](chaos-canon.md))
   - an image or song ([Prompt Lottery](prompt-lottery.md))
2. Members prompt it for the whole season, in whatever selection mode the community uses (rounds with previews, upvotes, every prompt in order, or a lottery).
3. The project **ships**. When that happens is a setting:
   - at the end of a fixed season length (e.g. 30 days)
   - and/or when a "ship it" post passes a score threshold
4. A **proposal round** opens. Each proposal post names a kind and a pitch ("a roguelike where you're the dungeon", "a lore bible for a desert planet"). The winner is picked with the community's usual mode, and the next season starts.

## The unique part

- **A gallery of shipped projects:** every season's final version is already a CID in the feed, so the community collects a permanent gallery of things it built together.
- **A natural end for projects that outgrow the format:** a single-file app that gets too big, or a story too long for one LLM call, ships instead of slowly breaking.
- **One bot for every kind:** the `builder.bso` bot switches pipelines (single-file call, coding agent, image or music model) from season to season.

## Seed bot

The bot proposes the first season itself, and posts a proposal or two in each proposal round if few members do.

## Builds on

- `builder.bso` ([Vibe App](vibe-app.md)), with all four kinds
- [Vibe App](vibe-app.md), [Slow Repo](slow-repo.md), [Chaos Canon](chaos-canon.md), [Prompt Lottery](prompt-lottery.md)

## Open questions

- **Settings that change with the kind:** limits that suit a cheap text season (many prompts) are wrong for a repo season (few, costly builds). The bot may need settings for each kind.
- **Unfinished projects:** should a shipped project be able to come back for a second season?
