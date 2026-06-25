# The Dream Team

A pixel-art animation synced to music through a custom browser-based analysis tool.

**Case study:** `<add GitHub Pages URL>`
**Studio David Preli** — [davidpreli.com](https://davidpreli.com)

---

## The piece

Never speaking, two unfinished figures find one another.

The music is *the Dream Team* by Fievel Is Glauque, a Brussels and New York duo (pianist Zach Phillips, vocalist Ma Clément), from their 2021 debut *God's Trashmen Sent to Right the Mess*, recorded live to mono.

The two figures come from the Scan the World archive on MyMiniFactory, and their pairing is deliberate:

- **Rongo** — a heavy wooden figure from Mangareva in the Gambier Islands, thought to represent the god of agriculture, rain, and the breadfruit harvest. An abstraction given weight and limbs.
- **A female figure** after Alexander Burganov, built from body fragments by design. Incomplete is the point.

The song lyric puts it plainly: *doubling all partial so completely*. The visual language wrapping the figures is borrowed from Nathalie Du Pasquier's *Manifesto* series, translated into figure studies and texture compositions.

## Three pipelines, one composition

The animation was built across three parallel workflows that converged in a final After Effects composition.

**1. Figures.** STL files from Scan the World were geometry-prepped in Blender for Mixamo auto-rigging. Dance animations were applied and exported as FBX, chosen for universality and carelessness of movement.

**2. Audio.** The track was analysed by a custom tool ([Audio Cue Mapper](#audio-cue-mapper)) for onset events, structural sections, and tempo. Results exported as a JSX script that placed five marker layers into the AE composition.

**3. Compositing.** The Blender footage was keyed with the Extract effect, and the resulting mattes masked artwork layers beneath. Artwork layers were 200×200 px precompositions tiled across the full 2000×2500 frame. Inside each, large *Manifesto*-derived texture precomps were placed by a randomisation script synced to a slider control, with pixel sorting applied to break up monotonous regions.

## Cognitive load as compositional material

The piece is dense, and that is a choice.

When both figures are in frame, the texture count doubles: two visual languages in one space, more motion, more information per pixel. The background distortion grows stronger as the song goes on. What gives is the music. When the alto saxophone solo opens the track, the composition mellows, and the figures might pop off screen entirely on a cue.

The logic is borrowed from Frank Lloyd Wright's compression-and-release: a low entry ceiling, then the living room opens, the body registering the transition before the mind names it. Here the song tells the eye what to expect a fraction before the eye sees it. The viewer does not need to notice this for it to work.

The figures never speak to the audience. The only sound is the song. In a piece about incompleteness and finding a partner, they make their case entirely through movement.

## Audio Cue Mapper

The Cue Mapper was built because no existing tool produced the right output for this workflow. BeatEdit and similar AE plugins handle grid-locked music well; Fievel Is Glauque's recordings are live, loose, and resist a fixed grid.

It runs entirely in the browser: no server, no upload, no dependencies. The Web Audio API decodes the file, spectral flux onset detection with a hand-written FFT finds the hits, the track is segmented by RMS valleys, tempo is estimated by autocorrelation, and the results export as a JSX script that builds five marker layers in After Effects.

→ Full technical writeup: [Audio Cue Mapper repo](<add repo URL>)

## Tech stack

| Layer | Detail |
|-------|--------|
| 3D / rigging | Blender, Mixamo, Scan the World STL archive |
| Audio analysis | Audio Cue Mapper (Web Audio API, vanilla JS) |
| Composite | After Effects (Extract keying, tiled precomps, pixel sorting) |
| Page runtime | Static single-file HTML |
| Hosting | GitHub Pages |
| Embedding | Cargo 3 iframe with a `postMessage` resize bridge |
| Fonts | IBM Plex Mono + DM Serif Display |

## Repo contents

This repository hosts the case study page (a self-contained HTML file). The analysis tool that drove the sync lives in its own repo.

## Credits

- **Music:** Fievel Is Glauque — *the Dream Team*, from *God's Trashmen Sent to Right the Mess* (2021)
- **Figures:** Scan the World archive (MyMiniFactory) — a Rongo figure (Mangareva) and a figure after Alexander Burganov
- **Visual language:** after Nathalie Du Pasquier's *Manifesto* series

---

Studio David Preli — [davidpreli.com](https://davidpreli.com)
