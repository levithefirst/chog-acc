# CHOG: The Journey to Robinhood

A 60-second, three-lane endless-runner browser game themed around Chog and the Monad community ("Chog World Order"). The whole game is a single self-contained `index.html`.

**Play:** [chog-acc.vercel.app](https://chog-acc.vercel.app) · [levithefirst.github.io/chog-acc](https://levithefirst.github.io/chog-acc/)

[![Deploy to GitHub Pages](https://github.com/levithefirst/chog-acc/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/levithefirst/chog-acc/actions/workflows/deploy-pages.yml)

## Gameplay

1. Pick one of 10 Chog characters. Each has its own speed, jump, chaos and luck stats. Then enter a player name.
2. Run for 60 seconds. Difficulty ramps up over the first 8 seconds.
3. Grab pickups, avoid hazards, and try to beat your best score.

| Collect | Effect |
|---|---|
| $CHOG Coin | Bonus score and a small speed boost |
| Chaos Bomb | Clears nearby obstacles |
| Unhinged Mode | Temporary invincibility |

Hazards to avoid: **Sniper Bot, Rug Pull, Bubblemap Cluster, FUD Cloud**.

**Controls**

| Input | Desktop | Mobile |
|---|---|---|
| Switch lanes | `A` / `D` or `←` / `→` | Swipe left / right |
| Hop | `W`, `↑` or `Space` | Tap |

When a run ends you can retry, view the leaderboard, copy a share message, post it to X with a tweet intent, or save a score-card image to attach to your post.

## How it works

- **One file.** `index.html` holds all markup, CSS and JavaScript (~470 KB), with character art embedded as base64 data URIs. There is no build step, no dependencies and no backend. The only external request is for Google Fonts.
- **Local-only state.** The best score overall and per character, the selected character, the player name, the muted setting, and the leaderboard are all stored in `localStorage` under `chog_journey_*` keys. The leaderboard shows top runs on the current device only. There is no global leaderboard.
- **Audio.** Sound effects are synthesized with the Web Audio API, which starts on the first user gesture.

## Running locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deployment

`.github/workflows/deploy-pages.yml` publishes the repo root to GitHub Pages on pushes to `main` or `claude/commit-and-deploy-8o1v69`, or when run manually. The Vercel URL currently serves the same `index.html`. The repo has no Vercel config file, so it is presumably connected through Vercel's Git integration.

> [!NOTE]
> The share text links to a placeholder, `https://YOUR-VERCEL-LINK.vercel.app` (`SHARE_LINK` in `index.html`), so shared posts don't link to the live game yet.

## License

No license specified.
