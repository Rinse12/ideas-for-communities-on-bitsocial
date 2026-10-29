# Community Auction

> Every year the community's name goes to the highest bidder, who decides what it's about until the next auction.

**Kind:** governance
**Effort:** L
**Needs:** on-chain auction contract

## How it works

1. The community lives at a memorable `.bso` / `.eth` name.
2. Once a year an on-chain auction runs for it. The winner gets the name, points it at their own community, and sets the theme for the year.
3. Next year it's auctioned again.

## The unique part

Only possible because **a community's name is transferable property** on chain. No platform has to approve the handover, and nobody can take the name away mid-term.

Making the term enforceable:

- With ENS, the auction contract can issue the name as a **wrapped subname with a one-year expiry** (e.g. `this-year.auction.eth`). The holder controls it for the term, and it returns automatically. The same works on `.bso` if it supports an equivalent.
- Simpler version: transfer the full name to the winner and trust them to put it up for auction next year.

## What moves and what doesn't

The name points to a community address. Transferring the name doesn't move the old posts: last year's community stays at its key-based address, archived, and the name now points at the new owner's community. Optionally the previous owner can hand over the community key too, so the history continues.

## Builds on

- ENS NameWrapper (or `.bso` registry), an English-auction contract
- The proposed Bitsocial Chain / BSO token, if it happens

## Open questions

- Where do the proceeds go: the previous holder, a treasury, burned?
- A minimum-rules covenant (e.g. no illegal content) can't be enforced on chain, only socially.
