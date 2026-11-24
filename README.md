# NIIMBOT Custom Label Studio

A free, independent, browser-based label designer for the **NIIMBOT M2-H** featuring Bluetooth/USB workflows, a zoomable drag-and-drop editor, imported artwork, QR codes, shapes, Vial Calc (including an optional four-stage Protocol builder), and single-label or CSV batch printing.

[☕ Support Development](https://buymeacoffee.com/tmags) — voluntary donations; no features are locked behind a donation.

## Features
- Create labels with text, images, QR codes, lines, circles, rectangles, triangles, hexagons and rounded corners
- Reposition, resize, rotate, reorder, duplicate and snap layers
- Import exported Canva PNG/JPG/WebP/PDF artwork; import/export editable JSON projects
- Export PNG labels with custom filenames
- Print multiple copies of a custom design or print variable-data batches from CSV
- Live label preview, zoom, undo/redo and an easier-to-use layer editor
- **Vial Calc:** concentration (mg/mL), optional U-100 conversions and linked text layers
- **Vial Calc → Enable Protocol:** enter up to four stages (amount in mg and duration in weeks), preview a formatted schedule, optionally show per-stage U-100 equivalents, and insert a linked editable **Protocol** text layer; stages update the layer automatically
- See the [online Studio User Guide](guide.html#vial-calc) for the Protocol walkthrough

## Vial Calc protocol feature

Open **Custom Label → Vial Calc**, then check **Enable Protocol**. Enter a positive amount in mg and a duration in weeks for each of up to four stages; unused stages can be left blank. Optionally enter **Vial amount (mg)** and **Final vial volume (mL)** to display a U-100 conversion for stages where it can be calculated. The Studio flags values outside the vial amount or above 100 U-100 units and omits those invalid conversions. Click **Add protocol layer** to place the schedule on the label, then move and style it like any text layer. The schedule is linked to the calculator and updates when stage entries change. Export the editable JSON project to save the inputs and linked layer.

**For informational label formatting only.** This feature does not prescribe, validate, or recommend a treatment or dosing schedule. Verify any figures independently before use.

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

## User guide

📖 **[Read the complete Label Studio User Guide](USER_GUIDE.md)** for setup, label design, Canva imports, Bluetooth printing, batch CSV printing, and troubleshooting.
