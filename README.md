# GenerativeTesting

A private bench for trying generative routes side by side.

## Sproutsmith Route Lab

`index.html` is a single static page, with no build step and no server. It calls fal's queue API straight from the browser with a fal key you paste into the page.

- The key is kept in that browser's local storage and is sent only to fal. It is never in this repo.
- Every run is a real call on your fal account and spends your fal balance.
- Use a key made just for testing, and delete it at fal when you are done.
- fal's safety checker is left on. The page sends no setting that loosens it.

### Using it

Open `index.html` in a browser, or turn on GitHub Pages for this repo (Settings, Pages, deploy from the `main` branch, root folder) and open the Pages link.

### Routes

The route list is the `ROUTES` array near the top of the script in `index.html`. Endpoint ids and field names were read from fal's client library (`@fal-ai/client` 1.11.0, November 2026). fal renames and retires routes; one that answers "not found" needs its id checked on fal.

To add a route, add one entry to `ROUTES`: its kind, endpoint id, a name, and its fields. "Any other route" in the page runs any endpoint without editing the file.

### Not for production

Putting a key in the browser is for quick tests only. A real product keeps the key on a server and has the page call that server.
