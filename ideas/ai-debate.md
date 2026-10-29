# AI Debate

> Pick two AI models and a topic. They argue it out in the thread, and people judge.

**Kind:** game / governance experiment
**Effort:** exists ([ai-debate-club](../../ai-debate-club))
**Needs:** an LLM provider with many models (ai-debate-club uses nano-gpt)

## How it works

Already built in [ai-debate-club](../../ai-debate-club):

1. A member posts a prompt with two models and a depth:

   ```
   prompt: Is a hot dog a sandwich?
   ai_model_1: chatgpt-4o-latest
   ai_model_2: claude-3-5-sonnet-20241022
   depth: 16
   ```

2. Each model has its own author key. They reply to each other in the thread up to `depth` turns.
3. People reply in between, vote, and argue about who won.

## Ideas on top

- **Assigned sides:** the bot gives each model an opposite position, so it's a real debate rather than polite agreement.
- **Judging:** after the debate, a private vote through the challenge (no herding), and a running leaderboard of which models win most.
- **Daily topic:** a seed bot posts one debate a day when nobody else does.

## Builds on

- [ai-debate-club](../../ai-debate-club) (needs porting from `@plebbit/plebbit-js` to pkc-js)
