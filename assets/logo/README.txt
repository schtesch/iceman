ICEMAN logo files
=================

WHICH FILE TO USE
- Website header: svg/iceman-lockup-compact-on-light.svg
  (use the -on-dark file on purple or other dark backgrounds)
- Larger placements such as an about page, title slide or poster:
  svg/iceman-lockup-on-light.svg or svg/iceman-lockup-on-dark.svg
- Icon alone, for example as a project card picture: svg/iceman-mark.svg
- Link preview or social media card (1200 x 630): png/iceman-project-card-1200x630.png
- The png/ folder holds PNG copies (lockups at 3x size). Prefer the SVG files on websites.

The lockup files include clear space around the artwork. Keep at least that
much space free when you place them.

FAVICON
Copy the files in favicon/ to the root folder of the website and add these
two lines to the <head> of each page:

  <link rel="icon" href="/favicon.ico" sizes="16x16 32x32 48x48">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">

favicon.ico contains a hand-drawn pixel version for 16 px and a simplified
version for 32 and 48 px. Browsers pick the size they need.

favicon.svg holds the simplified 32 px design as a vector. It is optional:
some browsers prefer an SVG favicon and scale it down to 16 px instead of
showing the pixel version.

icon-192.png and icon-512.png suit a web app manifest.
apple-touch-icon.png uses the purple background because iOS fills
transparent areas with black.

TEXT
All text appears as outlines, so the files look the same on every computer.
To change the wording, regenerate the files. The typeface is Outfit
(free, SIL Open Font License, available from Google Fonts).

PLOT INSIDE THE CUBE
Log scale, fixed-effect inverse-variance pooling, two equally precise subgroups.
- Pooled estimate: CI just crosses the line of no effect, p = 0.08
- Subgroup 1: CI excludes the line of no effect, p < 0.001
- Subgroup 2: CI crosses the line of no effect, p = 0.33
- Test for interaction: p = 0.002
- The diamond spans 71% of each subgroup interval
