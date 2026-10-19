# NIIMBOT Custom Label Studio — User Guide

[**Open the Label Studio**](https://tmags-ai.github.io/niimbot-custom-label-studio/)

This free browser-based label designer is intended for the **NIIMBOT M2-H** printer. Use desktop Google Chrome or Microsoft Edge with Bluetooth support.

## 1. Connect your printer

1. Turn on your NIIMBOT M2-H and load the correct label roll.
2. Open the Label Studio website.
3. Set the label width and height to match the installed roll.
4. Click **Connect Bluetooth**.
5. Select your printer in the browser permission window and approve the connection.

You can design labels before connecting; Bluetooth is only required to print.

## 2. Create a label

Use the layer controls to add and customize:
- **Text:** product names, strengths, LOT numbers, dates and other information.
- **Images:** PNG, JPG or WebP artwork and logos.
- **QR codes:** a URL or text string encoded as a scannable QR code.
- **Shapes and lines:** rectangles, rounded rectangles, circles, triangles and hexagons.

Select a layer to adjust its position, size, rotation, color, font, and other available properties. Drag elements in the preview to arrange the design. Enable **Snap to another layer** to assist alignment.

## 3. Import a Canva design

1. In Canva, choose **Share → Download**.
2. Export the design as **PNG** (recommended) or **PDF Print**.
3. In Label Studio, find **Import a finished label** and choose **Upload Canva export / preconfigured label**.
4. Select the exported file and check its size and alignment in the preview.

Imported finished-label artwork can fill the label. Use the layer/image tools when you want to position artwork alongside separately editable text and QR codes. For thermal printing, prefer high-contrast black-and-white artwork.

## 4. Print custom design copies

1. Confirm that the preview and label dimensions look correct.
2. Connect the printer.
3. Set the desired number of copies in **Print custom design copies** (1–100).
4. Click **Print custom design copies**.
5. Start with **one test label** before a large print run.

Recommended starting settings: **Print density 3**, **Paced** Bluetooth write mode, and **1** test copy.

## 5. Save and reopen a design

- **Export editable project:** save a reusable, editable project file.
- **Import project:** reopen a previously saved project.
- **Clear layers:** start a new design; export your project first if you want to keep it.

## 6. Batch print using CSV

Create a CSV spreadsheet with column headers and a row for each label variation. For example:

```csv
Product,Strength,LOT,Copies
Product A,10 mg,LOT-001,5
Product B,20 mg,LOT-002,10
Product C,30 mg,LOT-003,5
```

In your design, insert matching placeholders into text or QR layers:

- `{{Product}}`
- `{{Strength}}`
- `{{LOT}}`

Load the CSV in the **CSV batch printing** section. The application replaces placeholders with the values from each row. The optional **Copies** column sets the quantity for that row. The example requests **20 labels** in total.

Use the included [batch-example.csv](batch-example.csv) as a template.

## 7. Troubleshooting

**Printer not found:** Make sure the M2-H is powered on, Bluetooth is enabled on your computer, and the browser supports Web Bluetooth. Disconnect the printer from another active device if needed.

**Printer connects but won't print:** Check battery, label roll, label dimensions and printer model. Try disconnecting/reconnecting and printing one label in **Paced** mode.

**Label appears faint or unclear:** Try adjusting print density and using solid black-and-white, high-contrast artwork. Small details and gray gradients may not reproduce well.

**Website shows 404:** Confirm that GitHub Pages is publishing from `main` and `/(root)`, with `index.html` at the repository root.

**Canva artwork looks wrong:** Re-export as PNG at the correct aspect ratio and check the preview before printing.

## 8. Support development

[☕ Support Development on Buy Me a Coffee](https://buymeacoffee.com/tmags)

Donations are optional. The Label Studio remains free to use.

---

**Compatibility note:** This build is designed for the NIIMBOT M2-H. Other NIIMBOT printer models have not been verified with this version. This is an independent project, not affiliated with NIIMBOT or Canva.

## Multi-ribbon color printing (manual registration)

The Studio supports **Black, White, Gold, Red, Blue, and Green** as virtual layer/ribbon colors. These colors are a screen preview; the M2-H prints one physical ribbon color at a time.

1. Create your custom label and select each text, shape, image, or QR layer.
2. Choose its **Ribbon / layer color** in the selected-layer properties.
3. Set **Preview → All colors (combined)** to see the complete design. You can also preview just one color. White ink is displayed against a light-gray preview background so it remains visible.
4. Select the physical ribbon color in **Ribbon installed / print color** and enter the number of copies.
5. Load that color ribbon and click **Print selected ribbon color**. Only elements assigned to that color are sent as black-and-white print data; the physical ribbon supplies the ink color.
6. **Manually rewind and precisely realign** the same labels without changing their order or position. Install the next ribbon, select its color, and print again.
7. Repeat for each color. Use the **same label dimensions and copy count** for every pass.

**Important:** This is manual multi-pass printing, not automatic color printing. Registration accuracy depends on your rewind and feed alignment. Test with a single label before printing multiple copies. Imported finished artwork is not separated automatically into color layers; use editable Studio layers for color passes. The regular single-pass printing controls should not be used for mixed-color custom designs.

Ribbon color assignments are included when you **Export editable project** as JSON and restored when you **Import project**.
