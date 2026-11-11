# Grace Taiken: website

The website for **Grace Taiken Fashion & Beauty Salon** (WhatsApp name "taikenfashion"), a fashion designer and dressmaker at 341 Nkomo Street, Pretoria West. Built by TshedzaWebDev as a free preview; it becomes the live site if they go ahead.

**Preview:** https://sudo-tm12.github.io/grace-taiken/ (GitHub Pages, deployed from the `main` branch root)

## What it is

- **Format:** one self-contained page (`index.html`). There is no build step; edit the file and push.
- **Design:** "the atelier", built from their sign: gold on deep espresso, ivory sections, and Cormorant Garamond with Manrope.
- **Hero:** a fabric swatch book that fans open on a gold rivet (lace, shweshwe, satin, wax print, pinstripe), with a "GT made to measure" hang tag.
- **Fabrics:** each service card is topped with its fabric. All the fabrics are drawn in code (SVG/CSS patterns), with no stock photos.
- **Tape measure:** it runs across the page and slides as you scroll.
- **Process:** "How it works" runs along a stitched line on desktop; on phones the steps are cards that stack as you scroll.

**Scroll effects:** one `requestAnimationFrame` loop drives them all. It works only on what is on screen and moves things with transform and opacity only. Everything is off under reduced motion.

- **Needle and thread:** a gold needle sews a thread down the page as you scroll. The thread follows a faint chalk line and crosses the page between sections.
- **Hero (desktop):** the headline rises in line by line with a gold shimmer, gold dust drifts behind it, and the swatch book fans wider as you scroll.
- **Hero (phones):** exactly one screen (`100svh`), tested at 360×780, 375×667, 390×844 and 412×915.
  - **Layout:** headline, swatch book, the picked fabric, the booking button, the address and the tape measure all show before the first scroll.
  - **Entrance:** the swatches are dealt in one by one, then fan open.
  - **Picking a fabric:** tap one, or swipe the fan (it tilts under the finger). The picked swatch springs up, the hero glow takes its colour, and the info strip updates with an "Ask" link to WhatsApp for that service.
  - **Before anyone touches it:** the fan cycles through the fabrics on its own, with a "Tap or swipe" hint.
  - **Gold dust:** it drifts away from the finger, and a tap throws sparkles.
  - **Fan sizing:** the size and vertical position are set in JS (`fitFan`) from the space available.
- **Occasions:** two ribbons drift in opposite directions and speed up with your scroll.
- **Fabric cards:** each fabric unrolls (clip reveal) with a light sweep, and the patterns drift with the scroll, so the satin shimmers.
- **Statement:** a pinned line ("Bring your idea. Leave with your identity.") fills word by word in ink and gold, with a large GT watermark turning behind it.
- **Closing:** the GT tag swings with your scroll speed.
- **Headings:** they rise in word by word, and the gold buttons carry a passing shine.
- **Visit the studio:** a live Google map, with a drawn fallback.
- **Phone action bar:** WhatsApp, Call and Directions, shown after the first scroll.
- **Buttons:** every one opens WhatsApp (+27 61 987 9968) with a message written for that service.
- **Not in search engines:** the page carries `noindex` until the client says go.
- **Extras:** JSON-LD ClothingStore data and reduced-motion support.
- **Logo:** `storefront.png` is the client's sign, taken from their WhatsApp Business profile picture.

## Before launch (if they go ahead)

- Add a gallery section with their real photos (the fabric visuals stay as the design language).
- Confirm their full opening hours, the services list, and "dukes" = doeks.
- Use their real logo file in the header in place of the sign photo.
- Remove `noindex` and connect their own domain if they want one.
