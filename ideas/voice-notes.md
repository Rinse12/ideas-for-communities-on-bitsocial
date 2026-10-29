# Voice Notes

> A forum where every post is a short voice recording. A bot writes the transcript underneath, so it reads like text and sounds like people.

**Kind:** media
**Effort:** S–M
**Needs:** Whisper (local) or a hosted speech-to-text API

## How it works

1. A post is a link to an audio file (catbox, 0x0, any host that serves the raw file). The challenge fetches the link, checks it is audio and under the length limit (say 90 seconds), and rejects anything else, including text-only posts.
2. The post goes up with the link as the body and the duration as the title suffix.
3. A bot transcribes it and replies with the text, marked as the transcript. Clients that render replies show it right under the player link.
4. Replies work the same way: audio in, transcript under. A community can allow text replies too, with a `text` flair, so people without a microphone can still take part.

## The unique part

Voice carries tone, hesitation and accent, which is most of what forums lose, and voice posts are hard to mass-produce. The protocol only moves text, but **a link plus a transcript is a voice forum** that's searchable, quotable and readable on mute, which the audio-first apps never managed. The challenge doing the format check means the community never fills with text no matter how popular it gets.

Uses that fit:

- **Accent map**: read the same passage, the bot pins a map of where members are from (self-declared).
- **Language exchange**: pair with [Target Language Only](target-language-only.md); the transcript is run through the language detector, so you have to *speak* the language.
- **Sixty-second stories**, **daily voice journal**, **song sketches** (the transcript becomes the lyric sheet).
- **Radio call-in**: a weekly thread where the host picks clips to play on a stream.

The transcript also makes the content moderatable with the normal text tools (wordfilter, AI moderation) with no extra work.

## Seed bot

Public-domain audio: LibriVox snippets, Freesound field recordings, old radio from archive.org, posted on a schedule with credit, as onlycats-poster (not on GitHub yet) does for photos. For a conversation community a weekly voice prompt from the owner does more than a bot.

## Builds on

- A custom challenge that fetches the link and checks the content type and duration (ffprobe)
- Whisper or faster-whisper for the transcript bot
- Existing moderation challenges, applied to the transcript

## Open questions

- Hosting: audio links rot. The bot can re-upload to a second host and add the mirror link to the transcript reply.
- Length limit is the main dial. Ninety seconds keeps it a forum; ten minutes makes it a podcast feed.
- Synthetic voices are easy now. A community that cares can pair this with [Nonce in Frame](nonce-in-frame.md)'s idea: the challenge gives you a word to say at the start of the clip.
- Whisper cost is small locally and nonzero hosted. Transcribe only approved posts.
