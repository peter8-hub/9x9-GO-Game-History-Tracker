# 9×9 GO Tracker

A static, browser-only personal history tracker for 9×9 Go SGF games.

## What it does

- Paste a 9×9 SGF game.
- Preview the parsed result and final board before saving.
- Save games locally in your browser history.
- Reopen saved games for replay.
- View simple personal stats.
- Export and restore your archive.

The app is focused on history tracking. It does not calculate territory, detect dead stones, verify scores, or provide AI review. The official result comes from the SGF `RE[...]` field.

## How to open it

1. Download or unzip the release package.
2. Open `index.html` in a modern browser such as Chrome, Safari, or Edge.
3. Keep using the same browser/profile if you want the local saved history to remain available.

No server, account, backend, API, npm, build step, or internet connection is required.

## How to paste and save SGFs

1. Open the app.
2. Go to **Add Game**.
3. Paste a 9×9 SGF into the box.
4. Click **Preview Game**.
5. Check the result summary and final board.
6. Click **Save to History**.

The app is hard-coded to detect the user name `idfji` from `PB[...]` or `PW[...]`.

## Where data is stored

Saved games are stored locally in the browser using IndexedDB.

This means:

- Saved games should persist after refreshing the page.
- Saved games should persist after closing and reopening the browser, as long as browser storage is not cleared.
- Saved games are local to that browser/profile/device.
- Clearing browser data, using private browsing, changing devices, or using a different browser profile can remove or hide the saved history.

## How to back up data

Use **Backup & Export → Export full JSON backup**.

The JSON backup is the safest preservation format because it contains the full saved records, including:

- original SGF text
- parsed metadata
- result fields
- replay/final-board data
- favorites, review-later flags, notes, and tags
- derived capture/opening/profile fields

Back up regularly before clearing browser data or switching devices.

## How to restore data

1. Open **Backup & Export**.
2. Click **Import JSON backup**.
3. Select a previously exported backup file.

Import merges records with the current archive and skips duplicates using the normalized SGF hash and game fingerprint.

## CSV export

Use **Export CSV summary** to download a spreadsheet-friendly summary of saved games.

The CSV uses user-perspective fields such as color, result, margin, move count, captures, opening summary, and other non-opponent summary fields. It does not include opponent names by default.

## SGF ZIP export

Use **Export SGF archive** to download a ZIP containing one original `.sgf` file per saved game.

Expected structure:

```text
go-tracker-sgf-export.zip
└── sgf/
    ├── game-001-black-win-84moves.sgf
    ├── game-002-white-loss-54moves.sgf
    └── ...
```

This export is useful when you want individual original SGF files outside the app.

## Detail SGF export

From a saved game’s replay/detail view, use **Export Original SGF** to download that single game’s original SGF text.

## Known limitations

- No scoring engine.
- No territory calculation.
- No dead-stone detection.
- No score verification.
- No AI review.
- No screenshot/OCR.
- Variations are imported as main line only.
- No full ko/superko validation.
- Browser-local storage can be lost if browser data is cleared.
