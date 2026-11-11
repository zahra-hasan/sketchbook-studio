---
name: sketchbook-video
description: Builds explainer-video pages in Zahra's "sketchbook" style (off-white paper, charcoal hand-drawn lines that draw themselves, handwriting text, chalk sound) using her Sketchbook Studio artifact. Use whenever she starts a new video or tutorial, wants new pages/slides for the sketchbook cut, wants a circuit, parts, code or concept page drawn, or says things like "new video", "next tutorial", "sketch page", "Arduino lesson", "add a page for...", even if she doesn't name the studio.
---

# Sketchbook video

Zahra makes Arduino-learning videos: talking head + workshop footage + a "sketchbook" cut where lines draw themselves on off-white paper. **Sketchbook Studio** (`assets/sketchbook-studio.html`, a single-file canvas app) is her editor for that cut. This skill starts a new video in that editor with her style intact and pre-built pages for the topic.

## Workflow

1. **Get the topic.** Ask only for what you can't infer: the video's topic and, if she has one, the script or outline (one page per idea). If she attaches images (Fritzing diagrams, schematics, photos of parts), those are the source of truth for what a page must show.
2. **Copy the studio** to the working folder as a new file named for the video (e.g. `studio-<topic>.html`). A new file gives a new artifact URL, so each video keeps its own autosaved scene and nothing from the last video leaks in.
3. **Add page builders for this video.** Each page is a function like `addTwoLedPage()` plus a left-panel button (`<button class="btn" id="...">` next to the existing ones, `$("id").onclick = fn`). Read `references/page-builders.md` first: it lists the helpers, the coordinate system, and how timing works. Reuse existing builders (chat, IDE code, breadboard, parts, circuit, build, two LEDs) when they fit; write new ones for new content. Optionally call the builders in the starting scene so the video opens with the pages already placed.
4. **Test it** in the Browser pane: click each new button, check for console errors, screenshot, and zoom on small details (wires, labels). Clear `localStorage` afterwards so her first open is clean.
5. **Publish** with the Artifact tool, `capabilities: {downloads: true}` (needed for scene JSON, PNG and video export), a 2 to 4 word title, icon `canvas`. Tell her the link and what each new button adds.
6. **Say what you verified and what you didn't** (e.g. "layout checked, not played through"), and anything you guessed from her pictures.

## Keep her style

Read `references/style-guide.md` before drawing anything. The short version: clean and readable beats decorative, big handwriting on straight lines, thin cables not pointy ends, real kit parts (5-band 220 ohm resistor, bullet-housing jumper wires), one colour per idea, a light joke where it fits. These came from her own corrections, so repeating a mistake she already fixed costs her real time.

## Editing existing videos

If she gives you a published studio link or a saved scene JSON, read the artifact first and build on it rather than starting from the bundled copy. Scene JSON loads through the studio's Load button.

## What she does herself

She records voiceover and footage, then arranges, retimes and exports inside the studio (timeline, sticky timing, copy/paste, fonts, colours, image drops, MP4/WebM export). Don't rebuild those; if she asks for a new editor feature, change the asset file too, so future videos get it.
