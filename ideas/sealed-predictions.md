# Sealed Predictions

> Forecast real-world questions privately, get scored when they resolve. A forecasting league with no money involved.

**Kind:** game
**Effort:** M
**Needs:** no keys (Manifold / Metaculus / Polymarket public APIs)

## How it works

1. The bot posts open questions from public prediction markets ("Will X happen by Dec 31?"), linking the source.
2. To predict, you reply and give a probability (0–100%) through the challenge. The reply itself is for your reasoning.
3. When the source question resolves, the bot posts the result and everyone's Brier score. The monthly leaderboard winner gets `Top forecaster` flair.

## The unique part

**Sealed forecasts.** Nobody sees anyone's number until resolution, so there's no herding toward the first confident reply. Two modes:

- **Simple:** the custom challenge stores your probability. You trust the community node not to peek or tamper.
- **Trustless:** you post `sha256(probability + salt)` as a public commitment and reveal it after resolution, and the bot verifies. Needs a small client helper, but nobody, including the owner, can change what you said.

## Seed bot

Fully bot-run from public market APIs, with resolution taken from the same source.

## Builds on

- A custom challenge (simple mode), or the commit-reveal helper (trustless mode)
- Manifold / Metaculus public APIs

## Open questions

- Members could post their own questions, with the bot resolving only the ones linked to a market.
- Show the market's own probability at close as a benchmark: did the community beat the market?
