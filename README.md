# Sweep

A Mac disk cleaner built as a single Claude artifact page: `sweep.html`.

- **In a browser** it shows a sample Mac, and you can scan your own by pasting a read-only script into Terminal.
- **Installed as a Mac app** from the Claude desktop app, it scans by itself in two steps: it measures 19 places where space builds up, then Claude looks past them for app leftovers, caches and old build folders. Every find is checked and measured by Sweep, and Claude's finds only ever go to the Trash. When a scan or clean finishes while Sweep is in the background, it sends a notification.

## Files

- `sweep.html` is the whole app: markup, styles, the scan and clean shell scripts, and the page's code.

## Publishing

The page is published as a Claude artifact. Changes are made in `sweep.html` and published again to the same artifact from Claude.
