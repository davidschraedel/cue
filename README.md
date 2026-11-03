# Cue

A random prompt generator for improvised music, inspired by contemporary dance rehearsal settings. It imitates an instructor calling out instructions to an accompanist.

Each press of **New prompt** randomizes:

- **Tempo**, as a BPM plus a feel descriptor (and occasional half-time / double-time feels)
- **Meter**, including odd meters and groupings (e.g., 7 grouped as 2-2-3), or free time
- **Phrasing**, meter-aware phrase architecture in bars, counts, or breath cycles (e.g., 4 + 4 bars in odd meters, 8 + 8 counts in 4/4, open breath phrases in free time) with entrance and resolution cues
- **Style**, character or genre descriptors, including occasional hybrid pairings
- **Quality**, contemporary dance movement qualities the music should evoke
- **Texture**, density and register focus
- **Energy**, from 1 to 10 mapped to qualitative energy tiers (*hushed*, *moderate*, *driving*, *explosive*) with dynamic movement arcs
- **Sound source**, single instruments or layered pairings (from hand drums to prepared piano to modular synths and found objects)
- **Tonal color**, harmonic palettes from modal and drone to atonal and pentatonic
- **Sentence**, a natural spoken-style callout synthesising all parameters into rehearsal-ready speech

---

## Features & Controls

- **Spoken Callout Grammar**: The cue is rendered as a natural, conversational sentence (e.g., *"Can you give us something in 7, grouped 2-2-3, around 84, slow and heavy…"*) using a client-side template grammar without requiring AI, APIs, or internet connectivity.
- **Dynamic Seasonal Vocabulary**: Automatically injects evocative, seasonally themed vocabulary based on the current calendar month (Spring, Summer, Fall, Winter) into styles, movement qualities, textures, sounds, harmonic palettes, energy arcs, and tempo feels. You can also manually force or test any season using the `?season=` query parameter (e.g., `?season=fall` or `?season=winter`).
- **Independent Lock & Reroll**: Lock any individual parameter (including the Sentence phrasing style) using the shackle icons, or reroll specific parameters one-by-one without altering the rest of your cue.
- **Meter-Aware Phrasing Coupling**: Phrasing structures and cues automatically adapt to the rolled meter (duple counts, triple/waltz groupings, odd-meter cross-phrasing, or unmeasured breath cycles). When **Meter** is rerolled individually while Phrasing is unlocked, Phrasing automatically cascades and updates to maintain musical consistency.
- **Sentence Framing Control**: The **Sentence** row can be locked or rerolled independently across six templates — *narrative*, *direct*, *conversational*, *shorthand*, *atmospheric*, and *instructional* — with varied openings (*"Can you give us"*, *"Let's have"*, *"Try"*, *"I'm looking for"*, *"How about"*, *"Let's go with"*), while direct and shorthand styles intentionally omit the opener (indicated by `—` in the control).
- **Tempo- & Energy-Synced Pulse**: An ambient visual pulse beats in exact synchronization with the generated BPM and scales its glow intensity with the energy rating:
  - In **Dark mode**, an ambient radial backdrop glow and parameter card borders pulse with the tempo.
  - In **Light mode**, the prompt card and parameter containers produce a luminous rhythmic box-shadow pulse.
  - A real-time tempo indicator dot in the header pulses along with the beat.
  - The pulse effect can be toggled on or off anytime via the **Pulse** button.
- **Responsive Studio Layout**
- **Custom Accent Color with Perceptual Luminance Tuning**: An interactive color picker in the header dynamically shifts the interface accent, text highlight, and ambient glow colors. Dark mode employs perceptual hue luminance correction (`getHueLuminance`) to keep bright colors (like yellows or cyans) well-balanced without washing out the display. Custom color choices are preserved independently per theme.
- **Light / Dark Theme Toggle**: A sun/moon button in the header switches between light and dark modes. The selected theme persists across sessions via `localStorage` and respects your operating system preference by default.
- **Sticky Glassmorphic Header**: The navigation header remains pinned during scrolling with a frosted glass backdrop filter (`backdrop-filter: blur(16px)`), elevating with subtle shadows and border contrast when scrolled past the page top.
- **Keyboard Shortcuts & Accessibility**:
  - Press the **Space bar** from anywhere on the page to instantly roll a new prompt (safely ignored when input controls are focused).
  - Smooth swap micro-animations (`animation: swap`) visually indicate which parameters updated during rolls or rerolls.
  - Full screen-reader support with `aria-live="polite"` on the spoken prompt, semantic button roles, and `aria-pressed` states on locks.
  - Respects system `prefers-reduced-motion` settings, automatically disabling pulse animations and transitions for sensitive users.
- **Logo Reset**: Clicking the **Cue** wordmark in the header navigates back to the root route, resetting prompt state for a fresh rehearsal session.

---

## Running Locally

Cue is a zero-build static web application that uses modern ES modules. Serve it with any local web server:

```bash
# Using Python
python3 -m http.server 8000

# Or using Node / npx
npx serve .
```

Open `http://localhost:8000` (or the URL provided by your server) in your browser. You can also use the **Live Server** extension in VS Code.

### Testing Seasonal Vocabulary

To preview or test seasonal vocabulary sets, append the `season` query parameter to your local URL:

- Spring: `http://localhost:8000/?season=spring`
- Summer: `http://localhost:8000/?season=summer`
- Fall: `http://localhost:8000/?season=fall`
- Winter: `http://localhost:8000/?season=winter`