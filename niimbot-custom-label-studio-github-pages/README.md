# NIIMBOT Custom Label Studio

A free, independent, browser-based label designer for the **NIIMBOT M2-H** with Web Bluetooth printing, Canva-export imports, drag-and-drop layers, QR codes, shapes, and multiple-copy / CSV batch printing.

[☕ Support Development](https://buymeacoffee.com/tmags) — voluntary donations; no features are locked behind a donation.

## Features
- Create labels with text, images, QR codes, lines, circles, rectangles, triangles, hexagons and rounded corners
- Reposition, resize, rotate, reorder, duplicate and snap layers
- Import exported Canva PNG/JPG/WebP/PDF artwork; import/export editable JSON projects
- Export PNG labels with custom filenames
- Print multiple copies of a custom design or print variable-data batches from CSV
- Live label preview and independently scrolling editor controls

## Use online with GitHub Pages

1. Upload **the contents of this folder** to the root of a GitHub repository. Keep `index.html` at the repository root.
2. In GitHub, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the `main` branch and `/ (root)` folder, then **Save**.
5. After GitHub publishes the site, open `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/` using Chrome or Edge on a compatible desktop.
6. Turn on the M2-H, click **Connect Bluetooth**, and print a one-copy test label.

GitHub Pages uses HTTPS, which is required for Web Bluetooth. Printer pairing requires a direct user click and a compatible Bluetooth adapter/browser. Printing depends on third-party libraries loaded from CDNs, so internet access is required.

## Run locally

In this directory run:

```sh
python -m http.server 8000
```

Then visit `http://localhost:8000` in Chrome or Edge.

## Printer compatibility

The application explicitly checks for the **M2-H model ID 4608** before printing. Other models are **not enabled** in this build, even if the upstream library may support them. Printing is not independently hardware-certified; test first.

## CSV batch printing

Use `batch-example.csv` as a starting point. Insert matching placeholders (for example `{{Product}}`, `{{Strength}}`, `{{LOT}}`) into text or QR layers. A `Copies` column can override the global copies setting per row.

## Open-source credits

The app loads the following third-party libraries at runtime:

- [niimbot-web-bluetooth](https://github.com/iscarelli/niimbot-web-bluetooth) — browser Bluetooth printer protocol
- [PDF.js](https://github.com/mozilla/pdf.js) — PDF rendering
- [QRCode.js](https://github.com/davidshimjs/qrcodejs) — QR generation

Additional ecosystem acknowledgments (not imported by this application):
- [NiimBlue](https://github.com/MultiMote/niimblue)
- [NiimBlueLib](https://github.com/MultiMote/niimbluelib)

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and review upstream licenses before redistribution.

## Support

If this tool helps you, you can [support its development on Buy Me a Coffee](https://buymeacoffee.com/tmags). Donations are entirely optional.

## Disclaimer

Independent community project, not affiliated with or endorsed by NIIMBOT or Canva. NIIMBOT and Canva are trademarks of their respective owners. No warranties of printer compatibility or label accuracy.
