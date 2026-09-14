# Panel Gutter

A single-page tool for padding a too-tall comic so Instagram stops cropping the
top and bottom panels off it.

Instagram's tallest feed frame is 4:5. A vertical comic strip is usually far
taller than that, so the feed centre-crops it and the first and last panels are
the first things to go. This adds **gutters** down the sides instead — a flat
band of colour that widens the image until it matches the frame, leaving every
panel intact.

## Use it

Open `index.html` in a browser. That's the whole install — no build step, no
dependencies, no network calls except the two Google Fonts. Everything happens
in the browser: the image is never uploaded anywhere.

To use it from a phone, serve the folder over your network
(`python3 -m http.server`) or host it on GitHub Pages.

## What it does

- **Frame** — 4:5 (feed), 1:1, 9:16 (story), 1.91:1, or Original for a plain
  border. It pads whichever axis needs it, so a too-wide image works too.
- **Gutter colour** — Black and White as one-tap buttons, a full colour picker,
  and *Match edges*, which takes the median of the image's border pixels and
  usually lands on the comic's own paper colour.
- **Extra gutter** — insets the artwork further inside the frame without
  changing the output ratio.
- **PNG or JPG** — PNG by default, since flat line art is what JPEG handles
  worst.
- **Save** — uses the platform's file-save path where one exists, otherwise the
  Web Share sheet (which gives you *Save Image* on iOS and Android), otherwise a
  plain download. On a phone you can also press and hold the preview.

Images keep their native resolution, capped at 3000px on the long edge.
EXIF rotation is honoured. Drag-and-drop and paste both work.

## Layout

`index.html` is the whole app — markup, styles, and script in one file. The
region between the `<!--ARTIFACT-->` markers is the portable fragment (title,
styles, body, script) that can be lifted out and hosted as a standalone page.
