# Cue

A random prompt generator for improvised music, inspired by contemporary dance rehearsal settings. It imitates an instructor calling out instructions to an accompanist.

Each press of **New prompt** randomizes:

- **Tempo**, as a BPM plus a feel descriptor (and occasional half-time / double-time feels)
- **Meter**, including odd meters and groupings (e.g., 7 grouped as 2-2-3), or free time
- **Phrasing**, count structures (e.g., 8, 4 + 4 + 8, 5 + 3) with entrance and resolution cues
- **Style**, character or genre descriptors, including hybrid pairings
- **Quality**, contemporary dance movement qualities the music should evoke
- **Texture**, density and register focus
- **Energy**, from 1 to 10 with an energy arc
- **Sound source**, from hand drums to prepared piano to modular synths and found objects
- **Tonal color**, harmonic palettes from modal and drone to atonal and pentatonic
- **Sentence**, a more natural spoken-style callout synthesising all parameters

---

## Features & Controls

- **Spoken Callout Grammar**: The cue is rendered as a natural, conversational sentence (e.g., *"Give me something in 7, grouped 2-2-3, around 84, slow and heavy…"*) using a client-side template grammar without requiring AI, APIs, or internet connectivity.
- **Independent Lock & Reroll**: Lock any individual parameter (including the Sentence phrasing style) using the shackle icons, or reroll specific parameters one-by-one without altering the rest of your cue.
- **Sentence Framing Control**: The **Sentence** row can be locked or rerolled independently across four templates — narrative, direct, conversational, and shorthand — with varied openings (*"Give me"*, *"Let's have"*, *"Try"*, *"I'd like"*, *"Take"*).
- **Tempo-Synced Pulse**: An ambient background glow pulses in sync with the generated tempo and scales its brightness with the rolled energy level. Toggle this on or off anytime via the **Pulse** button.
- **Custom Accent Color**: An interactive color picker in the header dynamically shifts the interface accent, text highlight, and ambient glow colors. Custom colors are saved per theme (separate choices for light and dark mode).
- **Light / Dark Theme Toggle**: A sun/moon button in the header switches between light and dark modes. The selected theme persists across sessions via localStorage and also respects your system preference by default.
- **Keyboard Shortcut**: Press the **Space bar** to generate a new prompt (does not fire when an input control is focused).
- **Logo Reset**: Clicking the **Cue** wordmark in the header returns to the home/root route.

---

## Running Locally

Cue is a self-contained static web application with no build steps or dependencies:

1. Open `index.html` in your browser.
2. Press **New prompt** or the **Space bar** to generate cues.