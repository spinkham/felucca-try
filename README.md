# Felucca emulator with MIDI knob control (unofficial build)

Live: https://spinkham.github.io/felucca-try/

[Felucca](https://github.com/hugelton/Felucca) (by Leo Kuroshita, Hügelton Instruments) running in the
browser, the same page as the [official emulator](https://hugelton.github.io/Felucca/webapp/try/) plus one
addition: a MIDI controller's knobs turn the panel's knobs.

| CC | Panel knob |
|---|---|
| 20 | SELECT |
| 21 | ALGORITHM |
| 22 | PRESETS |
| 23–26 | KNOB 1–4 |
| 27 | MASTER (volume) |

Any MIDI channel. The panel knob follows how far your controller's knob moves (one detent per step), so
nothing jumps on first touch; set endless encoders to absolute mode. Every other message (notes, bend, the
firmware's own CC map) goes to the firmware as before. Use Chrome or Edge, press **Switch on**, allow MIDI.

`felucca.wasm` is the official v1.1.5.1 build, unchanged (from hugelton/Felucca's gh-pages). Source for the
page changes: [spinkham/Felucca, branch emu-midi-knobs](https://github.com/spinkham/Felucca/tree/emu-midi-knobs).
GPL-3.0 (see LICENSE); the DotGothic16 font is SIL OFL 1.1 (fonts/OFL.txt).
