# Island Rail Stand-In

A web photo stand-in for the Restore Island Rail Society. Visitors pick a board, upload a photo, line their face up in the hole, and download the finished picture.

Everything runs in the browser. Photos never leave the visitor's device.

## Files

- `index.html` — the whole app (HTML, CSS and JavaScript in one file)
- `boards/salish-express.jpg` — the Salish Express board
- `boards/window-seat.jpg` — the Window Seat board
- `boards/tunnel.jpg` — the Tunnel Run board
- `boards/rail-with-trail.jpg` — the Rail with Trail board

- `og-image.jpg` — the preview picture shown when the link is posted on Facebook, X, LinkedIn, Slack, texts and so on

The face holes are cut in code, so the green in the artwork never shows.

## Publish with GitHub Pages

1. Create a repository and upload both files, keeping the `boards` folder.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then **Save**.
4. After a minute the app is live at `https://<your-username>.github.io/<repo-name>/`.

## Adding or changing a board

Add a 2400×1350 image to `boards/`, then add a line to the `SCENES` list near the top of the script in `index.html` with its name, file and `hole` (centre `x`, `y` and radii `rx`, `ry`, in pixels).

More at [restoreislandrail.com](https://restoreislandrail.com).

## Link preview

The `og:` and `twitter:` tags at the top of `index.html` point to `https://skullyman.github.io/PhotoStandIn/`. If you move the site to its own address (for example `photo.restoreislandrail.com`), change the `og:url`, `og:image` and `twitter:image` addresses to match.
