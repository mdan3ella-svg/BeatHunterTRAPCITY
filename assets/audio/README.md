# Audio DLC — how to add real trap samples

The game **ships fully playable with a built-in procedural WebAudio trap synth** — no
audio files required. This folder lets you *upgrade* any layer to a real sample.

## Add a stem
1. Get a **royalty-free / CC0** trap one-shot (`.mp3`, short — a single kick, an 808 note, a hat, etc).
2. Drop it into `stems/` using the filename listed in `manifest.json`
   (e.g. `stems/kick.mp3`, `stems/808.mp3`, `stems/vox.mp3`).
3. Commit + push. On next load the game fetches `manifest.json`, decodes any stems it finds,
   and shows `DLC LOADED: n stems`. Layers with a real sample show **DLC** in the HUD.
4. Anything missing silently uses the synth. Partial packs are fine.

## Pitch
Melodic layers (`808`, `sub`, `lead`, `pad`, `vox`) are pitch-shifted per sequencer step,
so provide the **root note** sample and the engine transposes it via `playbackRate`.

## Where to get CC0 / royalty-free trap sounds
- **Freesound.org** — filter by CC0 license (kicks, 808s, hats, vox chops, risers).
- **freepats.zenvoid.org**, **Sonatina / VSCO CE** style CC0 packs.
- Any pack you have the rights to distribute. Do **not** commit copyrighted samples to a public repo.

## Layer → file map
| Layer | file |
|---|---|
| KICK | stems/kick.mp3 |
| HI-HATS | stems/hat.mp3 |
| SNARES | stems/snare.mp3 |
| OPEN HAT | stems/openhat.mp3 |
| PERC | stems/perc.mp3 |
| 808 BASS | stems/808.mp3 |
| SUB | stems/sub.mp3 |
| PADS | stems/pad.mp3 |
| LEAD | stems/lead.mp3 |
| VOX | stems/vox.mp3 |
| FX | stems/fx.mp3 |
