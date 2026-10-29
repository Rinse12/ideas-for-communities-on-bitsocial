# Solvers Only

> A puzzle a day. You can only comment once you've solved it, so every thread is spoiler-free by construction.

**Kind:** game
**Effort:** S
**Needs:** no keys (Lichess puzzle API, or member-submitted puzzles)

## How it works

1. The bot posts a puzzle: a chess position from Lichess, a cipher, a logic puzzle, a CTF-style flag hunt.
2. To reply, the challenge asks for the answer. Right answer, your reply is published. Wrong answer, it isn't, and you can try again.
3. Inside the thread, everyone has solved it, so people talk freely about the trick, alternative solutions and how long it took.
4. Members can post their own puzzles: when you post one, the challenge asks you privately for the answer, and the node stores it for your thread.

## The unique part

**The answer is the challenge.** No spoiler tags, no mod removing hints, no "don't read the comments". The gate is enforced at publish time by the community node, and the answer never appears in public unless a solver writes it out.

Answers are stored as a salted hash, normalized (case, whitespace, chess moves in UCI or SAN). A puzzle can accept several answers.

A `Stuck?` comment under each puzzle, posted by the bot, is the one place the challenge doesn't ask for the answer. Replies there can ask for hints, and solvers can answer vaguely.

## Seed bot

- Lichess daily puzzle and the open puzzle database (CC0, millions of positions with solutions, rated by difficulty)
- Generated puzzles with known answers: sudoku, nonograms, simple ciphers
- An "easy / medium / hard" post each day, like Name That Species

## Builds on

- Lichess puzzle API and database
- The same one-guess-per-author storage as [Where Is This?](where-is-this.md)

## Open questions

- Member-submitted puzzles with a wrong stored answer lock everyone out. The author can edit the answer, and a puzzle nobody solves in 48 hours gets a bot reply saying so.
- Count solve order: first ten solvers get flair, or keep it uncompetitive?
- For puzzles with a unique answer that's easy to brute-force (a 4-digit number), rate-limit attempts per address.
