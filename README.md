# XR Lab Hours Sign

A single‑file, print‑ready **HTML** sign for posting the Lone Star College XR Lab open hours. Designed for **letter (8.5×11 in) landscape**, black‑and‑white, and easy on ink.

![preview](./screenshot.png)

---

## Features

* **One page, one file**: no build step or framework required.
* **Print‑friendly**: border prints, large legible type, hides buttons when printing.
* **Wordmark‑first** layout: big logo/wordmark on the left, **QR to book** on the right.
* **Clear hours**: Morning / Afternoon with a 30‑minute lunch break implied.
* **Accessible**: semantic table with `aria-label`, high‑contrast colors.

---

## Repo Structure

```
/ (repo)
├─ index.html           # The sign (open in a browser and print)
├─ XR Lab Logo_Black.png# Your wordmark/logo
├─ Lab Booking Form QR.png  # Your QR code image
└─ README.md            # This file
```

> **Tip:** File names in `index.html` already point to `XR Lab Logo_Black.png` and `Lab Booking Form QR.png`. Adjust if yours differ.

---

## Quick Start

1. **Clone / download** this repo.
2. Drop in your assets:

   * Replace `XR Lab Logo_Black.png` with your wordmark (ideally a transparent PNG or SVG).
   * Replace `Lab Booking Form QR.png` with your QR code.
3. Open `index.html` in **Chrome** or **Edge**.
4. `Ctrl/Cmd + P` → print using the settings below.

### Print Settings

* **Destination:** your printer or "Save as PDF"
* **Pages:** 1 page
* **Layout / Orientation:** **Landscape**
* **Margins:** Default (or None)
* **Scale:** 100% (do not fit to page)
* **Headers/Footers:** Off
* **Background graphics:** On (usually optional, but keep on for consistent border thickness)

> If your printer refuses landscape, try printing to PDF first, then print the PDF.

---

## Customization

Open `index.html` and tweak:

### 1) Hours

Edit the `<tbody>` rows under the **Morning** and **Afternoon** columns.

```html
<tr>
  <td>Tuesday</td>
  <td>10:00 AM – 12:30 PM</td>
  <td>1:00 PM – 4:00 PM</td>
</tr>
```

### 2) Logo / Wordmark

* Replace the `src` for the logo image:

  ```html
  <img src="XR Lab Logo_Black.png" alt="Lone Star College XR Lab" class="logo" />
  ```
* **Size** is controlled by `.logo { max-width: 6.5in; }` in `<style>`. Adjust as needed.

### 3) QR Code

* Replace the `src` in the QR `<img>` tag.
* Size is controlled by `.qr img { width: 2.2in; height: 2.2in; }`.

### 4) Title Text

The big header under the logo says **“Lab Hours.”** Change it here if desired:

```html
<h1 class="title">Lab Hours</h1>
```

### 5) Footer Contact

Edit the footer line near the bottom:

```html
<div class="footer">
  Questions? Reach out to <a href="mailto:tc-xrlab@lonestar.edu">tc-xrlab@lonestar.edu</a>
</div>
```

### 6) Border & Shadows

The printed page keeps a **2px** black border. You can change the thickness by editing:

```css
.sheet { border: 2px solid var(--line); }
```

---

## Accessibility Notes

* Uses a semantic `<table>` with a descriptive `aria-label`.
* High‑contrast monochrome palette.
* Meaningful `alt` text on images (`alt="Lone Star College XR Lab"`, `alt="QR code to booking form"`).

---

## Troubleshooting

* **It prints on multiple pages** → Ensure **Landscape** and **Scale = 100%**. If your browser adds extra margins, set **Margins = None** or reduce the table font-size from `18pt` to `16pt` in the CSS.
* **Border doesn’t print** → Some printers drop thin lines when “Background graphics” is off. Turn **Background graphics** on or increase border to `3px`.
* **QR looks soft** → Export the QR as a high‑resolution PNG (at least 800×800 px) or use an SVG.
* **Logo too big/small** → Tweak `.logo { max-width: ... }` until it balances visually with the QR.

---

## Browser Support

Tested in **Chrome 126+** and **Edge 126+** on Windows 10/11. Other modern browsers should work; printing behavior can vary by driver.

---

## Versioning

Use simple tags like `v1.0.0`, `v1.1.0`, etc. Changelog example:

* **v1.1.0** – QR moved to top‑right, footer contact added, print border enforced.
* **v1.0.0** – Initial landscape layout with morning/afternoon columns.

---



---

## Credits

Design & layout: XR Lab @ Lone Star College.
