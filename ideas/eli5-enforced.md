# ELI5, Enforced

> Explain like I'm five, and the community actually checks.

**Kind:** conversation
**Effort:** S
**Needs:** nothing (no LLM)

## How it works

1. Anyone posts a question.
2. Top-level answers must read at or below a set grade level (Flesch-Kincaid grade 6 by default).
3. Too hard? The challenge shows your score and the three hardest sentences, so you know what to simplify.

## The unique part

A custom challenge using a plain readability formula: cheap, deterministic, no API. Questions and follow-up replies aren't checked, only the answers.

**Variant: Up-Goer Five.** Only the 1,000 most common English words are allowed, and the challenge lists the words you used that aren't on the list (after xkcd's Thing Explainer). Harder and funnier.

## Seed bot

Turns a random Wikipedia article into a question each day ("ELI5: what is a phase-locked loop?").

## Builds on

- A readability library (e.g. `text-readability`), a word list for the Up-Goer variant

## Open questions

- Readability formulas can be gamed with short choppy sentences. That's arguably the point.
- Code blocks and quotes should be ignored when scoring.
