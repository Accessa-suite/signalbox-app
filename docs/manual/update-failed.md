# Update failed

> What to do when an update won't download or install, when the .deb update asks for a password, or when About says updates aren't available.

Section: Troubleshooting · Updated: 2026-11-23

If an update doesn't go through, Signalbox keeps running the version you have. Nothing is half-installed. This page covers the messages you can see and how to get the new version anyway.

## The .deb asks for your password

That's expected. A `.deb` update installs a system package, so Linux asks for your password through its standard prompt (polkit, via `pkexec`). Enter your own password to continue.

- If you cancel the prompt, the update fails with **Install failed: …**. Click **Restart now** again when you're ready.
- If no password prompt appears at all, your desktop may not run a polkit agent (common on minimal window managers). Install the update by hand, below.

## Messages and fixes

| Message | What to do |
|---|---|
| **Download failed: …** | A network problem, or the file didn't match its signature. Check your connection and click **Restart now** again. |
| **Install failed: …** | For a `.deb`: the password prompt was cancelled or couldn't open. For an AppImage: Signalbox couldn't write the AppImage file; check you own it and the folder is writable. For macOS: make sure Signalbox is in a folder you can write to, such as Applications. |
| **Last check failed: …** in **Projects & settings → About** | Signalbox couldn't reach the update server. It tries again at the next check. Click **Check now** to try at once. |
| **Still checking for updates; try again in a moment.** | Wait a few seconds. |
| **The update is already being installed.** | Wait for the banner to finish. |
| **Updates aren't available for this install: it isn't a .deb, an AppImage or a macOS app.** | You're running a copy Signalbox can't replace, such as a binary copied by hand. Install from the download page. |
| **Updates aren't available for .rpm installs.** | Download a `.deb` or AppImage from the download page. |

## Install the update by hand

1. Open **Projects & settings → About** and click **Download page**, or go to the Signalbox download page.
2. Download the file for your system.
3. Quit Signalbox from the tray lamp's menu.
4. Install it:

On Linux with the `.deb`:

```sh
sudo apt install ./Signalbox_<version>_amd64.deb
```

On Linux with the AppImage, replace the old file with the new one and make it executable:

```sh
chmod +x Signalbox_<version>_amd64.AppImage
```

On macOS, drag the new Signalbox onto Applications and replace the old one. Then clear the quarantine once more:

```sh
xattr -dr com.apple.quarantine /Applications/Signalbox.app
```

Your projects, tickets and settings are kept. They live in the data folder, not in the app. See [Logs and data locations](logs-and-data.md).

## The banner went away

You clicked **Later**. The banner stays hidden for that version. Open the palette (Ctrl+K, ⌘K on Mac) and choose **Check for updates**, or click **Check now** in **About**, to bring it back.

## Related

- [Updates](updates.md)
- [Install on Linux](install-linux.md)
- [Install on macOS](install-macos.md)
- [macOS won't open Signalbox](macos-wont-open.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/update-failed/
