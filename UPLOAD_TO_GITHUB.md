# GitHub upload instructions

Upload these files to the root of your GitHub Pages repository:

- `index.html`
- `README.md`
- `site.webmanifest`
- `apple-touch-icon.png`
- `icon-192.png`
- `icon-512.png`

Replace the existing files with the same names.

The updated `index.html` supports both the reliable clipboard Shortcut flow and the automatic Base64 URL import flow.

## Recommended iPhone clipboard Shortcut

Use this when automatic deep-link handoff is unreliable:

```text
Receive Apps and Text input from Share Sheet
If there’s no input: Get Clipboard

Get text from Shortcut Input

Copy Text to Clipboard

Text:
https://peter8-hub.github.io/9x9-GO-Game-History-Tracker/?clip=1

Open URLs
```

Then tap **Import from Clipboard** inside the tracker.

## Automatic Base64 URL Shortcut

The app also supports this URL format:

```text
https://peter8-hub.github.io/9x9-GO-Game-History-Tracker/?autosave=1&sgf64=[URL Encoded Base64 Text]
```

Shortcut action order:

```text
Receive Apps and Text input from Share Sheet
If there’s no input: Get Clipboard

Get text from Shortcut Input

Encode Text with base64
Line Breaks: None

URL Encode Base64 Encoded

Text:
https://peter8-hub.github.io/9x9-GO-Game-History-Tracker/?autosave=1&sgf64=[URL Encoded Text]

Open URLs
```

After testing, remove temporary `Show Result` actions from the shortcut.
