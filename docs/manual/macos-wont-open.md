# macOS won't open Signalbox

> Fix "Apple could not verify Signalbox" or "Signalbox is damaged" on macOS with one Terminal command, or with Open Anyway in System Settings.

Section: Troubleshooting · Updated: 2026-11-23

The Mac builds aren't notarised by Apple yet, so the first time you open a downloaded copy, macOS blocks it. The app isn't damaged. Clear the block once and it opens normally.

## What you see

One of these:

- "Apple could not verify "Signalbox" is free of malware…"
- "Signalbox can't be opened because Apple cannot check it for malicious software."
- "Signalbox is damaged and can't be opened. You should move it to the Trash."

All three mean the same thing: macOS put a quarantine flag on the download.

## Fix it with Terminal

1. Make sure Signalbox is in **Applications** (drag it there from the `.dmg`).
2. Open **Terminal**.
3. Run:

```sh
xattr -dr com.apple.quarantine /Applications/Signalbox.app
```

4. Open Signalbox from Applications or Spotlight.

The command only removes the quarantine flag. It changes nothing else.

## Fix it without Terminal

1. Open Signalbox once and close the warning.
2. Open **System Settings → Privacy & Security**.
3. Scroll down to the message about Signalbox and click **Open Anyway**.
4. Confirm with your password or Touch ID.

> **Note:** On macOS 15 Sequoia and later, right-click → **Open** no longer gets you past the warning. Use **Open Anyway** or the Terminal command. On macOS 14 and earlier, right-click → **Open**, then **Open** again, also works.

## When you need to do it again

- Once per download. If you replace the app with a new download, clear the quarantine again.
- Not after updates that Signalbox installs itself. See [Updates](updates.md).

## Still won't open

- Check your Mac runs macOS 11 Big Sur or later.
- If you moved the app somewhere other than Applications, use that path in the command.
- If it opens and then quits at once, start it from Terminal to see its output: run the program inside `Signalbox.app/Contents/MacOS/`. See [Logs and data locations](logs-and-data.md).

## Related

- [Install on macOS](install-macos.md)
- [Updates](updates.md)
- [Logs and data locations](logs-and-data.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/macos-wont-open/
