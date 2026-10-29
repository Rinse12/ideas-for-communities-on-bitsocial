# Jury Moderation

> A reported post is judged by three random members. Their votes are secret, the verdict and the tally are public.

**Kind:** governance
**Effort:** M
**Needs:** nothing (mintpass optional)

## How it works

1. To report a post, reply `!report rule 2`. The bot removes the report reply and, once two different addresses have reported, opens a case.
2. The bot posts the case: a link to the post, the rule cited, and three jurors drawn at random from members active in the last month who aren't the author or a reporter.
3. Each juror replies to the case post. The challenge asks for their vote privately: remove, keep, or abstain. The published reply can carry their reasoning or just say "voted".
4. After 48 hours, or when all three have voted, the bot posts the tally and acts on it. Two votes to remove and the post goes. The author can appeal once, to a fresh jury of five.

## The unique part

[Rotating Mod](rotating-mod.md) gives one person the power for a day. This gives three people one decision, and takes the vote through the private challenge so jurors can't be lobbied by watching each other, and aren't individually blamed for a removal. The tally is public, so the community still sees how close a call it was.

The reported post stays up while the case is open. The community's owner is still there for emergencies, and every owner removal shows up in the mod log as an owner removal, not a verdict.

## Seed bot

The bot that runs the cases. Juror eligibility can use mintpass so a pile of fresh addresses can't stack the pool.

## Builds on

- Private vote collection, as in [Constitution](constitution.md)
- Role changes through `community edit` for removals
- mintpass for eligibility (optional)

## Open questions

- Jurors who never show up. If one of three doesn't vote in 48 hours, draw a replacement rather than deciding on two votes.
- Hidden juries: don't publish who was drawn, and let anyone try to vote with the challenge only accepting jurors. Fewer lobbying problems, but jurors have to notice on their own that they were picked.
- A `!report` on a case post itself, or on the jurors' replies, is probably just noise and shouldn't open a case.
