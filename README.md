```
██████╗ ███╗   ███╗
██╔══██╗████╗ ████║   BLACK MIRROR BOARD
██████╔╝██╔████╔██║   ─────────────────────────────────────────
██╔══██╗██║╚██╔╝██║   draw to build
██████╔╝██║ ╚═╝ ██║   v0.9.6 · 99letters studio · 2026
╚═════╝ ╚═╝     ╚═╝
```

![stack](https://img.shields.io/badge/stack-vanilla_JS-000000?style=flat-square)
![deps](https://img.shields.io/badge/deps-zero-000000?style=flat-square)
![canvas](https://img.shields.io/badge/canvas-HTML5-000000?style=flat-square)
![license](https://img.shields.io/badge/license-MIT-000000?style=flat-square)
![platform](https://img.shields.io/badge/platform-web%20%7C%20mobile-000000?style=flat-square)

---

**For designers who dream in code.**  
A visual-to-terminal synthesis engine.  
Draw a shape. Watch the terminal respond. Ship nothing — feel everything.

---

## philosophy

**Intuition over syntax.**  
You draw. The machine translates. No keyboard required to feel like an engineer.

**Subtractive design.**  
One file. Zero dependencies. Zero build steps. If it doesn't need to exist, it doesn't.

**George Hotz energy.**  
The terminal moves at the speed of thought. Your hand replaces his keyboard.

---

## shape → command

```
○  circle      git init / npm create / python -m http.server
◎  double      docker run / kubectl apply -f
△  triangle    git checkout -b / if [ condition ]
□  square      docker build / terraform plan
→  arrow       curl | jq / grep | sort | uniq
T  text        stdin echo / raw injection
✎  pen         free path — close loop to fill like a shape
🖼  image       place any photo or asset directly on the board
```

---

## features

```
PATH EDITING     select any object → drag ○ vertex anchors to reshape
                 drag □ bbox anchors (8-point) to scale freely
                 rotation ring above the bbox — Illustrator feel
                 every shape (circle / triangle / square / arrow / pen)
                 supports both per-vertex edit AND bbox scale at once

PEN → PATH       freehand strokes are auto-simplified on lift via
                 Douglas–Peucker → anchor count stays editable (≤12)
                 dense pts kept internally for curve smoothness
                 tap a stroke → ○ vertex dots + □ bbox handles appear
                 tap a vertex dot → drag that point only
                 tap the line body → drag the whole stroke

PEN CLOSE        draw a pen path back near its start point →
                 blue snap ring appears → release to auto-close
                 closed paths support fill color like any shape

FILL + LINE      fill: none / black / grey / white
                 line: on / off (red-slash icon removes outline)
                 apply before drawing or change on selected object

BLACK MIRROR     every draw action fires real terminal output
SYNC             typewriter queue · syntax highlighting · ambient daemon

IMAGE UPLOAD     toolbar 🖼 button → pick any image file
                 auto-scaled to fit view · move · resize · rotate
                 exported in PNG · saved in JSON

TRANSPARENT      select objects → press X
PNG EXPORT       tight-cropped · transparent bg · Retina-ready

UNDO / REDO      Ctrl+Z / Ctrl+Y · 60-state snapshot history

PAN + ZOOM       Space+drag · pinch · scroll · double-tap resets

PANEL RESIZE     drag the divider bar between canvas and terminal
                 desktop: horizontal  mobile: vertical
                 mobile input row is pinned to the viewport bottom —
                 resizing the split never hides the prompt

MOBILE ANCHORS   vertex / bbox handles scale up on touch (≈1.7×)
                 active anchor shows a halo so the finger doesn't
                 occlude it · tighter vertex hit-radius leaves room
                 on the line body for whole-object drag
                 stroke body hit-zone grows to ≈28 px on touch

PERSISTENCE      SAVE ↓ / OPEN ↑ · full JSON snapshot
                 images stored as base64 · no cloud · no auth

DARK MODE        type "dark mode" in terminal → canvas inverts to void
                 type "light mode" → surface restored
                 scan animation + glitch transition
                 export PNG respects current mode — white lines on transparent

FEEDBACK         tap the logo → modal → mail to studio
```

---

## usage

```sh
# no install. open directly.
open projects/black_mirror/app.html

# or serve locally
python -m http.server 8000
# → localhost:8000/projects/black_mirror/app.html
```

```
keyboard
────────────────────────────────────
S          select tool
P          pen  (tap for width)
C          circle
G          triangle
Q          square
A          arrow
T          text
I          upload image
X          export transparent PNG
1 2 3      line width
Space      pan mode (hold)
Del        delete selected
Ctrl+Z     undo
Ctrl+Y     redo
Esc        deselect / cancel
```

---

## terminal

```sh
> help            show command reference
> clear           flush terminal output
> dark mode       embrace the void
> light mode      return to surface
> youtube         —
> yt              ——
```

> Type `dark mode` to embrace the void.  
> Type `youtube`. Something else happens.

---

## deploy

GitHub Pages. No build. No CI. No config.

```
99letters.github.io/projects/black_mirror/app.html
```

Push. Done.

---

## stack

```
rendering     HTML5 Canvas · ctx.setTransform · devicePixelRatio
input         Pointer Events API · setPointerCapture · Map<pointerId>
shapes        bounding box + angle analysis · bezier smoothing
path edit     RDP simplification on pen lift · evenly sampled anchors
              per-vertex drag + proportional 8-handle bbox scale
pen close     distance-to-origin threshold · snap ring indicator
image         FileReader → base64 · HTMLImageElement cache · drawImage
terminal      async typewriter queue · RAF-synced · syntax highlight
persistence   JSON.stringify(S.objects) · File API · no server
audio         Web Audio API · oscillator · mechanical key feel
export        OffscreenCanvas · toDataURL('image/png') · anchor link
mobile        touch-action: manipulation · gesturestart blocked
              vertical panel resize · fat-finger hit multiplier ×2.2
              terminal input row: position:fixed bottom:0 +
              safe-area-inset-bottom · glitch transform disabled
              (transformed ancestor would trap the fixed child)
```

---

## files

```
black_mirror/
├── app.html        ← the entire engine. one file.
├── logo.png        ← studio mark
├── README.md       ← you are here
├── overview.html   ← team persona viewer
├── usage.md        ← interaction guide
├── ux.md           ← ux research perspective
├── designer.md     ← design perspective
└── marketer.md     ← market perspective
```

---

## contact

```
feedback  →  kinoshita.studio@gmail.com
             subject: Black Mirror Feedback
             (tap the logo in-app to open the form)

instagram →  @tkinoshita99
             instagram.com/tkinoshita99/
```

---

*Draw to Build. — 99letters / 2026*
