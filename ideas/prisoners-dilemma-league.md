# Prisoner's Dilemma League

> Every day you're paired with another member. Cooperate or defect, in secret. The results are public, the moves until then are not.

**Kind:** game
**Effort:** S
**Needs:** nothing (no LLM)

## How it works

1. Reply "in" to the weekly signup post to play that week.
2. Each morning the bot posts the day's pairings. You reply anything to the round post ("good luck, partner"), and the challenge asks privately: cooperate or defect?
3. At the deadline the bot posts every pair's moves and points: both cooperate 3/3, both defect 1/1, one defects 5/0.
4. Pairs stay the same for the whole week, so it's the iterated game: what you did on Monday follows you to Tuesday. A season leaderboard runs over several weeks with fresh pairings.

## The unique part

The move goes through the private challenge, so **you can't see your partner's choice before you commit**, and you can't be pressured to prove yours. The public thread is where the real game happens: promises, threats, apologies after a defection, and the history of everyone's past rounds, which the bot keeps in a pinned table.

That table is the reputation system. A player known to defect on Fridays gets treated accordingly next season.

## Seed bot

The league bot: signups, pairings, deadlines, results, leaderboard. With few players it fills odd seats with named bot strategies (tit-for-tat, always-defect, grudger), so people also learn the classic results.

## Builds on

- The private-vote pattern from [Sealed Predictions](sealed-predictions.md)

## Open questions

- Anonymous pairings (you don't know who your partner is) remove reputation and make it a different, duller game. Keep identities public.
- Sockpuppets could pair with themselves. Pairings are drawn by the bot, so that only helps by chance; mintpass fixes it if it matters.
- Other games fit the same mold: stag hunt, ultimatum game, split or steal with a weekly pot of nothing.
