# File Converter

A small browser-based file converter for personal use. It converts common image and audio files directly on the device, without uploading the selected files to a server.

## Features

- Drag and drop files or choose multiple files manually
- Image conversion to WebP, PNG, or JPEG
- Optional image resizing while preserving aspect ratio
- Adjustable quality for WebP and JPEG output
- Audio conversion to WAV or MP3
- Selectable MP3 bitrate: 96, 128, 192, 256, or 320 kbps
- Automatic audio resampling when needed for MP3 compatibility
- Per-file conversion status and output-size comparison
- Individual file downloads
- Download multiple converted files together as a ZIP archive
- Duplicate output filenames are handled automatically
- Light and dark mode support based on the browser/system preference
- Responsive layout for desktop and smaller screens
- Conversion settings are locked while processing to prevent mixed-output batches
- Existing converted results are cleared automatically when conversion settings change

## Privacy

Image and audio conversion is performed locally in the browser. The files selected for conversion are not uploaded by the app.

MP3 encoding uses the `lamejs` library loaded from cdnjs. Because of this external dependency, MP3 conversion requires access to that script when the page is opened. WAV and image conversion use browser APIs directly.

## Run

Open the hosted version in a modern browser:

https://file-converter.learninglabs.workers.dev/

You can also run the app locally by opening `index.html` in a modern browser. If MP3 conversion is needed, the browser must be able to load the external `lamejs` script from cdnjs.

## Supported Output Formats

### Images

- WebP
- PNG
- JPEG

Optional maximum image dimensions:

- Original size
- 1920 px
- 1280 px
- 800 px

The selected maximum applies to the longest side of the image while preserving its aspect ratio.

### Audio

- WAV
- MP3

Available MP3 bitrates:

- 96 kbps
- 128 kbps
- 192 kbps
- 256 kbps
- 320 kbps

## Technology

The app is intentionally lightweight and framework-free. Everything is contained in a single HTML file using:

- HTML
- CSS
- Vanilla JavaScript
- Canvas API for image conversion and resizing
- Web Audio API for audio decoding
- `lamejs` for MP3 encoding
- Blob and Object URL APIs for local downloads
- A small built-in ZIP implementation for downloading multiple converted files

## Notes

Browser support depends on the browser's ability to decode the source image or audio format. Very large images, long audio files, or large batches can use significant memory because conversion takes place entirely in the browser.

## Credits

Created by **Ehsan Ashour Zadeh** for personal use.  
October 2026.
