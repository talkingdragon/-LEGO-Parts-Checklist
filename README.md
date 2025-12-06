# Parts Checklist

Parts Checklist helps you merge one or more CSVs of LEGO parts, auto-detect sticker sizes from part names, and generate printable A4 sheets to lay out and verify physical pieces.

## Features
- Merge multiple CSV files and preserve file order
- Smart size detection from `NxM` patterns in part names
- Repeat items by quantity, adjustable columns, and image scale
- Click-to-remove uploaded CSVs; printable A4 sheets with sheet titles
- Simple single-file app (open `index.html` in a browser)

## CSV format
The parser expects the last three columns to be `elementId`, `quantity`, `image`. Everything before those columns is treated as the part name (this makes the parser tolerant of commas inside names).

Example row:
name,elementId,quantity,image FLAT TILE 2X4,4579690,1,bltb7137c2c8faefd45/4579690.jpg


Notes
- If the `image` column is a short path (e.g., `blt.../4579690.jpg`) the app will convert it to the LEGO CDN photoreal URL.
- The app detects sizes from patterns like `1x1`, `2x4`, `4X4` in the name and maps stud counts into grid buckets:
  - studs 1–2 → 1×1
  - studs 3–4 → 2×2
  - studs 5–6 → 3×3
  - studs 7+ → 4×4

## Usage
1. Open `index.html` in a Chromium-based browser (or any modern browser).
2. Upload one or more CSV files using the file input.
3. Click a filename in the file list to remove it from the merged set.
4. Adjust **Columns** and **Image scale** as needed.
5. Toggle **Repeat by quantity** and **Show captions**.
6. Click **Print A4** to print the sheets.

## Development
- The app is a single HTML file. Edit `index.html` directly.
- App version is stored in the `APP_VERSION` constant near the top of the script. Update it when you add features or fixes.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.
