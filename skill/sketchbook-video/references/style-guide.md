# Zahra's sketchbook style

## Look
- Paper: `#f6f2e8` (palette `#fbfaf6 #f6f2e8 #efe8d6 #e6dcc4`). Less beige than first tried, **no vignette / dark corners** (she disliked the vintage look).
- Ink: charcoal `#161514`, slightly heavier lines for contrast. Charcoal grain comes from the destination-out pattern; wobble is two-pass Catmull-Rom.
- Text: Caveat 700 by default, **large**, written on **straight lines** (no tilt). Other fonts available: Kalam, Patrick Hand, Shadows Into Light, Gloria Hallelujah, Architects Daughter, Reenie Beanie, Permanent Marker, DM Sans, DM Mono (use mono for code).
- Colour accents (individually per element): red `#c0392b`, orange `#e07b00`, gold `#d4a017`, green `#2e8b57`, teal `#0f8b8d`, blue `#2563eb`, purple `#6d3fc0`, pink `#d6407c`, brown `#7a4b2a`. One colour = one idea, repeated in the note and its highlight on the diagram.
- Images simply appear. They never fade or wipe in.

## Motion and sound
- Lines draw themselves; text writes left to right. Items are timed as "follows previous" with a lag (negative lag = overlap), so a longer line pushes everything after it (sticky timing). Absolute times only when she asks.
- Pages are separated by a `break` item that wipes the previous page. Things stay until the next page unless given a life.
- Sound is a quiet chalk rub only. She rejected "tv noise", "electrical signal", "water drums" and the version with extra grit. Do not add layers to the audio.

## Drawing real parts (from her kit, not textbook symbols)
- **Jumper wire**: thin cable, black bullet-shaped housing, long metal pin. No pointy arrow ends.
- **Resistor**: 5-band 220 ohm = red, red, black, black, brown. (Her 4-band "black black red" was a different part; she found the 5-band.)
- **LED**: round dome, long leg (anode) on the resistor side, short leg to ground; red and yellow used for pairs.
- **Arduino Uno** and the wide breadboard with the blue/red power rails. Pins 9 and 10 for the two-LED lesson, 13 for blink.
- Wire colours: red/blue for signal pins, black for GND, green for the return from the far LED.

## Page layout habits
- Diagram on the left, 3 to 4 numbered notes on the right (x ~ 1190), each note's colour matching a highlight ring or rounded box on the diagram.
- Title top-left in large Caveat; a small grey joke/footer line at the bottom ("Twice the lights, twice the ways to plug it in wrong. Go slowly.").
- Tone: friendly, slightly funny, beginner-first. Explain why, not just what.
- Wires avoid crossing LEDs and each other; route on the breadboard hole grid.

## Existing page templates (left-panel buttons)
Claude chat page (funny "I bought an Arduino kit" exchange recommending Paul McWhorter's course), Arduino IDE (void setup / void loop, colour-coded blink code), Breadboard concept, Parts needed (Arduino, resistor, LED, two jumper wires), Circuit explained (5V, 330 ohm, LED, ground schematic), Build on breadboard (one LED), Two LEDs (pins 9 and 10, shared ground rail).
