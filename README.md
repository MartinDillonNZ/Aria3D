Aria3D Demo Engine v8

A browser-based prototype that turns a simple 3D scene into layered, spatialised music in real time. Built with Three.js for visuals and Tone.js for audio, it explores how you might navigate by sound—hearing objects, height, distance, terrain, weather, hazards, and even your own movement tempo.

Headphones recommended.

What it does

Objects sing: Each object has its own instrument/voice. Height maps to octave, left/right to stereo, and distance to volume. Occlusion and elevation filters help the cues feel natural.

32-bar scene score: A 32-bar loop assigns note sets per bar; visible objects play sparse patterns that adapt to density so the mix stays intelligible.

Proximity percussion: Come near an object and you’ll hear a tom pattern; make contact and you get short burst rolls. Different objects use different tom pitches.

Terrain & edges: Standing on road/path/natural/water layers adds complementary percussion (snare/rim/shaker/sustain). Approaching walls produces directional hi-hat ticks; ramps emit bongo (incline) or conga (decline) taps.

Hazard warnings: A “drop” (hole) emits a crash-style cue that speeds up and positions itself ahead of you as you face it.

Weather & sky: Clear/wind/rain/storm ambience runs through a dynamic low-pass whose brightness follows your elevation; day/night and clouds add very soft melodic phrases (sun/clouds) on select bars.

Movement tempo: Walk vs run changes the kick pattern so the scene “paces” with you.

Controls

Start/Stop audio: Click Start Audio (browsers require a gesture). Optional Mouse Look (then click canvas to lock pointer).

Move: W A S D (Shift to run). Turn with ← →.

Weather: 1 Clear, 2 Wind, 3 Rain, 4 Storm.

Sky items: 5 Day/Night toggle (Sun), 6 Clouds on/off.

Panels / HUD

Left panel: Position, rotation, 32-bar counter, estimated speed (m/min), proximity list.

Bottom band: Which objects are in your field of view (🟢), which are near (🟡).

Right HUD: Bar number, movement mode (STOP/WALK/RUN), FOV count, FPS.

Sky box: Weather, current surface, time of day, cloud state.

Sound mapping (cheat-sheet)

Objects: 3D panners + per-category synths; octaves chosen from on-screen vertical extent; gentle occlusion/elevation filtering; proximity toms (patterns A–D) and contact rolls.

Terrain:

Road = snare anchor (beats 1 & 3)

Path = rim double-strike

Natural = shaker on beat 2

Water = sustained noise on beat 2

Edge = fast hi-hats near walls (heading-aware)

Ramp = bongo (up) / conga (down) taps while traversing

Drop = crash escalates as you approach & face it

Weather/Sky: Clear/Wind/Rain/Storm noise bed with crossfades + filter; Sun/Clouds play sparse, very quiet motifs on specific bars; Night disables sun motif.

Tempo: Walking vs running changes the kick rate.

Tech

Three.js r128, Tone.js 14.8, WebAudio 3D Panner, Pointer Lock API, rAF loop. All client-side.

Getting started

Clone the repo and serve it locally (avoid file:// CORS issues):

# macOS/Linux
python3 -m http.server 8080
# Windows
py -m http.server 8080


Open http://localhost:8080 and click Start Audio.

Use the controls above; wear headphones for clear spatial cues.

Notes / limitations

Prototype mix is intentionally conservative to reduce fatigue; try holding Shift to hear the faster kick mapping.

Desktop Chromium browsers recommended; mobile not tested.

No backend; everything runs in the browser.

Roadmap ideas

HRTF convolution & personalization, improved occlusion/obstacle logic, revived “guide” tool, larger streamed scenes, screen-reader callouts, saveable scenes.

License

MIT (or your preferred license). Credits to Three.js and Tone.js.
