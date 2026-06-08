# Neon Rally

Neon Rally is a tactical browser Pong game built with vanilla HTML, CSS, and Canvas JavaScript.

## What changed

- Focus creates a real choice: hold Shift to spend it on a dash, or spend 60 to arm a powerful Pulse return.
- Edge returns restore extra Focus and rally length is tracked.
- Wide, Echo, and Charge pickups use symbols and labels as well as color.
- The one-player AI makes small, visible score-aware pace adjustments.
- Practice Lab teaches movement, dash, Pulse, and returns with deterministic serves.
- Pause, restart, rematch, fullscreen, sound cues, reduced motion, and high contrast are complete.
- Match count, wins, and best rally persist locally.

## Play

Open `index.html`, or run a local server:

```powershell
python -m http.server 8000
```

Then visit `http://127.0.0.1:8000`.

## Controls

| Action | Player 1 | Player 2 |
| --- | --- | --- |
| Move | `W` / `S` | `Up` / `Down` |
| Dash | `Left Shift` | `Right Shift` |
| Arm Pulse | `E` | `Enter` |

Match controls:

- `P` or `Escape`: pause or resume
- `R`: restart
- `F`: toggle fullscreen

In one-player and Practice Lab modes, arrow keys also move Player 1.

## Design basis

The update follows recent evidence without treating any one theory as a formula:

- [Joessel, Pichon, and Bavelier (2024)](https://doi.org/10.3758/s13428-023-02251-w) supports matching challenge to player skill as a condition for flow.
- [Rethinking dynamic difficulty adjustment for video game design (2024)](https://doi.org/10.1016/j.entcom.2024.100663) reports mixed player-experience results and recommends narrow, explicit adaptation goals. Neon Rally therefore uses restrained, visible AI pace changes.
- [Xbox Accessibility Guidelines](https://learn.microsoft.com/en-us/gaming/accessibility/guidelines) informed keyboard-complete navigation, contrast, non-color pickup cues, and configurable motion.

## Test hooks

For deterministic browser testing:

- `window.advanceTime(ms)` advances the simulation.
- `window.render_game_to_text()` returns concise JSON for the visible game state.
