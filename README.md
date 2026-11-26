# Sweep

A Mac disk cleaner built as a single Claude artifact page: `sweep.html`.

- **In a browser or Claude's artifact panel** it shows how to install Sweep as a Mac app from the Claude desktop app.
- **Installed as a Mac app**, it asks once for full disk access, then scans and cleans by itself. It can also show in the menu bar and send notifications.

## Scanning

One scan, shown as one: a drawing of the Mac's drive, one status line under it with Stop (then Continue), and one clock.

- Sweep measures 19 places where space builds up (caches, logs, Xcode, simulators, package caches, Docker, old downloads and more) while it maps the home folder.
- Claude then looks past them for app leftovers, caches and old build folders. Sweep checks and measures every find itself.
- Results land in the sidebar: a gauge for the disk and what cleaning frees, and the items in three groups, Caches and logs, Developer and Large files.

## Cleaning

Clean opens one dialog: how much is deleted directly and how much goes to the Trash, where it can be restored.

- **Clean up** moves what it can to the Trash. Steps that are a tool's own command (npm, pnpm, simulators, Go modules, Docker) can't use the Trash and always delete. Claude's finds always go to the Trash.
- **Delete Immediately** deletes everything directly, Claude's finds included.
- The dialog shows one progress bar, then closes, and dust and a wiper play over the page. The results update from what the clean did, with no second scan: cleaned items drop out, what went to the Trash counts toward "Empty the Trash", and the free space is the clean's own last reading.
- When a scan or clean finishes while Sweep is in the background, it sends a notification.

## Files

- `sweep.html` is the whole app: markup, styles, the scan and clean shell scripts, and the page's code.

## Publishing

The page is published as a Claude artifact. Changes are made in `sweep.html` and published again to the same artifact from Claude. The installed app offers a reload when a new version is published.

## Notes for the app

- The window's drag areas come from CSS `app-region` rules. The Claude app copies every element such a rule matches into window-drag areas that sit above the whole page, dialogs included, and those areas take clicks and hover. Keep the selectors narrow: the toolbar is `nav.top`, because the drive drawing's SVG faces are also class `top`.
