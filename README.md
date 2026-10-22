# Read Aloud

A single-file text-to-speech page. Type or paste text, pick a voice, and press Play. It uses the speech engine built into your browser, so there is nothing to install and no account or API key.

## Features

- Reads any text aloud with the voices installed on your device
- Highlights each word as it is spoken and shows progress
- Play, pause, resume and stop
- Speed (0.5x to 2x), pitch and volume controls
- Voices grouped by language, with a note when a voice is online
- Remembers your last text, voice, speed, pitch and volume between visits
- Light and dark themes that follow your system setting
- Works on desktop and phone widths
- Keyboard shortcut: Ctrl or Cmd + Enter starts and pauses

## Files

| File              | Purpose                                              |
| ----------------- | ---------------------------------------------------- |
| `read-aloud.html` | The whole app: markup, styles and script in one file |
| `README.md`       | This file                                            |

## Run it

1. Download `read-aloud.html`.
2. Open it in a browser (double-click it, or drag it into a browser window).

No build step or server is needed.

## How it works

- **Speech:** the browser's Web Speech API (`speechSynthesis`). Available voices depend on your operating system and browser.
- **Word highlighting:** driven by the `boundary` events the speech engine fires. Some voices, especially online ones, send these less reliably, so highlighting may be coarser.
- **Long text:** split into chunks of roughly 160 characters so that long passages are not cut off by some browsers.
- **Changing a setting while speaking:** playback restarts from the current word with the new voice, speed, pitch or volume.
- **Saved settings:** stored in the browser's `localStorage` under `read-aloud-prefs` (voice, speed, pitch, volume) and `read-aloud-text` (last text). Clearing site data or using a private window resets them.

## Browser support

Any recent version of Chrome, Edge, Safari or Firefox that supports speech synthesis. If it is not supported, the page shows a message and disables Play.

## Limitations

- The list of voices comes from your device, so it differs between computers and phones.
- Some browsers pause or stop speech when the tab is in the background.
- The page only reads text you type or paste. It does not export audio files.

## 
