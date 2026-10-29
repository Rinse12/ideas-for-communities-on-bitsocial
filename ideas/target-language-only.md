# Target Language Only

> A community for learners of one language where every post has to be in that language. Slip into English and the post bounces.

**Kind:** conversation
**Effort:** S–M
**Needs:** a language detector (no LLM) for the gate; an LLM for corrections (optional)

## How it works

1. One community per language: `aprende-espanol`, `nihongo-dake`, and so on. Any topic, as long as it's in the target language.
2. The challenge runs a language detector over the post. Below a confidence threshold, or detected as another language, the post is rejected with the detected language and a short nudge in the target language.
3. A correction bot replies to posts with mistakes, quoting the sentence and the fix, marked as a bot so nobody has to feel corrected by a person. Members can turn it off per post with a tag.
4. Flair by level: the bot estimates CEFR level from a member's last N posts and sets `A2`, `B1`, ... Members who prefer not to show it opt out.

## The unique part

Language-learning subreddits drift to English within a week because English is easier and nobody enforces anything. Here the **language is the challenge**: the rule is applied before the post exists, uniformly, with no mod effort. The detector is a fast local model (fastText, CLD3 or lingua), so the gate costs nothing and needs no key.

Two refinements the private challenge makes possible:

- **Graded strictness.** The challenge can tell a beginner "that was mostly English, try again, here's one of your sentences translated" without publishing their failed attempt.
- **Hints, not answers.** On rejection the challenge can show the member the word they're probably missing. Nothing public.

## Seed bot

Daily prompt posts in the target language ("Describe your morning", "What did you eat?") from a fixed list, plus link posts to graded readers, news in easy language (News in Slow Spanish, NHK Easy) and public-domain texts.

## Builds on

- A language-detection library (fastText `lid.176`, lingua) in a custom challenge
- [AI Moderation Challenge](https://bitsocial.net/apps) plumbing for the optional correction bot

## Open questions

- Code-switching is normal and useful ("how do you say *deadline*?"). Allow a quoted foreign word or short phrase, reject only when the majority of the text is off-language.
- Short posts defeat detectors. Below ~5 words, pass them.
- Scripts and dialects: the detector must accept romaji for Japanese learners or reject it, and the community should say which.
