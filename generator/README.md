> **Update (Nov 11):** this is now built in the main app repo, [Studywithloop/loop](https://github.com/Studywithloop/loop). Work on `api/generate.js` there instead of starting from scratch here.

# Feed generator — Beatriz

**Goal:** upload a lecture PDF or slide deck → loop. builds the feed automatically (no copy-pasting into ChatGPT).

## Input → output
- **Input:** PDF / exported slides.
- **Output:** feed JSON (see `CLAUDE.md`): 6–10 `concept` cards (≤45 words, example, `source: "slide N"`) and a `quiz` after every 2 concepts.

## Plan
1. Small backend endpoint `POST /generate` that receives the PDF and calls the Claude API (PDF input + structured outputs for the feed schema).
2. Upload screen in the app → shows a progress state → opens the feed.
3. Quality check: compare with the hand-written demo feed; every card must cite a slide that really says it.

## Done when
- [ ] A real IE lecture PDF becomes a feed in under a minute
- [ ] 0 cards with facts not in the slides (check by hand on 3 decks)
- [ ] Works from a phone

Claude API default model `claude-opus-5-5`; load the claude-api skill first; key in `.env`.
