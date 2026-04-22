# MyLanGo Brand Package

This folder is the custom Open edX brand package used by MyLanGo MFEs.
It provides logos, favicon, and Paragon theme overrides.

Package name: `@thitlwin/brand-mylango.app`

## Quick start

From this folder:

```bash
npm install
npm run build
```

If you are editing often:

```bash
npm run build:watch
```

## What to edit

### 1) Logos and favicon

Replace these files (keep names the same):

- `logo.svg`
- `logo-trademark.svg`
- `logo-white.svg`
- `favicon.ico`
- `paragon/images/card-imagecap-fallback.png`

### 2) Fonts

- Import fonts in `paragon/fonts.scss`
- Set global theme fonts in `paragon/_variables.scss`:
  - `$font-family-sans-serif` for body text
  - `$headings-font-family` for headings
- Add optional utility classes in `paragon/_overrides.scss`

Current setup uses:

- `"Shadows Into Light"` as main font
- `"Shadows Into Light Two"` for headings

### 3) Colors and component style

- Update base colors and theme map in `paragon/_variables.scss`
- Add component-level adjustments in `paragon/_overrides.scss`

## Local validation checklist

Before publishing/deploying:

<<<<<<< Updated upstream
`/paragon/fonts.scss`, `/paragon/_variables.scss`,
`/paragon/_overrides.scss` A SASS theme for
[\@edx/paragon](https://github.com/openedx/paragon). Theming
documentation in Paragon is coming soon. In the meantime, you can start
a theme by the contents of [\_variables.scss (after line
7)](https://github.com/openedx/paragon/blob/master/scss/core/_variables.scss#L7-L1046)
file from the Paragon repository into this file.

## MyLanGo consistency notes

This package is configured to match the current marketing color palette:

- Primary: `#DA291C`
- Secondary: `#0A1128`
- Accent: `#FDF4F5`

To keep LMS/CMS/MFEs and marketing pages visually consistent:

1. Keep these values aligned with `openedx-cms/src/app/globals.css`.
2. Update `paragon/_variables.scss` for Sass-level defaults.
3. Update `paragon/tokens/src/...` for token-based theme builds.
4. Rebuild and publish this package, then rebuild MFE images in Tutor.
=======
1. Run `npm run build`
2. Ensure no SCSS errors
3. Check that logo files exist with exact required names
4. Commit and push your changes

## Deploy to Tutor/Open edX

This brand is consumed by Tutor MFE builds (via plugin/config).
After updating this repo branch/tag:

```bash
source ~/hso-openedx-venv/bin/activate
tutor config save
tutor images build mfe --no-cache
tutor local dc up -d --no-deps --force-recreate mfe
```

## Common issue

If MFE build fails with SCSS errors like `Missing argument $border`,
your brand styles are incompatible with the Paragon version used by MFEs.
Fix by updating brand SCSS mixin calls to match the current Paragon API,
or align MFE/brand versions (same release family).

## File reference

- Theme fonts import: `paragon/fonts.scss`
- Theme variables: `paragon/_variables.scss`
- Theme overrides: `paragon/_overrides.scss`
>>>>>>> Stashed changes
