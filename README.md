<img alt="zygnul-logo" src="./assets/images/logo.png" style="margin-left:auto; margin-right:auto; display:block; width:200px;"/>

# Zygnul

**Zygnul** is a lightweight, browser-based glitch text generator for static and animated typography. It composes Zalgo marks and other transforms with styling effects to create expressive, chaotic text—then exports images or animations—all locally in your browser.

<!-- Uncomment and update if hosted -->
[**View Live Demo**](https://nqrlabs.com/Zygnul/)

## Overview

Zygnul synthesizes glitch typography using Unicode combining marks, character substitutions, and reversible text transforms.  
You can dial in intensity and distribution, paint glitches directly onto characters, and layer visual effects such as gradients, shadows, and glow.

Every step runs client-side with no uploads or network activity.  
All processing uses browser-native Canvas and Media APIs, ensuring full privacy and reproducibility.

## Features

- **Glitch engines:** Zalgo (up/mid/down marks), leet substitutions, mirror and upside-down transforms, plus optional math, Greek, and Arabic sets.  
- **Direct manipulation:** “Paint Mode” lets you brush glitches onto specific character positions.  
- **Style controls:** Text gradients, shadow, glow, and rainbow effects with adjustable background (solid/gradient/rainbow/transparent).  
- **Typography:** System fonts with optional custom font upload.  
- **Static output:** Copy the glitched text or export as a PNG image.  
- **Animated output:** Render loop to Canvas with export to **GIF** (via gif.js worker) or **WebM**.  
- **Performance helpers:** Frame caching and debounced updates for responsive interaction.  
- **Offline operation:** Everything runs locally using Canvas and standard Web APIs.

## Technical Notes

### Character Transform Engine
- Combines Unicode marks in configurable **up/mid/down** clusters to produce Zalgo-like corruption.
- Optional character mappers handle **leet**, **mirror**, and **upside-down** variants.
- Intensity and distribution sliders govern frequency and placement of marks.

### Rendering Pipeline
- 2D **Canvas** is used for layout, gradients, and raster export.  
- Background modes include solid, linear gradient, and rainbow cycling.

### Animation
- Frames are drawn to Canvas and cached to keep playback smooth; updates are **debounced** to reduce layout thrash during rapid slider changes.

### Export
- **GIF** generation via **gif.js** + web worker.  
- **WebM** export via **MediaRecorder** where available.  
- Static image export uses Canvas toDataURL/Blob.

## Intended Users

Designed for designers, streamers, ARG creators, and anyone exploring expressive or chaotic typography.  
Great for social posts, title cards, overlays, and experimental branding.

## Usage

1. Open the app in your browser.  
2. Enter your text.  
3. Adjust **Font Size**, **Glitch Intensity**, **Glitch Distribution**, and **Animation Speed**.  
4. Choose **Glitch Types** (Zalgo up/mid/down, leet, mirror, upside-down, math/Greek/Arabic).  
5. Select **Text Effect** (none/gradient/shadow/glow/rainbow) and **Background Effect**.  
6. (Optional) Enable **Paint Mode** and brush glitches over characters.  
7. For static art, click **Copy Text** or **Save Image**.  
8. For animation, click **Save as GIF** or **Save as WebM**.

Everything runs locally—no data leaves your system.

## License

MIT License — free for modification and use. Attribution appreciated if used publicly.

## Third-Party

- **gif.js** (MIT) — bundled locally at `/assets/js/vendor/gif.js` and `/assets/js/vendor/gif.worker.js`. See `THIRD_PARTY_NOTICES.md` for details.

## Credit

Created by **NQR** for glitch typographers, artists, and creative technologists who enjoy bending text past its breaking point.
