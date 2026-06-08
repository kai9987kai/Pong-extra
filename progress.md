Original prompt: innovate advance improve refine and push also add features and more meaningful play and look at research thats new and best to help

## Direction

- Replace the consequence-free dash with a shared Focus resource used for either movement bursts or an armed Pulse shot.
- Make skill visible through rally counts, edge-hit rewards, match stats, and readable power-up labels.
- Keep adaptive AI adjustments small and visible instead of using opaque rubber-banding.
- Add keyboard-complete menus, pause/restart/fullscreen flows, high contrast, reduced motion, and optional sound cues.
- Add deterministic `window.advanceTime(ms)` and `window.render_game_to_text()` hooks for browser testing.

## Research notes

- Recent flow work supports matching challenge to player skill.
- A 2024 DDA review reports mixed player-experience outcomes and recommends precise, goal-specific adaptation.
- Current Xbox Accessibility Guidelines emphasize input flexibility, contrast, non-color cues, and motion controls.

## Completed

- Implemented the redesigned match loop and UI.
- Ran the required Playwright action loop and visually inspected gameplay screenshots.
- Exercised menu, both players, movement, dash, Focus spending, Pulse, pause/resume, restart, tutorial, power-ups, game over, rematch, and accessibility options.
- Replaced the outdated README with current mechanics, controls, test hooks, and research references.

## Implementation notes

- Focus now creates a tactical tradeoff: dash drains it continuously; Pulse spends 60 and empowers the next return.
- Edge returns grant extra Focus, rallies are tracked, and local career-best rally stats persist.
- Power-ups are labeled Wide, Echo, and Charge rather than relying on color alone.
- Adaptive AI only makes small score-aware speed/reaction changes and exposes its current pace in the HUD.
- Added pause, rematch, fullscreen, reduced motion, high contrast, optional sound cues, and keyboard alternatives.
- Added deterministic browser-test hooks and concise text state output.
- First Playwright run passed without page/console errors. Screenshot review found the visible HUD was outside the captured canvas, so the score, rally, AI pace, and Focus display are now drawn directly on the play surface while semantic values remain in the DOM.
- Tutorial input checks reached the final return drill, but a random practice serve could miss the instructed paddle position. Practice serves are now centered and flat to make the drill deterministic and teach the intended mechanic.
- Full-page browser checks verified menu layout, pause focus, practice instructions, and the high-contrast toggle. Exiting practice left stale training labels behind the menu; menu return now resets to a neutral 0-0 adaptive-AI preview.
- Final automated suite: 15 assertions passed with zero browser console/page errors.
- Final reviewed screenshots cover menu, live gameplay, labeled power-up, practice overlay, pause, high contrast, and game over.

## Handoff

- Implementation and verification are complete.
- Generated screenshots and local server logs are ignored by Git.
