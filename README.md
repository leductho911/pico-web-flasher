# MindReset Pico — Web Flasher

Web-based firmware flasher for **MindReset Pico** (`ESP32-S3`) using `esptool-js` and Web Serial API.

- **Live Flasher:** https://leductho911.github.io/pico-web-flasher/
- **Requirements:** A Web Serial-compatible browser (Google Chrome, Microsoft Edge, or Opera) over HTTPS (or `localhost`).

---

## Deployment & Updating Firmware

### Option 1: Fastest & Cleanest (Separate repo or `gh-pages` branch)
Keep your source repo clean without committing `.bin` files to `english-improve` / `main`:

1. Create a new public GitHub repository (e.g. `leductho911/pico-web-flasher`), or use a `gh-pages` branch on your fork.
2. Copy **only these 7 files** from `build/boards/packages/pico/` into the root of that repo/branch:
   - `index.html`
   - `esptool-js-0.7.0.js`
   - `manifest.json`
   - `bootloader.bin`
   - `partitions.bin`
   - `firmware.bin`
   - `ota_data_initial.bin`
3. Push to GitHub.
4. On GitHub, open **Settings → Pages**:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (or `master` / `gh-pages`) and `/ (root)`
   - Click **Save**.
5. After ~1 minute, your flasher is live at:
   - `https://leductho911.github.io/pico-web-flasher/` (if separate repo), or
   - `https://leductho911.github.io/read-pico-reader/` (if `gh-pages` branch).

> **Note:** Your `index.html` uses relative paths (`./manifest.json`, `./esptool-js-0.7.0.js`, etc.), so it works out of the box at any GitHub Pages URL with zero edits. Whenever you rebuild firmware, just overwrite the `.bin` files and `manifest.json` and push.

