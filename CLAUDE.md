# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static web-based APK distribution page for **ManyDrug (의약품 정보)**, a Korean pharmaceutical information Android app. The site provides a download landing page for beta testers with app details, installation instructions, and direct APK download from GitHub Releases.

- **Primary language**: Korean (UI and documentation)
- **Tech stack**: HTML5, CSS3, vanilla JavaScript — all embedded in a single `index.html`
- **No build system, no package manager, no dependencies** (only external resource: Google Fonts)

## Running Locally

```bash
# Option 1: Open index.html directly in a browser

# Option 2: Local HTTP server
python -m http.server
# Then visit http://localhost:8000
```

There are no tests, linters, or build steps.

## Architecture

Everything lives in `index.html`:
- **Lines ~1-10**: HTML head, metadata, Google Fonts (Inter)
- **Lines ~10-204**: Embedded `<style>` — dark theme, card-based responsive layout, purple-pink gradient accents
- **Lines ~206-301**: HTML body — header, Android download card, iOS TestFlight card, features list, changelog
- **Lines ~303-326**: Embedded `<script>` — `downloadAPK()` function (triggers GitHub Releases download) and dynamic build date updater

APK is served from: `https://github.com/jeff-kho/manydrugtest/releases/download/v1.5.0%2B7/app-release.apk`

## Key Conventions

- **Single-file approach**: All CSS and JS are embedded in `index.html`, not in separate files
- **Responsive design**: Mobile-first, max-width 680px container, CSS Grid (2-col → 1-col on mobile)
- **Dark theme**: Background #000000, cards #1a1a1a, accent gradient #8A2BE2 → #FF1493
- **App metadata in HTML**: Version (v1.5.0 Build 7), file size (30.1 MB), min SDK (API 21), target SDK (API 35) are hardcoded in the page

## Assets

`assets/` contains branding images: app logo, icon, and 4 app screenshots (main, search, drug detail, laws).

## Documentation Files

All deployment/hosting guides are in Korean markdown files at the project root. `README.md` covers 5 hosting options (GitHub Pages, Firebase, Netlify, Google Drive, Vercel). `GEMINI.md` provides an English-language project summary.
