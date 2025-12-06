# Parts Checklist

**PartsChecklist-v0.10.html** — single-file app to merge CSVs of LEGO parts and generate printable A4 sheets for verifying physical pieces.

---

## Files
- **PartsChecklist-v0.10.html** — the single-file application you can open in a browser.  
- **README.md** — this file.  
- **LICENSE** — project license (recommended: MIT).

---

## Features
- Merge multiple CSV files and preserve file order.  
- Smart size detection from `NxM` patterns in part names.  
- Repeat items by quantity, adjustable columns, and image scale.  
- Click-to-remove uploaded CSVs; printable A4 sheets with sheet titles.  
- Single-file distribution for easy sharing and printing.

---

## CSV format
The parser expects the **last three columns** to be `elementId`, `quantity`, `image`. Everything before those columns is treated as the part **name** (this makes the parser tolerant of commas inside names).

**Example row**
```csv
name,elementId,quantity,image
FLAT TILE 2X4,4579690,1,bltb7137c2c8faefd45/4579690.jpg
```

## Notes

- If the `image` column is a short path (e.g., `blt.../4579690.jpg`) the app converts it to the LEGO CDN photoreal URL.  
- Size detection looks for patterns like `1x1`, `2x4`, `4X4` in the name and maps stud counts into buckets:
  - **studs 1–2** → **1×1**
  - **studs 3–4** → **2×2**
  - **studs 5–6** → **3×3**
  - **studs 7+** → **4×4**

---

## Usage

1. Open **PartsChecklist-v0.10.html** in a modern browser.  
2. Upload one or more CSV files using the file input.  
3. Click a filename in the file list to remove it from the merged set.  
4. Adjust **Columns** and **Image scale** as needed.  
5. Toggle **Repeat by quantity** and **Show captions**.  
6. Click **Print A4** to print the sheets.

---

## Development

- The app is a single HTML file. Edit **PartsChecklist-v0.10.html** directly.  
- App version is stored in the `APP_VERSION` constant near the top of the script — update it when you add features or fixes.  
- For quick testing, open the file directly in a Chromium-based browser or any modern browser.

---

## Contributing

- Open an issue for bugs or feature requests.  
- If you submit a PR, include a short description and update `APP_VERSION` in the file header.  
- Keep changes focused and include examples or test CSVs when relevant.

---

## Changelog (high level)

- **v0.10** — Single-file app, multi-CSV merge, smart size detection, printable A4 layout.

---

## Contact

If you want help adapting the layout, adding per-file sheets, or automating exports, open an issue or add a note in the repository.
