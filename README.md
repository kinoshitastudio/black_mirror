<div align="center">

```
 ██████╗ ███╗   ███╗
 ██╔══██╗████╗ ████║     BLACK MIRROR BOARD
 ██████╔╝██╔████╔██║     ─────────────────────────────
 ██╔══██╗██║╚██╔╝██║     draw to build
 ██████╔╝██║ ╚═╝ ██║     v1.0 · 99letters studio · 2026
 ╚═════╝ ╚═╝     ╚═╝     release: 2026-04-16
```

![stack](https://img.shields.io/badge/stack-vanilla_JS-000?style=flat-square)
![deps](https://img.shields.io/badge/deps-zero-000?style=flat-square)
![canvas](https://img.shields.io/badge/canvas-HTML5-000?style=flat-square)
![themes](https://img.shields.io/badge/themes-light_%7C_dark_%7C_gray-000?style=flat-square)
![license](https://img.shields.io/badge/license-MIT-000?style=flat-square)

</div>

---

A terminal-driven infinite canvas. One HTML file. No dependencies. No build.
Every draw action speaks back through a live shell. **v1.0 ships 2026-04-16.**

```
open projects/black_mirror/app.html
```

That's the install.

---

## What's new in v1.0

```
GRAY MODE          studio ground #DCDBD5 · cobalt ink #1600A2
                   `gray` in terminal · all fills re-tint on switch

HIT-TEST 2.0       segment-distance picking + 8px invisible pad
                   thin strokes grab like fat ones · hover glow
                   directional cursors (nwse/nesw/ns/ew)

SHIFT RESIZE       corner drag + Shift = aspect-lock
                   Alt = center-pinned symmetric scale
                   Shift+Alt = both · 0.5×/1×/1.5×/2× snap
                   images lock by DEFAULT — Shift to free them

THEMED SELECTION   selection box + marquee recolor per mode
                   cobalt on light · white on dark · white on pebble

ALPHA PNG          selection-aware · tight bbox · 3× DPR cap
                   transparent background for compositing
```

---

## Philosophy

**Intuition over syntax.** Draw a shape. The terminal answers.

**Subtractive.** One file. Zero deps. Zero build. If it doesn't need to exist, it doesn't.

**Local-first.** No cloud. No auth. Ctrl+S is JSON, export is PNG. Your file, your disk.

---

## Shape → command

```
○  circle      git init / npm create / python -m http.server
◎  double      docker run / kubectl apply -f
△  triangle    git checkout -b / if [ condition ]
□  square      docker build / terraform plan
→  arrow       curl | jq / grep | sort | uniq
T  text        stdin echo / raw injection
✎  pen         freehand path — close loop to fill like a shape
🖼  image       drop any photo or asset onto the board
```

---

## Features

```
CANVAS           infinite pan · 0.15× → 8× zoom · Retina-ready
                 pointer events unified across mouse / touch / pen
                 DPR-scaled ctx.setTransform · 60fps redraws

SELECT · MOVE    click body or within 8px of line · drag to move
                 hover glow · cursor: move / nwse-resize / ns-resize
                 marquee: dashed box · intersection-aware

EDIT             8-handle bbox: tl/tm/tr/rm/br/bm/bl/lm
                 per-vertex anchors on pen / triangle / path
                 rotation ring above the bbox (Illustrator feel)
                 Shift: lock aspect · Alt: center-pin · Shift+Alt: both
                 live snap at 0.5× / 1× / 1.5× / 2× scale milestones

PEN → PATH       freehand → RDP simplify on lift (≤ ~12 anchors)
                 dense pts kept internally for smooth curves
                 auto-close: draw back to origin → blue snap ring

FILL + LINE      fill: none / black / grey / white
                 line: on / off (no outline, closed shapes only)
                 all fills re-tint to match active theme

THEMES           light : surface #FAFAF8 · ink #0c0c0c
                 dark  : void    #000000 · ink #F0EDE6
                 gray  : pebble  #DCDBD5 · ink #1600A2
                 swap via terminal: `light` | `dark` | `gray`
                 glitch-flash + scan overlay between modes

IMAGE UPLOAD     toolbar 🖼 · any image file · base64 inline
                 aspect-locked on corners by default (Shift frees)
                 move · resize · rotate · export

TRANSPARENT PNG  select, press X · tight-crop · 3× DPR · alpha bg

PERSISTENCE      SAVE ↓ / OPEN ↑ · full JSON snapshot including
                 canvas objects + terminal log + view transform

UNDO · REDO      Ctrl+Z / Ctrl+Y / Ctrl+Shift+Z · 60-state history

PAN · ZOOM       Space+drag · pinch · scroll-wheel · double-tap reset

TERMINAL         typewriter queue · syntax highlight · ambient daemon
                 commands: dark / light / gray / help / clear / youtube
```

---

## Keyboard

```
S          select          1 2 3      line width
P          pen             Space      pan (hold)
N          path            Shift      lock aspect (while resizing)
E          eraser          Alt        center-pin (while resizing)
C          circle          X          export transparent PNG
G          triangle        I          upload image
Q          square          Del        delete selected
A          arrow           Ctrl+Z     undo
T          text            Ctrl+Y     redo
                           Esc        deselect · cancel
```

---

## Terminal commands

```
> help            command reference
> clear           flush output
> light           surface mode
> dark            void mode
> gray            studio mode (cobalt on pebble)
> youtube         (try it)
```

---

## Quick start

```sh
# no install. open directly:
open projects/black_mirror/app.html

# or serve locally (to enable file:// APIs on strict browsers):
python -m http.server 8000
# → http://localhost:8000/projects/black_mirror/app.html
```

---

## Stack

```
render       HTML5 Canvas · ctx.setTransform · devicePixelRatio
input        Pointer Events · setPointerCapture · multi-touch pinch
geometry     RDP simplification · bezier smoothing · segment-distance
             ray-cast point-in-polygon for closed-fill hit-test
theming      CSS custom properties · body.bm-{light|dark|gray}
             resolveFill() — channel-invert + cobalt retint
resize       single resizeBoxWithMods(anchorId, ob, nx, ny, shift, alt)
             drives both per-object + multi-select group math
persistence  JSON.stringify(S.objects) · FileReader · base64 images
audio        Web Audio API · oscillator · mechanical key feel
export       offscreen canvas · toDataURL('image/png') · alpha preserved
```

---

## Files

```
black_mirror/
├── app.html        ← the entire engine. one file.
├── logo.png        ← studio mark
├── README.md       ← you are here
├── overview.html   ← team persona viewer
├── usage.md        ← interaction guide (v1.0)
├── ux.md           ← UX research perspective
├── designer.md     ← design perspective
└── marketer.md     ← market perspective
```

---

## Deploy

GitHub Pages. No build. No CI. No config.

```
99letters.github.io/projects/black_mirror/app.html
```

Push. Done.

---

## Contact

```
feedback   →  kinoshita.studio@gmail.com
              subject: Black Mirror Feedback
              (tap the logo in-app to open the form)

instagram  →  @tkinoshita99
              instagram.com/tkinoshita99/

dev log    →  /md.html  — full v0.1 → v1.0 retrospective
```

---

<div align="center">

*Draw to Build. — 99letters / 2026-04-16*

</div>
