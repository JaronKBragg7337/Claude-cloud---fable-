# Tesseract pieces

Small browser toys built around a tesseract (a 4D hypercube). No build step, no dependencies beyond two Google Fonts. Open either file in any modern browser.

- `index.html` is Tesseract Drift, a generative art and ambient sound toy.
- `anatomy.html` is Tesseract Anatomy, a cross-section and unfolding explorer.
- `pages.html` is Tesseract Pages, the outside view: eight rooms on the eight cells of a turning tesseract, seen from outside.
- `inside.html` is Tesseract Inside, the first-person test: you stand inside the tesseract and the rooms turn through you. This is the direction (see the correction below).

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

## Tesseract Pages (first build, 11/4)

- The eight Seam Room rooms (Garage, Media Room, Kitchen, Gym, Hallway, Closet, Music Studio, the Creature's Room) are assigned to the eight cells.
- **Ground zero** is the +w direction, toward the viewer. The cell whose centre is furthest along +w after the 4D rotation is the active page. Its front face carries the page: the room is loaded in an iframe and mapped onto that face with a CSS homography, so the page sits inside the cube and skews with it as it turns. The cube turning is the fold between pages; the leaving page stays on its face for a moment and fades.
- **Who turns it.** Drag the strip at the bottom (or anywhere outside the page): sideways pulls the next room in from the side (xw plane), up or down brings the rooms above and below (yw plane). Let go and it coasts, then settles so the active page sits square in front of you. Or leave it turning on its own: the page is held flat for the chosen seconds, then a quarter turn brings the next one; wander sometimes turns in the yw or zw plane instead so all eight cells get a turn. The arrows step a quarter turn.
- The tilt only shows while turning; at rest the page is flat and fully usable. On wide screens the arriving room is preloaded onto its cell too, so both rooms are visible during the fold. Each room has a deep link: `pages.html#kitchen`, `#music-studio`, `#the-creatures-room` and so on.
- The HUD names the active room, how long it has been held, and which cell is arriving. The dock keeps the time held in each room.
- Inside a claude.ai artifact other sites cannot be framed, so that copy shows a card per room with a link; opened from the repo or from the site, the real rooms show on the faces.

## Tesseract Inside (first-person test, 11/4)

- Your 3D space is the hyperplane w = 0 through the centre of the tesseract. The slice of the tesseract that lies in your space is the room you stand in. Each of its walls is where one cell crosses your space (the same cross-section math as Anatomy), so every wall, the floor and the ceiling is a door into a different cell. At rest the slice is a cube with six walls; while turning it morphs through seven- and eight-sided shapes, and walls slide through you.
- Eight plain rooms, each a solid colour, no website pages. Every wall carries its room's name, its cell label and its distance along w. Rooms far along the fourth direction are see-through (fade by w), and every cell's edges are drawn faintly as a ghost so you can see rooms beyond the walls.
- Ground zero is you. Drag the view to look around. Drag the strip to turn the tesseract: sideways rotates your right wall through w (the hidden room swaps in), up and down does the ceiling and floor. The arrows do a quarter turn; "Through the door ahead" turns the room in front of you into your space. Each room has a chip in the dock: tap it and the tesseract steers until that room's wall is dead ahead and solid. It also turns slowly on its own.
- You can walk a little (WASD or the pad on touch screens), clamped to the ball that every slice contains, but the shifting is the tesseract's.
- On a phone the repo copy offers "use phone tilt to look" (device orientation, needs a tap to allow on iOS).

## Direction - "this is it" (Jaron, 11/4/2026 4:20 PM)

The tesseract was the principle, not the product. What it is for:

- **Pages live on a turning tesseract.** Its 8 cells are 8 pages (rooms, sites, tools).
- **Ground zero.** One fixed spot. Whichever cell is passing through it is the active page (its URL, its content), until the turn moves it on.
- **The Seam Room, inverted.** In the Seam Room the pages stay still and you walk to them. Here you stay at ground zero and the pages turn to you. Same rule, "where you are picks the page", with the other side moving.
- **Who turns it.** The user (swipe/grab), the tesseract's own rhythm (a clock, a news cycle), or both: it drifts and you can grab it. Fast = glimpses, slow = you live in one page.
- **The fold between pages.** Like the Dr Strange folding buildings. As one cell leaves ground zero and the next arrives, the two rooms fold into each other. Anatomy's hyperplane slice already computes those in-between shapes; it can become the transition.
- Metaverse feel. Same family as the Seam Room (lab/seam-room on the site), whose rooms (studio, creature room, kitchen...) can be the first 8 cells.

The first sketch Claude showed him is a turning tesseract with 8 labelled cells, where the cell nearest ground zero lights up and names the active page. It also shows how long each page was held.

### Correction - inside, not outside (Jaron, 11/4 5:18 PM)
- The pages-on-faces build (Tesseract Pages) is close but is the OUTSIDE view. It's like looking at a cube with a page on each side. The real site pages also add noise (settings/overlays) and can't be played in there.
- What he means: **you are INSIDE the tesseract, first person.** The tesseract moves; the player mostly doesn't. You can walk around the room you're in, but the shifting is the tesseract's.
- Picture: a carnival hall of mirrors where every mirror is a door to a different room, angled every way.
- For testing: **basic rooms, different coloured walls, no website pages.** Complex environments come later.
- Geometry that fits: each cube cell touches 6 others through its faces, so in any room all 6 sides (4 walls, floor, ceiling) are doorways into 6 different rooms. Only the opposite cell isn't next to you. Looking through doorways repeats like mirrors. As the 4D rotation runs, the slice of the tesseract you stand in morphs (cube -> other shapes), and rooms slide past you and through you.
- More from Jaron (5:24 PM):
  - Not perfect squares. Shapes morph into "ugly weird things" depending on the slice you're in at that moment.
  - **Fade by 4D distance:** rooms further away in the 4th direction are partly see-through, so you can see through them into other rooms. How faded depends on where each room sits on the tesseract right then.
  - **Every face gets a label/position.** There is a defined ground zero, and the tesseract can be steered to turn a certain way so chosen rooms come forward.
