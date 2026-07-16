# Beatpad Loops — how they work

The DAW screen's **BEATPAD // LOOPS** panel holds up to 12 pads. Each pad plays
a looping `.mp3` sample through the same master FX chain (filter/drive/comp/
reverb/delay) as the rest of the beat.

## Import during a session
Click an empty pad (or **+ IMPORT MP3**) and pick one or more `.mp3` files.
They decode instantly and play right away — no server needed. This is
session-only: reloading the page clears them.

## Make a loop persist (GitHub Pages / future sessions)
1. Drop the `.mp3` file into this folder (`assets/audio/loops/`).
2. Add it to `manifest.json`'s `"loops"` array, e.g.:
   ```json
   "loops": [
     "vocal_chop.mp3",
     { "file": "hihat_roll.mp3", "name": "Hi-Hat Roll" }
   ]
   ```
   A plain string uses the filename (minus `.mp3`) as the pad label; the
   `{file, name}` form lets you give it a custom label.
3. Commit + push. On next load, the game fetches this manifest and decodes
   every listed file straight onto the pads (`pad0`, `pad1`, ... in list order).

## Where to get CC0 / royalty-free loops
- **Freesound.org** — filter by CC0 license (drum loops, vocal chops, risers).
- Any pack you personally have distribution rights to.
- Do **not** commit copyrighted loops to a public repo.
