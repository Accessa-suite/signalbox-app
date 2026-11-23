# Install on macOS

> Install Signalbox on a Mac from the .dmg and open it the first time, past the "Apple could not verify" warning.

Section: Getting started · Updated: 2026-11-23

Signalbox for macOS is one app for Apple silicon and Intel Macs, on macOS 11 Big Sur or later. The app isn't signed with an Apple Developer ID, so the first time you open it takes one extra step.

## Before you start

- Install `git`. The Xcode command line tools include it: run `xcode-select --install` in Terminal.
- Install at least one agent and log in to it in Terminal: Claude Code (`claude`), Codex (`codex`), Gemini CLI (`gemini`) or opencode (`opencode`).
- If you use GitHub, installing the `gh` command and running `gh auth login` lets Signalbox read your pull requests without a token.

## Install

1. Download the `.dmg` from the [download page](https://signalbox.accessa.co.ke/download/).
2. Open the `.dmg` and drag **Signalbox** onto **Applications**.
3. Open **Terminal** and run the command below. It removes the "downloaded from the internet" flag that macOS puts on the app, and changes nothing else.
4. Open Signalbox from Applications or Spotlight.

```
xattr -dr com.apple.quarantine /Applications/Signalbox.app
```

> **Note:** Without step 3, macOS says "Apple could not verify "Signalbox" is free of malware", "Signalbox can't be opened because Apple cannot check it for malicious software", or "Signalbox is damaged and can't be opened". The file isn't damaged. All three mean the app isn't notarised by Apple.

## Without Terminal

1. Open Signalbox once and close the warning.
2. Open **System Settings → Privacy & Security**.
3. Scroll down to the message about Signalbox and click **Open Anyway**.
4. Confirm with your password or Touch ID.

> **Warning:** On macOS 15 Sequoia and later, right-click → **Open** no longer gets you past the warning. Use **Open Anyway** or the Terminal command.

## Updates

You clear the quarantine once per download. Updates that Signalbox installs itself don't need it again. If you replace the app with a new download from the website, run the `xattr` command again. See [Updates](updates.md).

## The first time it runs

- **Agents and tools.** Signalbox finds `claude`, `codex`, `gemini`, `opencode`, `git` and `gh` through your login shell's `PATH`, the same way Terminal does. Installs from Homebrew, nvm or `~/.local/bin` work. If you install an agent while Signalbox is open, quit it and open it again.
- **Keychain.** The first time Signalbox saves or reads a token (for a tracker, a code host or phone alerts), macOS asks for Keychain access. Choose **Always Allow**.
- **Closing the window.** Your sessions keep running. Click Signalbox in the Dock, or its lamp in the menu bar, to bring the window back. Quit from the lamp's menu or with ⌘Q.

## Related

- [macOS won't open Signalbox](macos-wont-open.md)
- [First run](first-run.md)
- [Agent not found](agent-not-found.md)
- [Install on Linux](install-linux.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/install-macos/
