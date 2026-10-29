# Ephemeral Confessions

> Say it anonymously. It's gone in 24 hours.

**Kind:** uncensorable
**Effort:** S
**Needs:** nothing

## How it works

1. Post a confession, ideally from a fresh throwaway identity (the community's description shows how to make one in Seedit).
2. People reply for a day.
3. After 24 hours a bot with the moderator role removes (or purges) the post and its replies.

## The unique part

A custom challenge that protects *other* people as well: it rejects posts containing phone numbers, email addresses, street addresses or full names (a regex/NER check), so a confession can't turn into doxxing.

## Be honest about "gone"

Removing a post stops the community node from serving it, but peers that already fetched it may still have a copy. The community's description should say **removed after 24 hours**, not "erased forever".

## Builds on

- A small removal bot (community RPC)
- Wordfilter / custom challenge for the personal-info check

## Open questions

- 24 hours, or a shorter window like 6?
- Reply-only "advice" mode, where the confessor gets answers but nobody can quote them later?
