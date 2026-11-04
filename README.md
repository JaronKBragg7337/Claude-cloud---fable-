# Tesseract Drift

A generative art and ambient sound toy built around a tesseract (a 4D hypercube).

Open `index.html` in any modern browser. No build step, no dependencies beyond two Google Fonts.

## What it does

- A tesseract rotates through the xw, yw and zw planes and is projected 4D → 3D → 2D. Edges are colored by their position along the fourth axis: warm when they come toward you in w, cool when they recede.
- A simplex-noise flow field drives thousands of particles. Near the hypercube they are pulled along its edges, so the trails trace the shape as it turns inside out.
- Your pointer stirs the field as a vortex. Dragging rotates the projection.
- With sound on, a filtered sawtooth drone plays under four sine partials whose pitches follow the w coordinate of four vertices, so the chord shifts with the 4D rotation. Pointer x sets the filter cutoff, pointer y the reverb, and moving the pointer plucks pentatonic notes picked by the angle around the center. The waveform is drawn as a ring around the hypercube.

## Controls

Rotation speeds per 4D plane, 3D drift, w depth (the 4D perspective distance), zoom, turbulence, edge pull, particle count, trail length, four palettes, a reseed button, a snapshot button that freezes the frame as an image you can save, and volume and root note for the synth.
