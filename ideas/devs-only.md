# Devs Only

> A forum for developers, where every member has proved a real GitHub account, without logging in with GitHub.

**Kind:** gated
**Effort:** M
**Needs:** GitHub public API (no key needed at low volume)

## How it works

1. On your first post the challenge gives you a short nonce and asks for your GitHub username.
2. You sign the nonce with an SSH key that's on your GitHub account: `ssh-keygen -Y sign -n bitsocial -f ~/.ssh/id_ed25519`, and paste the signature.
3. The challenge fetches `github.com/<user>.keys`, checks the signature, and checks the account is real (age, public contributions). From then on your Bitsocial address is verified and you aren't asked again.

## The unique part

A custom challenge that turns **an SSH key you already have** into membership: no OAuth app, no company in between. The link between your Bitsocial address and GitHub username is known only to the community node, so flair can say `verified dev` or, if you choose, `verified dev · @username`.

## Seed bot

Link posts from Hacker News front page or GitHub trending, so there's something to discuss.

## Builds on

- `ssh-keygen -Y verify` (or the `sshpk` library)
- GitHub's public `.keys` endpoint and user API

## Open questions

- Thresholds: account age, contributions in the last year? Configurable per community, so "Rust devs only" or "maintainers of 100+ star repos" also work.
- Also accept GitLab / Codeberg keys the same way.
