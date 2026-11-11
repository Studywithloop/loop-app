# loop. — shared context for Claude Code

Read this before helping anyone on the team. Every teammate opens this repo in Claude Code, so this file is how we share context.

## The product
loop. turns a university course’s own material into a 5-minute, TikTok-style revision feed:
- **swipe to learn**: concept cards (30–90 s each) and short clips of videos the professor assigned
- **swipe to test**: after every 2 cards/clips, one quick question about *that* content (active recall)
- **swipe to reinforce**: missed questions come back (spaced repetition), weighted towards the exam date
Every card must link back to its source (slide number or video timestamp). Professors can approve feeds.

Positioning: we don’t replace studying; we fill the gap between the lecture and sitting down to study. Main alternatives: ChatGPT/NotebookLM (need prompts, not course-aware), Quizlet/Anki (no explanations), TikTok/YouTube (not your syllabus).

## Team (lead: Beatriz)
Beatriz (CEO/product, presents), Noor + Ferdinand (tech: video clipper), Bianca (market/competition + professor partnerships), Marcelo (business model + financials), Dalya (validation/user research), Ghaya (go-to-market, brand, Instagram). Details: docs/TEAM.md.

## Brand
Name is always lowercase **loop.** with a violet square dot. Tagline: “cool kids stay in the loop.”
Colours: black `#0D0D0F`, off-white `#F4F2F6`, violet `#7A3CF0` (dark `#5E25D1`), lavender `#DCD0F7`. Font: Plus Jakarta Sans (800 italic for headlines). Headlines lowercase, ending with a violet “.”.

## Feed format (shared by generator/ and video-clipper/)
```json
{
  "title": "Course · topic",
  "cards": [
    {"type": "concept", "id": "c1", "title": "...", "body": "max 45 words", "example": "...", "source": "slide 3"},
    {"type": "clip", "vid": "YOUTUBE_ID", "start": 0, "end": 90, "title": "...", "source": "4:30–6:00"},
    {"type": "quiz", "about": "c1", "question": "...", "options": ["...", "...", "..."], "answer": 0, "explain": "..."}
  ]
}
```
The live MVP (studywithloop.github.io/app/) already renders `concept` and `quiz` cards from this JSON.

## Rules
- **Privacy (GDPR):** never commit or paste real student emails, phone numbers or grades. Use made-up test data. Sign-ups live only in the team Google Sheet.
- **Secrets:** API keys go in `.env` (git-ignored), never in code or chat logs.
- **Content accuracy:** generated cards must only use the source material; always keep the source reference.
- **Claude API:** default model `claude-opus-5-5`. Load the claude-api skill before writing API code.
- Keep the MVP simple; prefer working end-to-end over perfect.
