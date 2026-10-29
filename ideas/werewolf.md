# Werewolf

> The social deduction game, played on a public forum. Your role and your night actions go through the private challenge, so nobody needs DMs.

**Kind:** game
**Effort:** M
**Needs:** nothing (no LLM)

## How it works

1. The bot opens a signup post. You reply "in" and the challenge answers with your role, privately: `You are a werewolf. The other wolf is 12D3…kq7.` or `You are the seer.` The reply itself gets published and just says "in".
2. Each night the bot posts "Night 3". Every player replies something (the content doesn't matter, "sleeping" is fine) and the challenge asks the question that fits their role: wolves name a target, the seer names someone to inspect, villagers get "sleep well". The seer's answer comes back in the next night's challenge text.
3. In the morning the bot posts who died. The day thread is the public argument. Lynch votes are public replies (`vote: 12D3…kq7`), counted at the deadline.
4. The game ends when the wolves are gone or outnumber the village. The bot posts every role and every night action.

## The unique part

Werewolf needs two things a forum doesn't have: private role assignment and private night actions. Here **both are the challenge exchange**, which only the player and the community node see. The public thread looks like a normal game thread, and the moderation log shows nothing, because nothing was moderated.

Everyone posts every night, so the number of posts gives nothing away. The challenge for a villager is a no-op by design.

## Seed bot

The game bot itself: signups, night and day posts, deadline counting, role reveal. A game needs 7 or more players, so the first games can mix in bot players with a simple strategy (wolves pick the loudest villager, villagers vote with the majority).

## Builds on

- Any text-captcha-style custom challenge, with the challenge text replaced by role-specific prompts
- Address-to-role storage on the node, wiped at the end of each game

## Open questions

- Dead players and spectators should still be able to post, but in a separate "graveyard" thread the challenge keeps living players out of.
- A player can screenshot their challenge text to "prove" a role. That is true in every online Werewolf and is part of the game.
- Timezones: one night and one day per 24 hours, or faster games with a fixed roster?
