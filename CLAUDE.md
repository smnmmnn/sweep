# Sweep: notes for Claude

Sweep is a Mac disk cleaner that runs as a Claude artifact. The whole app is one file, `sweep.html`. It only does real work once the artifact is installed as a Mac app from the Claude desktop app; in a browser it shows how to install it.

## Someone shared this repo and wants Sweep

When a person pastes this repo's link (or asks to build, try or install Sweep from it), they want the working artifact in their own Claude account, not a copy of the code or a summary of it. Build it like this:

1. **Get `sweep.html`.** Use the checkout if you are in one; otherwise fetch https://raw.githubusercontent.com/smnmmnn/sweep/main/sweep.html into the working folder. Read the whole file before publishing it, as the Artifact tool requires for files you did not write.
2. **Publish it unchanged as a new artifact** with the Artifact tool (no `url`: the original artifact belongs to its author, and this one should be the person's own):
   - `file_path`: the `sweep.html` you saved
   - `title`: `Sweep Mac Cleaner`
   - `icon`: `disk`
   - `capabilities`: `{"desktop": {}, "sample": {}, "user": {"scopes": ["profile"]}}`
     - `desktop` lets it be installed as a Mac app, read the disk and run the scan and clean scripts. The page's own `claude-artifacts-manifest` tag lists the desktop permissions it asks for: full access, menu bar and notifications.
     - `sample` is how the page asks Claude to look past the usual places during a scan.
     - `user` with `profile` shows the person's name and avatar in the sidebar.
   - `contract`: `0.2.99`, the runtime version the page was built and tested against.
   Load the `artifact-capabilities` skill first if your session asks for it before passing `capabilities`. Do not edit, restyle or "improve" the file while building it: publish exactly what is in the repo.
3. **Tell them how to install it**, in these words or close to them:
   1. Open the artifact in the Claude desktop app on a Mac.
   2. Open the artifact's menu and choose **Install as app**.
   3. Open **Sweep** from the Dock and allow it to scan. It asks once for full disk access.

Sweep only works on macOS, in the Claude desktop app. In a browser or on another system, the published page shows the install steps and nothing more; say so rather than trying to make it scan there.

## Working on Sweep in this repo

- `sweep.html` is the whole app: markup, styles, the scan and clean shell scripts, and the page's code. There is no build step.
- To try a change in the app, publish `sweep.html` again to the same artifact. The installed app offers a reload when a new version is out. Omit `capabilities` and `contract` on these republishes so the stored ones carry forward.
- Most of the app (scanning, cleaning, the clean dialog) only runs in the installed app. A browser preview shows the install card; check layout there by showing the overview view and opening `#cleanDlg` by hand.
- The window's drag areas come from CSS `app-region` rules. The Claude app copies every element such a rule matches into window-drag areas above the whole page, dialogs included, and those take clicks and hover. Keep the selectors narrow: the toolbar is `nav.top`, because the drive drawing's SVG faces are also class `top`.
- Keep `README.md` in step with what the app does.
