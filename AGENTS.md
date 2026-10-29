# AGENTS.md

This repo is a list of ideas for communities on Bitsocial (for now mostly Seedit communities). Each idea lives in `ideas/<slug>.md` and follows `TEMPLATE.md`. `README.md` holds the index; add every new idea to its table. Bigger tools that several communities could use get their own project directory next to this repo (e.g. `../pkc_community_mirroring_subreddit`) and are linked from the README's Projects section.

## Tips for writing ideas

- **You can write a custom challenge.** Don't limit an idea to the existing challenges (AI moderation, image classifier, R9K, wordfilter, voucher, EVM contract call, flags, captcha, mintpass). A community can run its own challenge with whatever logic it needs, so if an idea needs a new check, describe the custom challenge it would use.
- **The challenge exchange is private between the user and the community node.** A challenge can collect a secret answer (a guess, a vote, a solution) that never appears in the public post.
- **Media works.** The protocol carries only text, but posts can link media uploaded from scripts to hosts like catbox or imgur.
- **Seed bots are encouraged but not required.** onlycats-poster (not on GitHub yet) is the example: it posts on a random schedule from a free source, and a moderation bot checks every post.
- **Communities are key-owned, and their `.bso` / `.eth` names can be transferred on chain.**
