# TRAP CITY // THE BEAT HUNTER + DAW

**Every step makes the beat.** A single-file HTML5 side-scroller by **Vertascan** where you don't
just play music — you *build* an original trap instrumental by hunting Sound Capsules across five
neon districts, then produce and export it in the built-in DAW. Cross of *Shadow Protocol* platforming
and *FL Studio*, wrapped in cyberpunk TrapCity.

## Play
Open `index.html` — that's it. For audio DLC + background images to load, serve it over http
(GitHub Pages, or `python3 -m http.server` locally) rather than `file://`.

## Controls
| Action | Keys | Touch |
|---|---|---|
| Move | ◄ ► or A / D | left stick |
| Jump | SPACE / W / ↑ | JUMP button |
| Dash (damages boss) | SHIFT | — |
| DAW / Mixer | TAB | — |
| Play / stop beat | R | — |

## The loop
Explore → collect **Sound Capsules** → each capsule instantly adds a **track layer** to a beat that
loops live as you run → reach the studio door → clear the district → repeat. Final level is
**MajorStack Tower**: dash into the **Silence Engine** to defeat it, then **PRODUCE THE DROP** in the DAW.

## Levels → backgrounds
| # | District | Backdrop | Layers granted |
|---|---|---|---|
| 1 | The Block | `01_the_block.webp` | KICK, HI-HATS |
| 2 | Underground Studio | `02_underground.webp` | SNARE, OPEN HAT, PERC |
| 3 | Skyline / Tour Bus | `03_tour_bus.webp` | 808, SUB |
| 4 | Trap Mansion Vault | `04_vault.webp` | PADS, LEAD |
| 5 | MajorStack Tower (boss) | `05_tower.webp` | VOX, FX |

`keyart.png` is used as reference art. Backdrops render with **parallax depth-of-field** (blurred far
layer + sharp mid), neon dust particles, beat-synced pulse rings, camera FOV zoom, and screen shake.

## Audio
- **Procedural WebAudio trap engine** built in — kick, 808 glide bass, sub, hats, snare/clap, perc,
  pads, lead, vox chop, FX riser. No files needed.
- **Optional .mp3 DLC:** drop royalty-free stems into `assets/audio/stems/` (see
  `assets/audio/README.md`). Present layers show **DLC** in the HUD; missing ones fall back to synth.
- **Beatpad:** the DAW screen has a 12-pad DJ-style beatpad for looped `.mp3` samples. Import mp3s
  live during a session, or drop them into `assets/audio/loops/` + list them in
  `assets/audio/loops/manifest.json` to have them auto-load on every visit (see
  `assets/audio/loops/README.md`).
- **The DAW never autoplays** — entering the studio leaves everything stopped; press **PLAY** to start it.
- **Export:** the DAW renders the loop offline and downloads a **.WAV** of your beat.

## Deploy to GitHub Pages
```bash
git init && git add . && git commit -m "TRAP CITY // Beat Hunter"
git branch -M main
git remote add origin https://github.com/mdan3ella-svg/TRAPCITY-BEAT-HUNTER.git
git push -u origin main
# Settings → Pages → deploy from main / root
# live at https://mdan3ella-svg.github.io/TRAPCITY-BEAT-HUNTER/
```

## Structure
```
TRAPCITY-BEAT-HUNTER/
├── index.html                 # the whole game
├── README.md
└── assets/
    ├── backgrounds/           # level backdrops (webp) + keyart.png
    └── audio/
        ├── manifest.json      # DLC wiring
        ├── README.md          # how to add royalty-free mp3s
        └── stems/             # drop your .mp3 one-shots here
```

© Vertascan. Built as a self-contained HTML5 deliverable.
