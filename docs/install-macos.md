# Install on macOS

Signalbox runs on macOS 11 Big Sur or later, on Apple silicon and Intel. The Mac builds aren't signed with an Apple Developer ID yet, so the first open takes one extra step.

1. **Download and copy it to Applications.** [Download the .dmg](https://signalbox.accessa.co.ke/download/#macos), open it and drag **Signalbox** onto **Applications**.

2. **Clear the quarantine.** Open Terminal and run:

   ```
   xattr -dr com.apple.quarantine /Applications/Signalbox.app
   ```

   This removes the flag macOS puts on downloaded files. It changes nothing else.

3. **Open Signalbox.** Open it from Applications or Spotlight. It finds `claude`, `codex`, `gemini`, `opencode` and `git` through your login shell's PATH, the same way Terminal does, so Homebrew, nvm and `~/.local/bin` installs work.

## Without Terminal

Open Signalbox once and close the warning. Then go to **System Settings → Privacy & Security**, scroll to the message about Signalbox and click **Open Anyway**. Confirm with your password or Touch ID.

On macOS 15 Sequoia and later, right-click → Open no longer offers a way past the warning, so use Open Anyway or the Terminal command. On macOS 14 and earlier, right-clicking the app and choosing **Open**, then **Open** again, also works.

## What the warnings mean

Without the step above, macOS says “Signalbox can't be opened because Apple cannot check it for malicious software” or “Signalbox is damaged and can't be opened”. Both mean the app isn't notarised by Apple. The file isn't damaged.

You do this once per download. Updates that Signalbox installs itself don't need it again. If you replace the app with a new download, clear the quarantine again.

## First run

- **Keychain.** The first time Signalbox saves or reads a tracker token, macOS asks for Keychain access. Choose **Always Allow**.
- **Editors.** VS Code, Cursor, Zed and the JetBrains IDEs are found in Applications even if their command-line launcher isn't installed.
- **Closing the window.** Your sessions keep running. Click Signalbox in the Dock or its lamp in the menu bar to bring it back; quit from the lamp's menu or with `⌘Q`.
- **New tools.** If you install an agent CLI while Signalbox is open, quit Signalbox and open it again so it sees the new PATH.

---

Also on the website: https://signalbox.accessa.co.ke/install/macos/
