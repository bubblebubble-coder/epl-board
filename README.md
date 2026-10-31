# Premier League Data Board 2026/27

**English** | [中文](README.zh-Hant.md)

🔗 **Live site: https://bubblebubble-coder.github.io/epl-board/**

A mobile-friendly data board for the 2026/27 English Premier League, covering all 20 clubs. The site updates itself automatically with match data and AI-made pre-match predictions.

## What's on the site

The site has five tabs at the bottom of the screen:

- **Week**: every match in the current round. Each match card shows:
  - the AI's home/draw/away probabilities and its most likely scores
  - half-time outlook
  - expected corners (first half and full time), fouls and yellow cards
  - a confidence level and a short explanation
  - Tap a card to see the full reasoning, injuries and suspensions, confirmed line-ups, the history of every prediction version, and, after full time, prediction vs. actual with a short AI review.
- **Table**: the league table with recent form.
- **Teams**: each club's next match, its per-match averages with its rank among the 20 clubs, and every result this season with detailed stats.
- **Rankings**: compare all 20 clubs on goals, first-half goals, corners, first-half corners, fouls, cards, xG and possession.
- **Accuracy**: how well the AI's predictions have done: result hit rate, exact scores, and the average error on corners, fouls and cards.

The site opens in English by default; use the **中文** button in the top-right corner to switch to Traditional Chinese.

## How it updates

| When | What happens |
|---|---|
| Right after matches finish | Results and match stats are refreshed. Matches that kicked off together are processed together. |
| 1 hour before the round's first match | The AI predicts every match of the round. |
| Every 12 hours during the round | Injuries, line-ups and odds are re-checked. The AI revises a prediction only if something relevant changed. |
| 1 hour and 30 minutes before each kickoff | A final check for confirmed line-ups and late news, such as an injury in the warm-up. |
| After each match | The AI writes a short review comparing its prediction with what happened. |

Every prediction is stamped with the date and time it was made, Malaysia time (UTC+8).

## Data and method

- **Source**: [Sofascore](https://www.sofascore.com) for fixtures, results, first- and second-half statistics, injuries, line-ups and bookmaker odds.
- **Statistical baseline**: a Poisson model built from this season's data and calibrated to the betting market.
- **Final prediction**: made by an AI analyst (Claude). It uses the baseline as one input, then weighs injuries, line-ups, form, head-to-head records, the referee and the match context.

## Repository contents

This repository contains only the published website: `index.html` and `data.json`. The scripts that collect data and run the predictions run privately and are not included.

## Disclaimer

All predictions are for reference and entertainment only. Single matches are highly unpredictable. Nothing on this site is betting or financial advice.
