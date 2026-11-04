# Tesseract pieces

Small browser toys built around a tesseract (a 4D hypercube). No build step, no dependencies beyond two Google Fonts. Open either file in any modern browser.

- `index.html` is Tesseract Drift, a generative art and ambient sound toy.
- `anatomy.html` is Tesseract Anatomy, a cross-section and unfolding explorer.

## Tesseract Drift

### What it does

- A tesseract rotates through the xw, yw and zw planes and is projected 4D → 3D → 2D. Edges are colored by their position along the fourth axis: warm when they come toward you in w, cool when they recede.
- A simplex-noise flow field drives thousands of particles. Near the hypercube they are pulled along its edges, so the trails trace the shape as it turns inside out.
- Your pointer stirs the field as a vortex. Dragging rotates the projection.
- With sound on, a filtered sawtooth drone plays under four sine partials whose pitches follow the w coordinate of four vertices, so the chord shifts with the 4D rotation. Pointer x sets the filter cutoff, pointer y the reverb, and moving the pointer plucks pentatonic notes picked by the angle around the center. The waveform is drawn as a ring around the hypercube.

### Controls

Rotation speeds per 4D plane, 3D drift, w depth (the 4D perspective distance), zoom, turbulence, edge pull, particle count, trail length, four palettes, a reseed button, a snapshot button that freezes the frame as an image you can save, and volume and root note for the synth.

## Tesseract Anatomy

- **Slice.** A 3D hyperplane at w = h cuts the rotated tesseract. Each of the eight cubic cells meets the hyperplane in a convex polygon, and those polygons are the faces of the cross-section. Sweep h or drift the xw, yw and zw angles to morph the solid. The readout gives its vertex, edge and face counts and which cells it passes through. A faint shadow of the whole tesseract shows the cut, warm above the plane and cool below.
- **Unfold.** The eight cells laid out as the familiar cross-shaped net, hinged in 4D. The fold slider turns every hinge from flat to closed, and the net passes through the fourth axis on its way to becoming a tesseract again. Cells keep the same colors in both modes, so a face in the slice is recognisably a cut through that cell.

## Direction - "this is it" (Jaron, 11/4/2026 4:20 PM)

The tesseract was the principle, not the product. What it is for:

- **Pages live on a turning tesseract.** Its 8 cells are 8 pages (rooms, sites, tools).
- **Ground zero.** One fixed spot. Whichever cell is passing through it is the active page (its URL, its content), until the turn moves it on.
- **The Seam Room, inverted.** In the Seam Room the pages stay still and you walk to them. Here you stay at ground zero and the pages turn to you. Same rule, "where you are picks the page", with the other side moving.
- **Who turns it.** The user (swipe/grab), the tesseract's own rhythm (a clock, a news cycle), or both: it drifts and you can grab it. Fast = glimpses, slow = you live in one page.
- **The fold between pages.** Like the Dr Strange folding buildings. As one cell leaves ground zero and the next arrives, the two rooms fold into each other. Anatomy's hyperplane slice already computes those in-between shapes; it can become the transition.
- Metaverse feel. Same family as the Seam Room (lab/seam-room on the site), whose rooms (studio, creature room, kitchen...) can be the first 8 cells.

The first sketch Claude showed him is a turning tesseract with 8 labelled cells, where the cell nearest ground zero lights up and names the active page. It also shows how long each page was held.
