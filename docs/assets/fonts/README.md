# Self-hosted web fonts

Inter and Playfair Display, both SIL Open Font Licence 1.1, which permits
self-hosting. Licence texts are alongside the font files as the OFL requires.

Each file is a variable font, subsetted to Latin and with its weight axis
trimmed to the range the site actually uses, then compressed to woff2:

  inter-latin-var.woff2            weight 300-700, upright
  playfair-latin-var.woff2         weight 400-700, upright
  playfair-italic-latin-var.woff2  weight 400-500, italic

Three files replace eleven static weights previously fetched from Google
Fonts on every page load. Serving them from this origin also stops visitor
IP addresses being sent to Google, which is the reason a German court found
unconsented Google Fonts embedding unlawful in 2022.

To regenerate, subset the upstream variable fonts with pyftsubset using the
Google "latin" unicode range and --flavor=woff2.
