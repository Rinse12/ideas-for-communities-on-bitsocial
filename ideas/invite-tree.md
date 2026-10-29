# Invite Tree

> Every member was invited by a member. The tree is public, and if someone you invited gets banned, you lose your invites.

**Kind:** gated
**Effort:** M
**Needs:** nothing

## How it works

1. A member who wants to invite someone replies "invite" anywhere. The challenge hands back a one-time code, tied to them, and the reply is dropped (nothing is published).
2. They send the code to the invitee however they like.
3. The invitee's first post: the challenge asks for an invite code. Valid code, they're in, and the node records the edge. From then on they're never asked again.
4. The bot keeps a pinned post with the whole tree: who invited whom, when, and who has been banned. Addresses only, since that's all anyone has.

## The unique part

This is how [lobste.rs](https://lobste.rs/about#invitations) stays civil, done without accounts: membership is a **chain of vouches that can be traced**. A ban is also a mark on the inviter, who loses invite rights for a while, and on their inviter if it keeps happening. People invite carefully.

The code is issued by the node, not signed by the inviter, so there is no key handling for users. The node knows the full tree; the public tree can be the full one or just depth and counts, as the community prefers.

It differs from the existing voucher challenge in that the vouch is a one-time code exchanged out of band, and the consequences flow back up the tree.

## Seed bot

None needed; the first members are invited by the founder. A "requests" community next door, open to anyone, lets people ask for an invite in public.

## Builds on

- The voucher challenge, for the shape of "a member vouches for a newcomer"
- Role changes through `community edit` for bans and invite freezes

## Open questions

- Invite rate limits (lobste.rs has none and relies on accountability) vs. one a week.
- How far up a ban propagates, and for how long.
- Someone with a banned subtree could start over with a fresh address and a new invite. The tree shows it was a fresh address, which is already a signal.
