## XMind to Miro Importer

Miro Web SDK app to import XMind (.xmind) files into Miro as mind map nodes, with drag-and-drop upload, structure preview, and progressive import.

## Features

- Drag-and-drop or file picker upload for `.xmind`
- Tree preview with node stats before import
- Progressive import with cancel support
- Mirotone-based UI

## How it works

1. Upload an XMind file.
2. The app parses `content.json` and shows a structure preview.
3. On import, nodes are created in Miro using the Mindmap Node API.

## Deployment (Vercel)

This app is a static frontend and can be hosted on Vercel.

1. Push the repository to GitHub.
2. Create a new Vercel project and import the repo.
3. Framework preset: **Other** (static).
4. Build command: leave empty.
5. Output directory: leave empty.
6. Deploy.

After deploy, use the Vercel URL for your Miro app configuration:

- `sdkUri`: `https://<your-vercel-project>.vercel.app/main.html`
- Panel URL: `https://<your-vercel-project>.vercel.app/panel.html`

## Miro App Manifest

Use the YAML manifest (`manifest.yaml`) with:

- `sdkVersion: SDK_V2`
- `sdkUri` pointing to `main.html`
- `boardPicker.allowedDomains` including your Vercel domain
- `icons.colored` and `icons.outline` inline SVG

## Notes

- Mindmap Node API is **experimental** in the Web SDK and may require access.
- Cache busting may be needed after updates (append `?v=...` to URLs).
