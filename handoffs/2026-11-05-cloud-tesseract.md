# Handoff: Tesseract Inside, room events + hold-then-change (cloud Fable, 2026-11-05)

Picked up from the 11/4 evening build of `inside.html` (the one Jaron approved at 6:25 PM). Only `inside.html`, `README.md` and this file changed. Pages and the slice version untouched.

## Done

1. **Entering a room is an event** (`arrive()` in inside.html). Fires when the room you are in changes, never on load.
   - Chime: WebAudio, created in code, AudioContext made/resumed on the first `pointerup`/`touchend`/`keydown` (iOS needs a gesture). One note per room on a major pentatonic from C5, plus a fifth 160 ms later; sine partials through a low-pass, master gain 0.11, about 1.8 s. "Chime on arrival" toggle in the dock.
   - Wash: full-screen div in the room's colour, opacity .42 to 0 over 1.2 s.
   - Name: "you are in the / Blue room" in Unbounded, centre of the screen, 2.1 s fade up, hold, fade away with a slight scale. Reduced motion: opacity only.
   - The room you are in (`mine`) only changes after a candidate cell has held the eye for 120 ms, so a wall brushing past is not an arrival.
2. **Hold, then change.** Own turn is now a state machine: rest (hold timer, slider `hold for` 2–30 s, default 8, with a tiny zero-mean breath of 0.014 rad) then one clean move via `bring(i)`: shortest arc swinging cell i's centre to −w, in a single fixed plane, eased in-out cubic over `move takes` (slider 0.8–6 s, default 2.4). `nextRoom()` picks the least recently visited neighbour (never the room you are in or its opposite, the wraparound room). Arrows (`roomToward(±r3)`), door button (`roomToward(f3)`) and chips all use `bring`, so they land square. Strip drag is unchanged and free-form; any manual input calls `manual()` which cancels the move and restarts the hold. The old `speed`/`steer`/`pending` code is gone.
3. **Seeing into neighbours (item 1 of the missing list, partial).** Walking is clamped to the room's own projected shape shrunk to 86% (`fits()`), with wall sliding; speed 0.8 u/s. Home eye moved to `[0.2, -0.36, -0.12]`. FOV now spans min(W,H) (default 72°) so portrait phones get a usable horizontal view. Default door size 0.62 → 0.70. During any turn the eye eases back to home.
   - Limit found: the wedge's far wall always covers its doorway from inside the inner cube (central projection), so neighbours only read as rooms from the threshold or during a move. Proposed next step: inset walls (a box inside each wedge with a gap) if Jaron wants rooms readable from the middle.

## Tested

Headless Chromium at 400×780 (touch) and 1280×800: no console errors or page errors. Door change, automatic change with hold 2 s, chip, arrow and strip drag all change rooms and fire the overlay. Screenshots looked right at both widths; dock labels fit at 400.

## Not done / watch

- Real iPhone check of the chime unlock (first tap anywhere) and of the silent switch.
- The breath during rest is tiny; if it reads as drift, delete the two `turn(E(..), E(3), ...)` lines in the rest branch.
- The site copy is `lab/tesseract/inside/index.html` in heartbeat-observatory (identical file).
