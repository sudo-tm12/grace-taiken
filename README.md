# Grace Taiken: website

The website for **Grace Taiken Fashion & Beauty Salon** (WhatsApp name "taikenfashion"), a fashion designer and dressmaker at 341 Nkomo Street, Pretoria West. Built by TshedzaWebDev as a free preview; it becomes the live site if they go ahead.

**Preview:** <https://sudo-tm12.github.io/grace-taiken/> (GitHub Pages, deployed from the `main` branch root)

## What it is

One self-contained page (`index.html`, no build step), plus `img/` (photos) and `storefront.png` (the client's sign, from their WhatsApp Business profile picture). Every button opens WhatsApp (+27 61 987 9968) with a message written for that service. The page carries `noindex` until the client says go.

- **Design:** "the atelier": gold on deep espresso, ivory sections, Cormorant Garamond with Manrope. Fabrics (lace, shweshwe, satin, wax print, pinstripe, gingham) are drawn in code and used as swatch chips and textures.
- **Hero: the atelier reel.** A tall rounded frame crossfades the six photos with a slow zoom.
  - Thin progress bars sit along the top.
  - A caption names the service and links to WhatsApp for it.
  - A soft glow behind the frame takes each photo's colour.
  - Tap right for the next photo, left for the previous; swipe; press and hold to pause. It pauses off screen.
  - On phones the hero is exactly one screen (`100svh`): headline, reel, booking button and address are visible before the first scroll. Checked at 360×780, 375×667, 390×844, 412×915 and 1440×900.
- **What we make:** photo cards. Each photo zooms out gently as it arrives and drifts with the scroll, with its fabric as a chip.
- **Scroll story:**
  - a gold needle sews a thread down the page
  - occasion ribbons drift across
  - a pinned statement fills word by word
  - on phones, the step cards stack as you scroll
  - the closing GT tag swings with your scroll speed
- **Visit:** a live Google map with a drawn fallback.

## Smoothness (how the motion is built)

- **One loop:** a single `requestAnimationFrame` loop reads all positions first and writes afterwards, so there are no forced re-layouts. Every scroll-driven value eases towards its target (`glide`) instead of jumping.
- **Thread:** one SVG path per section, so only the one being sewn repaints. The needle reads from a table of points worked out once, never from `getPointAtLength` while scrolling.
- **Cheap properties only:** the loop animates only `transform` and `opacity`. There is no backdrop blur on the sticky header or the phone bar, and no blend modes.
- **Measured:** a scripted 5,200 px scroll at phone size gave 0 frames over 33 ms (the previous version had 4).
- **Reduced motion:** everything is switched off when the visitor asks for less motion.

## Photos: stand-ins until the client sends their own

The six photos are freely licensed from Wikimedia Commons (CC BY-SA 4.0) and credited in the footer.

- `wedding.webp`: Photosbyosagie
- `heritage.webp`: Merriammahlaule.mm
- `evening.webp`: Chidi "Lex Ash" Ashimole
- `menswear.webp`: Ibrahima xaalil Ndiaye
- `children.webp`: Mathobelah
- `doeks.webp`: Jamie Tubers

Source pages are in `img/credits.json`. The photos were cropped to 800×880, so the crops are shared under CC BY-SA 4.0 too.

They show real people who have not agreed to advertise this business, so **replace them with Grace Taiken's own photos before launch**: same filenames, 800×880 WebP. Then remove the credits line.

## Before launch (if they go ahead)

- Their own photos (see above), and their real logo file in place of the sign photo.
- Confirm their full opening hours, the services list, and "dukes" = doeks.
- Remove `noindex` and connect their own domain if they want one.
