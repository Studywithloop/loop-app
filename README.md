# loop.

**Cool kids stay in the loop.** loop. turns university course material (slides, readings, assigned videos) into a 5-minute swipeable feed: swipe to learn, swipe to test, swipe to reinforce.

This repo holds the team’s **docs, pitch and task board**. **The app code lives in [ghayam0/loop](https://github.com/ghayam0/loop) (moving to the Studywithloop org)**: that is the main product code, built by Ghaya on top of the MVP.

| What | Where |
|---|---|
| Live landing page | https://studywithloop.github.io |
| **Main app (v2)** | https://loop-roan-two.vercel.app: accounts, AI feeds from PDFs and YouTube, reels |
| **Main app code** | [ghayam0/loop](https://github.com/ghayam0/loop) (moving to the Studywithloop org) |
| Old MVP (v1) | https://studywithloop.github.io/app/ |
| Landing + MVP code | [Studywithloop/studywithloop.github.io](https://github.com/Studywithloop/studywithloop.github.io) |
| Team inbox | apploopstudy@gmail.com |
| Task board | this repo’s **Issues** tab (filter by your name label) |

## Team
Seven equal partners, each owning one area. Roles and owners: [docs/TEAM.md](docs/TEAM.md).

## What’s in here
```
docs/
  TEAM.md        who owns what, how we work
  PITCH.md       investor pitch plan (Heusch framework), slide owners, numbers to fill
  ROADMAP.md     MVP → final product, in phases
video-clipper/   early notes; the real code is api/video.js in the main app repo
generator/       early notes; the real code is api/generate.js in the main app repo
CLAUDE.md        shared context every teammate’s Claude Code reads automatically
ONBOARDING.md    how to get set up (start here if you’re new)
```

## How we work (short version)
1. Pick your issue on the board, assign yourself, move it to *In progress*.
2. Code changes go in the **main app repo**; docs and pitch changes go here. Make a branch: `git checkout -b yourname/short-topic`.
3. Commit small, push, open a Pull Request, ask one teammate to review.
4. Never commit student data, passwords or API keys (use `.env`, which git ignores).
