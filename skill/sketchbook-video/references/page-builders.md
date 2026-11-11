# Writing a page builder

All code lives in the single script of `assets/sketchbook-studio.html`. Find existing builders with `grep -n "function add.*Page" sketchbook-studio.html` and copy the closest one.

## Canvas
1920x1080 logical px, origin top-left. Title around (300, 230) size 150; body text 72 to 90; notes ~60 to 70.

## Element kinds
- `{kind:"text", text, x, y, size, rot:0, color?, font?}`
- `{kind:"wire", pts:[[x,y],...], color?}` orthogonal polyline
- `{kind:"free", pts, color?}` freehand stroke (highlight rings, rects, sparks)
- `{kind:"part", part:"resistor"|"led"|"battery"|"button"|"capacitor"|"pot"|"ground"|"arrow"|"box"|"arduino"|"breadboard"|"breadboardwide", x, y, rot, scale, color?}`
- `{kind:"image", ...}` and `{kind:"break"}` (new page)

Per-item timing: `want: lagSeconds` in builders (becomes `lag`, follows the previous item); negative overlaps it. `dur` overrides draw time; `life`/`until:"next"` removes it later.

## Helpers (defined near the builders)
`placePage(items, toastMessage)` inserts a break + items after the selection or at the end and jumps to it. `R(cx,cy,k)` returns a transform P(x,y) for drawing at scale k around a centre. `rrectPts`, `sparkPts`, `loopArrowPts`, `rectPts`, `filledRect`, `circlePts`, `snake`, `mkFree(pts,color,lag)`, `picArduino`, `picResistor5`, `picLed(cx,cy,k,color)` (realistic kit parts, built from `free` strokes).

## Breadboard holes
For the wide board placed at (620,830) scale 0.85: column i is `BX(i)=620+(-560+40*i)*0.85`, row offset r is `BY(r)=830+r*0.85`. Rail rows are about r=-165 (top) and 165 (bottom); the middle gap is at r=0. Snap wire ends to these so they land in holes.

## Adding the button
```html
<button class="btn" id="myPage" style="width:100%;margin:0 0 8px" title="What it adds">+ My page</button>
```
```js
$("myPage").onclick = addMyPage;
```

## Checklist before publishing
- No console errors after clicking each new button.
- Zoom screenshots on labels and wire ends; text must not overflow cards.
- Non-ASCII characters written as `\u` escapes (arrows, ohm sign), or the page shows mojibake.
- `localStorage.clear()` after testing.
