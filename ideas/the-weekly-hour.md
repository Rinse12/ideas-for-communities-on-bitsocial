# The Weekly Hour

> Open one hour a week. Everyone's there at once, and the rest of the week you can only read.

**Kind:** conversation
**Effort:** S
**Needs:** nothing

## How it works

1. The community announces its hour, say Thursday 20:00–21:00 UTC. A pinned post shows a countdown and the next three dates.
2. Outside the hour, the challenge rejects every post and reply with "Opens in 3 days, 6 hours."
3. During the hour, no challenge at all (or just a captcha). Threads fill fast, because everyone who cares is reading right now.
4. At close, the bot posts a digest: thread count, most-replied post, and a link list. The threads stay readable forever; nothing is deleted.

## The unique part

The challenge is a **clock**. Nothing else changes, but the community behaves like a live event instead of a trickle. Everyone who posts knows their reply will be read within minutes, which is the thing that makes chat rooms feel alive and forums feel dead. Unlike a chat room, the result is a permanent, threaded, searchable archive, and there's no pressure to keep up the other 167 hours.

It suits anything that benefits from synchrony: a weekly office hours for a project's maintainers, a book club chapter discussion, a "what did you ship this week" for a small dev scene, a support group. A community can run several hours for several time zones with the same rule.

Variants:

- **Slow mode** instead of a hard close: one post per address per day, replies unlimited. The challenge counts.
- **Daily ten minutes**, like a standup.
- **Open while the owner is present**: the hour starts when the owner posts "open" and ends when they post "close". The challenge watches for those.

## Seed bot

Not needed. The owner posts an agenda or an opening prompt when the hour starts.

## Builds on

- A custom challenge that compares the current time to a schedule, and nothing else
- Pinned post with the schedule, updated by a small bot

## Open questions

- Clock skew: the challenge runs on the node's clock, so there's no way to cheat it, but a client might show the window as open a minute early. The rejection message should say the exact time.
- Does the archive get read? The digest post is the hook for people who missed it.
- If the hour is too small for the crowd, the fix is a second hour, not a longer one.
