# HelloHelder: Shoe Poster Studio

Single-file poster tool (`index.html`). A layered, glowing 3D shoe (Three.js) rotates 360 degrees, sits inside an editable poster layout, and exports to PNG/JPG at screen or print resolution (A4/A3 at 300 dpi, with DPI metadata).

- Edit headline, subline, copy position (7 variants), format (landscape, portrait, square), colours
- Pin frames of the rotation and return to them
- Partner logo strip with stand-ins, or upload your own logos
- Load an `.obj` to wrap the glowing layers around another model (beta)

## Analytics

Google Analytics 4 is wired in with measurement ID `G-9YC56MPK6Q`. To change it, edit `window.GA_MEASUREMENT_ID` near the top of `index.html`. Setting it back to the placeholder `G-XXXXXXXXXX` switches analytics off.

- It loads only on https, never on local files, localhost or inside claude.ai
- A small banner asks visitors to accept or decline first. Nothing loads before they accept, the choice is remembered in the browser, and an "Analytics choice" button in the controls lets them change it
- Usage events are sent once accepted: export format, PDF paper size and dpi, format change, shoes added, Trio layout. Poster text and uploaded files are never sent
