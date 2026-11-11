# Sketchbook Studio

A visual editor for making "sketchbook" explainer cuts for videos: off-white paper, charcoal-style hand-drawn lines that draw themselves, handwriting text and a chalk sound. Made for an Arduino-learning video series.

<p align="center">
  <img src="assets/screenshots/blink-draw.gif" width="600" alt="A sketchbook page drawing itself: the title 'Blink an LED' is handwritten, then a circuit appears stroke by stroke, from the D13 pin through a 220 ohm resistor and a red LED to ground">
</p>

Single file, no build step, no dependencies. Open `index.html` in a browser, or try it at **https://zahra-hasan.github.io/sketchbook-studio/**.

![The Sketchbook Studio editor: tools, ready-made page buttons, colours and parts on the left, the 1920x1080 board in the middle with playback controls, style settings on the right, and the timeline underneath](assets/screenshots/editor.png)

## Features
- Draw parts (resistor, LED, Arduino, breadboard...), wires, freehand lines, text and images on a 1920x1080 board
- Scale, rotate, multi-select, copy/paste, smart guides
- Timeline with sticky "follows previous" timing, overlaps, page breaks and per-item lifetimes
- Per-item colours and fonts, text editing on the board
- Ready-made pages: Claude chat, Arduino IDE, breadboard, parts, circuit, build, two LEDs
- Chalk sound, export to PNG, scene JSON and MP4/WebM video

## Ready-made pages

One click adds a finished page to the timeline. Every line, word and part draws itself in order when you press Play, and you can double-click any text to rewrite it.

| | |
|:---:|:---:|
| ![A Claude chat page: the question 'I bought an Arduino kit. How should I use it to learn?' and a funny three-step answer](assets/screenshots/page-claude-chat.png)<br>**Claude chat** | ![An Arduino IDE page: the blink.ino sketch with notes explaining that setup() runs once and loop() runs forever](assets/screenshots/page-arduino-ide.png)<br>**Arduino IDE** |
| ![A breadboard page explaining power rails, the short connected columns and the middle gap](assets/screenshots/page-breadboard.png)<br>**Breadboard** | ![A parts page with four cards: one Arduino board, one LED, one 220 ohm resistor and two jumper wires](assets/screenshots/page-parts-needed.png)<br>**Parts needed** |
| ![A circuit diagram of the 5V source, resistor R1, LED and ground, with notes on each part and arrows showing current flowing round the loop](assets/screenshots/page-circuit-explained.png)<br>**Circuit explained** | ![The LED circuit built on a breadboard next to an Arduino, with four numbered wiring steps](assets/screenshots/page-build-on-breadboard.png)<br>**Build it on the breadboard** |
| ![Two LEDs wired to pins 9 and 10 on a breadboard, with numbered notes on wires, resistors and the shared ground](assets/screenshots/page-two-leds.png)<br>**Two LEDs** | ![The starting scene: 'Blink an LED' with a hand-drawn circuit from pin D13 through a resistor and LED to ground](assets/screenshots/page-blink-an-led.png)<br>**The starting scene** |

## Claude skill
`skill/sketchbook-video` teaches Claude to start a new video in this style. Copy it to `~/.claude/skills/` to use it in Claude Code.

```bash
cp -R skill/sketchbook-video ~/.claude/skills/
```

## License
MIT, see [LICENSE](LICENSE).
