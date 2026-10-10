# Felucca emulator with MIDI knob control (unofficial build)

Live: https://spinkham.github.io/felucca-try/

[Felucca](https://github.com/hugelton/Felucca) (by Leo Kuroshita, Hügelton Instruments) running in the
browser, the same page as the [official emulator](https://hugelton.github.io/Felucca/webapp/try/) plus one
addition: a MIDI controller's knobs can turn the panel's knobs. It's opt-in: tick **MIDI CC 20–27 turn the
panel's knobs** under the panel.

| CC | Panel knob |
|---|---|
| 20 | SELECT |
| 21 | ALGORITHM |
| 22 | PRESETS |
| 23–26 | KNOB 1–4 |
| 27 | MASTER (volume) |

Any MIDI channel. With the box unticked (the default) every CC goes to the firmware, so a knob learned to
CC 20–27 with MIDI LEARN works as on the device. Ticked, a select sets how your controller sends CC 20–26:

- **absolute** (default): the panel knob follows how far your knob's value moves (one detent per step), so
  nothing jumps on first touch
- **relative 64±n** (Arturia Rel 1, BCR2000 Rel 2)
- **relative two's complement** (BCR2000 Rel 1, Ableton)
- **relative sign bit** (Mackie)

CC 27 (MASTER) is absolute in every mode. Both settings are kept in the browser. Every other message (notes,
bend, the firmware's own CC map) goes to the firmware as before. Use Chrome or Edge, press **Switch on**,
allow MIDI.

`felucca.wasm` is the official v1.5.1 build, unchanged (from hugelton/Felucca's gh-pages). Source for the
page changes: [spinkham/Felucca, branch emu-midi-knobs](https://github.com/spinkham/Felucca/tree/emu-midi-knobs), merged
onto 1.5.1.
GPL-3.0 (see LICENSE); the DotGothic16 font is SIL OFL 1.1 (fonts/OFL.txt).
