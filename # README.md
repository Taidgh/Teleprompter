# Teleprompter

A single-file, self-contained teleprompter for reading scripts off an external
display. No build step, no server, no dependencies — just open `teleprompter.html`
in a browser.

## Features

- **Full-screen scroll** — white text on a dark grey background, sized and
  paced for reading from a distance.
- **Adjustable speed and font size**, both in the editor and live while the
  prompter is running.
- **`<voice>` notes** — wrap stage directions, speaker labels, or cues you
  don't want spoken aloud in `<voice>...</voice>`. They render in a chosen
  color (pink by default) on the prompter with the tags themselves hidden,
  so they read as visual cues rather than script text.
  ```
  <voice>Federica:</voice> Welcome back to the lesson.
  <voice>(pause for response)</voice>
  ```
  The note color is adjustable via a color picker and is saved per script.
- **Local file storage** — no accounts, no cloud:
  - **Chrome / Edge**: link a folder once (via the File System Access API)
    and every save writes a real `.json` file straight into it. The app
    re-reads that folder automatically next time you open it, and deleting
    a script in the app deletes the file too.
  - **Safari / other browsers**: falls back to downloading a `.json` file on
    Save, with an **Import file** button to reload a previously saved script.
- **Light / dark mode** for the editor interface, with your preference
  remembered between sessions. The full-screen prompter display always stays
  dark-grey-on-white regardless of app theme, since that's what's legible
  on a screen while presenting.
- **Keyboard shortcuts** while the prompter is running:
  - `Space` — play / pause
  - `↑` / `↓` — adjust scroll speed
  - `Esc` — exit
- **Mirror flip** (horizontal/vertical) for use with physical teleprompter
  glass rigs, if you ever mount the display in one.

## Usage

1. Open `teleprompter.html` in a browser (Chrome or Edge recommended for full
   local-file support).
2. Write or paste your script, give it a title, and hit **Save**.
3. Adjust speed, font size, and note color to taste.
4. Move the browser window to your external display and click
   **Start teleprompter** — it will go full-screen.

## Browser support

The folder-linking storage relies on the File System Access API
(`showDirectoryPicker`), which is supported in Chromium-based browsers
(Chrome, Edge, Brave, Opera) but not currently in Safari or Firefox. Those
browsers still work fully — scripts just save via file download/import
instead of a live folder link.

## Privacy

Everything runs locally in the browser. No data is sent anywhere — scripts
are saved either to a folder you explicitly choose on your own machine, or
downloaded directly to your Downloads folder.

## License

Do whatever you want with this.