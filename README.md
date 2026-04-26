# tbr

A 1-level browser remake inspired by **Top Bot** (the 2013 iOS bouncing-robot
racer).

## Play

Open `index.html` in any modern browser. No build step, no dependencies — it's
a single HTML file with the game written in vanilla JavaScript and HTML5
canvas.

```sh
# from the repo root, any of these work:
xdg-open index.html        # linux
open index.html            # macOS
python3 -m http.server     # then visit http://localhost:8000
```

## How it plays

Your bot bounces forward on its own across a hilly track. You only control
**how high it bounces**:

- **Tap / click / Space** — hold at the moment of impact for a higher bounce.
- **Green stripes** on the ground — bounce on one for a speed boost.
- **Red gems** in the air — collect them; each one gives a small zip.
- **Spike mines** on the ground — touch one and the run ends.
- **Checkered flag** at the end of the track — finish line.

The HUD shows your timer, gems collected, and distance. Stars at the end
reflect how many gems you grabbed.

## Files

- `index.html` — the entire game (canvas, physics, art, HUD, level layout).
