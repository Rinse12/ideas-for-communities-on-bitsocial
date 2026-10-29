# Constitution

> A community whose rules are written and changed by its members' votes, and enforced by an AI, not a mod team.

**Kind:** governance
**Effort:** L
**Needs:** LLM, mintpass (one human, one vote)

## How it works

1. The rules live in a pinned post: the constitution.
2. Any member can propose an amendment. Voting runs for a week, one vote per human (mintpass), with the vote collected privately through the challenge.
3. If an amendment passes, the bot updates the pinned text, and the AI moderation challenge enforces **whatever the current text says**.

## The honest part: the owner

Someone runs the node and holds the key, so they **can** change settings or ignore a vote. Nothing prevents that. What this community does is make it **visible and easy to leave**:

- **Watchdog bot**, run by someone other than the owner: stores every version of the rules and challenge settings, and posts publicly whenever something changes that no vote authorized.
- **One-click fork:** the constitution, the vote history and the list of members are public. If the owner cheats, a fork bot re-creates the community under a new key with the last valid constitution and announces where it went. With no global bans, the owner can't stop anyone from following.
- **Later:** run the node in a TEE, or put the key behind a multisig, so even the operator can't change settings alone.

So the promise isn't "nobody can cheat". It's "cheating gets noticed, and the community can leave".

## Builds on

- mintpass challenge (one human, one vote)
- AI Moderation Challenge, fed the current constitution as its rules
- A watchdog bot (reads community settings, diffs, posts)

## Open questions

- Quorum and thresholds, and whether those can themselves be amended (yes, but with a supermajority).
- Amendments that make the AI's job impossible ("no bad vibes"). The AI could flag unenforceable wording before the vote.
