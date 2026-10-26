# SmartPDF Studio: website package

A complete PDF scanner and toolkit that runs in the browser. Files are processed on the visitor's device; nothing is uploaded by the app.

## Put it online (free, about 5 minutes, no coding)

Upload the **contents of this folder** (index.html, sw.js, manifest.webmanifest, the icons folder) to any static host. Every option below gives you an https address, which the camera scanner, password protection and "install app" all require.

* **Netlify Drop:** open app.netlify.com/drop and drag this folder onto the page.
* **GitHub Pages:** create a repository, upload these files, then Settings → Pages → Deploy from a branch → `main` / root.
* **Cloudflare Pages, Vercel, Firebase Hosting or your own web server:** upload the same files as a static site; no build step.

Open the address on a phone or computer. To install it as an app: Chrome/Edge menu → Install app; iPhone/iPad Safari → Share → Add to Home Screen.

The first visit needs internet (the PDF libraries load from the cdnjs and jsDelivr CDNs, with each as a backup for the other). After that the app opens offline and the tools that do not need new library downloads keep working. OCR downloads its engine and the language data it needs (a few MB per language) the first time you use it, then remembers them on that device.

## Tools

Organize: merge, split, extract/remove pages, visual page organizer (rotate, reorder, duplicate, delete), create PDF portfolio.
Optimize: compress (keeps text sharp; recompresses images and removes unused data).
Convert to PDF: JPG/PNG/WEBP, Word, Excel, PowerPoint (text only for the Office formats).
Convert from PDF: JPG/PNG, text, Word, Excel, PowerPoint.
OCR & Text Recognition: turn scanned PDFs and photos into searchable PDFs, plain text, Word or Excel (97 languages, up to 3 at once), with a review box to correct and search the recognized text.
Edit: full-screen editor (edit text in place, add text, date, notes, images, signatures, highlight, underline, strike-through, shapes, arrows, freehand, whiteout, remove item, pinch to zoom), watermark and page numbers, fill and flatten forms, create form fields.
Security: protect with a password (AES-128), unlock with the password, redact (flattens pages to images and verifies no text remains).
Utilities: metadata, repair, compare, Bates numbering, extract attachments. Camera document scanner with filters and multi-page PDF.

## Known limits

* OCR needs internet the first time each language is used, and accuracy depends on scan quality (use the review box). Table recognition into Excel is best-effort.
* Office conversions keep text only, not layout or images.
* Edit text changes the original text inside the PDF, keeping its font, size and colour. It can only use characters that exist in the PDF's embedded font (PDFs that embed only part of a font may lack some letters or digits, and the editor says which). Text inside images or scans needs OCR first.
* Password protection and the camera need https (any host above provides it).
* Tested in Chromium. Firefox and Safari were not available for testing; they should work on current versions, but report anything odd.
