# tbr

A 1-level browser remake inspired by **Top Bot** (the 2013 iOS bouncing-robot
racer). Single HTML file, no build step, no dependencies.

## Play

Open `index.html` in any modern browser:

```sh
xdg-open index.html        # linux
open index.html            # macOS
python3 -m http.server     # then visit http://localhost:8000
```

Or use the live preview link (no deployment needed):

- https://raw.githack.com/gnixon05/tbr/claude/topbot-game-remake-1TIhL/index.html

## How it plays

It's a time attack. Your bot flies through a snaking passageway from
start to finish; you only control altitude.

- **Hold** tap / click / <kbd>Space</kbd> — thrust upward.
- **Release** — fall under gravity.
- **Green strips** — fly through one for a speed boost.
- **Red gems** — collect for a small zip and a score line.
- **Pillars + corridor walls** — hitting them slows you down (kills any
  active boost), gives a brief invulnerability flash, and shakes the
  camera. They never end the run.
- **Checkered flag** — finish line. Your time is shown and your
  personal best is saved locally.

The level is procedurally laid out from a fixed seed, so it's the same
course every load and your best times are comparable. Use the small
"Reset best time" link on the title screen to clear it.

## Implementation notes

- Single `index.html` with vanilla JS + HTML5 canvas.
- Deterministic mulberry32 PRNG for level layout (gems, strips, pillars).
- Corridor is defined by piecewise section anchors that lerp between
  parameters (half-height, swell amplitude, frequency) — gives wide
  intros, tight straights, and big zigzag stretches.
- Best time stored under `localStorage["topbot.best.v2.<seed>"]`.

## Files

- `index.html` — the entire game.
