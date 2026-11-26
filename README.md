# Sweep

A Mac disk cleaner as a Claude artifact

## Install

Paste this into Claude:

```
Build me https://github.com/smnmmnn/sweep
```

1. Open the artifact in the Claude desktop app on a Mac.
2. Choose **Install as app** from the artifact's menu.
3. Open Sweep from the Dock. It asks once for full disk access.

Sweep only works as an installed app on macOS.

## Compatibility

You need:

- A Mac, Apple Silicon or Intel.
- The Claude desktop app to install Sweep as an app.
- Full disk access for Sweep.

## What it does

**Scan:** Sweep checks the usual places where space piles up: caches, logs, Xcode and simulators, package caches, Docker, and old downloads. Then Claude looks for more, such as app leftovers and old build folders. Sweep double-checks everything Claude finds. Results are grouped into three categories: Caches and logs, Developer, and Large files.

**Clean:**

- **Clean up** moves files to the Trash, so you can get them back. A few caches (npm, pnpm, simulators, Go modules, Docker) get cleared by their own tool instead, so those are gone for good.
  
- **Delete Immediately** deletes everything.

Sweep can live in the menu bar, and it tells you when a scan or clean finishes in the background.

## Development

The whole app is `sweep.html`. There is no build step.
