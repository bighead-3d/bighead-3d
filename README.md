# 3d.bighead.life

One column of Bighead pieces in live 3D, each with dimensions and a "see in your space" AR link. Hosted free on GitHub Pages.

## Add a piece

1. Export from Blender at real size (Ctrl+A → All Transforms, origin at bottom center).
2. Drop the files into `models/`, named by the piece number:
   - `models/04.glb` (required; web, Android AR)
   - `models/04.usdz` (optional; iPhone AR. Without it the page builds one on the fly)
3. Add an entry to `pieces.json`:

```json
{
  "id": "04",
  "dims": "45\" x 61\" x 4.5\"",
  "glb": "models/04.glb",
  "usdz": "models/04.usdz"
}
```

Watch the commas: every entry except the last ends with `},`.

4. Commit. The site updates in about a minute.

Optional: add `"poster": "posters/04.jpg"` to show a still image while the model loads.

## Link a piece from bighead.life

Set the Squarespace image's click-through URL to `https://3d.bighead.life/#04`. That opens the piece alone; a "see them all" link leads to the full column.

## Size guide

| Use | Target |
| --- | --- |
| Each GLB / USDZ on this site | under 10 MB (under 5 MB loads fastest on a phone) |
| GitHub hard limit per file | 100 MB |
| GitHub site size | about 1 GB recommended |

Keep high-res masters off the site. Decimate a web copy per piece.

## Setup (once)

1. New public repo, upload this folder, Settings → Pages → deploy from `main`, root.
2. Custom domain: `3d.bighead.life` (the `CNAME` file already says so). Tick "Enforce HTTPS" once it's available.
3. In the domain's DNS: add a CNAME record, host `3d`, pointing to `<your-github-username>.github.io`.
