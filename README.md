# Cue

A random prompt generator for improvised music in a contemporary dance setting. It works like a teacher calling out instructions to an accompanist, but you press a button instead.

Each press of **New prompt** randomizes:

- **Tempo**, as a BPM plus a feel word
- **Meter**, including odd meters and groupings (e.g. 7 as 2-2-3), or free time
- **Phrasing**, meaning count structures like 8, 4 + 4 + 8, or 5 + 3, plus how to enter and end
- **Style**, a character or genre word, sometimes a hybrid
- **Quality**, the movement quality the music should evoke
- **Texture** and register
- **Energy**, from 1 to 10 with an arc
- **Sound source**, from hand drums to synths to found objects
- **Tonal color**

The results are also written out as a spoken-style sentence, such as "Give me something in 7, grouped 2-2-3, around 84, suspended and sparse...". It's built from a template grammar in the browser, so it needs no AI or API and has no cost.

**Lock** any parameter you like and reroll the rest, or reroll one parameter at a time. The background glow pulses at the rolled tempo and brightens with the energy level (you can turn that off).

## Running it

It's a single static HTML file. Open `cue.html` in a browser. Press the button or the space bar to receive a cue.