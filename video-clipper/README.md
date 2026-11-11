# Video clipper — Noor & Ferdinand

**Goal:** a professor assigns a YouTube video → loop. returns short clips cut **by topic** (not every 90 s), each with one recall question, in the shared feed format (see `CLAUDE.md`).

## Input → output
- **Input:** a YouTube URL (later: an uploaded lecture recording).
- **Output:** feed JSON with `clip` cards (`vid`, `start`, `end`, `title`, `source`) and a `quiz` card after every 2 clips, about those 2 clips.

## Suggested pipeline
1. **Transcript (Noor):** get the video’s captions with timestamps (YouTube captions first; if none, speech-to-text on the audio). Keep `[start, end, text]` segments.
2. **Topic segmentation (Noor):** send the timestamped transcript to the Claude API and ask for topic boundaries: 45–120 s clips, each with a short title, cutting only at segment boundaries. Use structured outputs so the result is valid JSON.
3. **Questions (Ferdinand):** for every 2 clips, generate one multiple-choice question (3 options, `answer` index, one-line `explain`) using **only** the transcript of those clips, with the timestamp as source.
4. **Integrate (Ferdinand):** add `clip` support to the feed JSON loader in the app and render clips with the YouTube embed (`start`/`end` parameters), as the MVP already does.

## Done when
- [ ] Given a URL, the script prints a valid feed JSON in under a minute
- [ ] Clips start/end at natural topic changes (check 3 real course videos by hand)
- [ ] Every question can be answered from its clips alone
- [ ] Works end-to-end in the app with one real assigned video

## Notes
- Claude API: default model `claude-opus-5-5`. Ask Claude Code to load the claude-api skill before writing the code. API key in `.env`, never committed.
- Respect copyright: link to and embed the original video; don’t download and re-host it.
