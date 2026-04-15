```
██████╗ ███╗   ███╗
██╔══██╗████╗ ████║   BLACK MIRROR BOARD
██████╔╝██╔████╔██║   ─────────────────────────────────────────
██╔══██╗██║╚██╔╝██║   draw to build
██████╔╝██║ ╚═╝ ██║   v0.9 · 99letters studio · 2026
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
```

---

## features

```
PATH EDITING     select any object → drag □ anchors to deform
                 8-point bounding box on all shapes · Illustrator feel

BLACK MIRROR     every draw action fires real terminal output
SYNC             typewriter queue · syntax highlighting · ambient daemon

TRANSPARENT      ○ select objects → press X
PNG EXPORT       → tight-cropped transparent PNG · Retina-ready · instant

UNDO / REDO      Ctrl+Z / Ctrl+Y · 60-state snapshot history

PAN + ZOOM       Space+drag · pinch · scroll · double-tap resets

PERSISTENCE      SAVE ↓ / OPEN ↑ · full JSON snapshot · no cloud · no auth
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
# type into the terminal input to interact directly

> help          show command reference
> clear         flush terminal output
> youtube       —
> yt            ——
```

> Type `youtube`. Something happens.

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
terminal      async typewriter queue · RAF-synced · syntax highlight
persistence   JSON.stringify(S.objects) · File API · no server
audio         Web Audio API · oscillator · mechanical key feel
export        OffscreenCanvas · toDataURL('image/png') · anchor link
```

---

## files

```
black_mirror/
├── app.html        ← the entire engine. one file.
├── logo.png        ← mark
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

instagram →  @tkinoshita99
```

---

*Draw to Build. — 99letters / 2026*
