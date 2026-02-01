# GEMINI.md

## Project Overview

This project consists of a static web page and supporting documentation designed to facilitate the online distribution of a test version of an Android application named "Many Drug". The core of the project is a single `index.html` file that serves as a visually appealing download page for the `app-release.apk` file.

The directory also contains extensive documentation (in Korean) detailing multiple methods for hosting the download page on free platforms like GitHub Pages, Netlify, and Firebase.

**Technologies:**
*   HTML5
*   CSS3 (embedded)
*   Vanilla JavaScript (embedded)

## Building and Running

This is a static website with no build process.

### Running Locally

To view the website, you can simply open the `index.html` file in a web browser.

For a more realistic test that mimics a web server, you can use a simple local server. If you have Python installed, you can run the following command from the project's root directory:

```bash
# For Python 3
python -m http.server
```

Then, open your web browser and navigate to `http://localhost:8000`.

## Key Files

*   `index.html`: The main download page for the "Many Drug" Android application. It includes app details, installation instructions, and a download button.
*   `README.md`: A comprehensive guide (in Korean) explaining various options for hosting the APK and the download page.
*   `QUICK_START.md`: A fast-start guide (in Korean) for deploying the download page using services like Netlify and GitHub Pages.
*   `GITHUB_PAGES_업로드_가이드.md`: A detailed, step-by-step guide (in Korean) focused specifically on uploading the project to GitHub Pages.

## Development Conventions

The project uses standard, clean HTML, CSS, and JavaScript.
*   CSS is embedded within a `<style>` tag in the `index.html` head.
*   JavaScript is embedded within a `<script>` tag at the end of the `index.html` body.
*   The code is well-formatted and includes comments.
*   The primary language for the UI and documentation is Korean.
