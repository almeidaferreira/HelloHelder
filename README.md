# HelloHelder: Shoe Poster Studio

Single-file poster tool (`index.html`). A layered, glowing 3D shoe (Three.js) rotates 360 degrees, sits inside an editable poster layout, and exports to PNG/JPG at screen or print resolution (A4/A3 at 300 dpi, with DPI metadata).

- Edit headline, subline, copy position (7 variants), format (landscape, portrait, square), colours
- Pin frames of the rotation and return to them
- Partner logo strip with stand-ins, or upload your own logos
- Load an `.obj` to wrap the glowing layers around another model (beta)

## Analytics

The page loads Vercel Web Analytics (cookieless page views) when it is served from a Vercel domain. It does not load on local files or inside claude.ai.
Turn it on once in the Vercel dashboard: project `shoe-poster-studio`, Analytics tab, Enable. Usage events (export format, PDF paper size, format change, shoes added, Trio layout) are sent as custom events, which need a Vercel plan that includes them. Poster text and uploaded files are never sent.
