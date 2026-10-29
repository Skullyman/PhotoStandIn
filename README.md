# Island Rail Stand-In

A web photo stand-in for the Restore Island Rail Society. Visitors pick a board, take a selfie or choose a photo, line their face up in the hole, and download the finished picture.

## Privacy

Everything runs in the visitor's browser. Photos are never uploaded, stored or shared: there is no server, database or analytics, and the only outside request is for the Google Fonts typefaces. The finished picture leaves the device only if the visitor saves or shares it themselves. The page says this to visitors under "Add your photo".

## Files

- `index.html` — the whole app (HTML, CSS and JavaScript in one file)
- `boards/reimagine-frame.jpg` and `boards/reimagine-frame-hole.png` — the Rails with Trails Frame (the default board) and the cut-out shape for its opening
- `boards/halloween.jpg`, `boards/halloween-hole-1.png`, `boards/halloween-hole-2.png` — the two-person Happy Halloween board and the cut-out shape for each face
- `boards/salish-express.jpg` — the Salish Express board
- `boards/window-seat.jpg` — the Window Seat board
- `boards/tunnel.jpg` — the Tunnel Run board
- `boards/rail-with-trail.jpg` — the Rail with Trail board
- `boards/profile-frame.jpg` and `boards/profile-frame-hole.png` — the square Profile Frame board and the cut-out shape for its opening

- `favicon.ico`, `favicon.png`, `apple-touch-icon.png` — the browser tab and home-screen icons
- `og-image.jpg` — the preview picture shown when the link is posted on Facebook, X, LinkedIn, Slack, texts and so on

The face holes are cut in code, so the green in the artwork never shows.

## Publish with GitHub Pages

1. Create a repository and upload both files, keeping the `boards` folder.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then **Save**.
4. After a minute the app is live at `https://<your-username>.github.io/<repo-name>/`.

## Adding or changing a board

Add the image to `boards/`, then add a line to the `SCENES` list near the top of the script in `index.html`. Each board has a `holes` list with one entry per face: its centre (`x`, `y`) and radii (`rx`, `ry`) in pixels. Square boards also set `w` and `h`.

For faces that aren't a clean oval, give the hole a `mask`: a PNG the same size as the board that is transparent everywhere except the face shape. Boards with several holes get a "Photo 1 / Photo 2" picker automatically. The first board in the list is the one that opens by default.

## Link preview

The `og:` and `twitter:` tags at the top of `index.html` point to `https://photo.restoreislandrail.com/`. If the address ever changes, update `og:url`, `og:image` and `twitter:image` to match.

## Custom domain

The `CNAME` file tells GitHub Pages to serve the site at `photo.restoreislandrail.com`. Keep it in the repository.

## Camera

**Take a photo** opens the front camera. On phones it uses the phone's own camera screen. On computers it shows a live webcam view with a 3-second countdown. The browser asks permission the first time. The camera only works over `https://` (GitHub Pages is fine). If the stand-in is embedded in an iframe, the iframe needs `allow="camera"`.
