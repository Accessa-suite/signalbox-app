# Install on Linux

> Install Signalbox on Linux from the .deb package or the AppImage, and what each needs.

Section: Getting started · Updated: 2026-11-23

Signalbox for Linux comes as a `.deb` package and as an AppImage, both for 64-bit x86 (`x86_64` / `amd64`). Pick the `.deb` on Debian, Ubuntu and their derivatives, and the AppImage anywhere else.

## Before you start

- **glibc 2.34 or newer.** Debian 12, Ubuntu 22.04 and newer have it. Check with `ldd --version`.
- **git**, and at least one agent installed and logged in: Claude Code (`claude`), Codex (`codex`), Gemini CLI (`gemini`) or opencode (`opencode`).
- **A keyring** for tokens. GNOME Keyring or KWallet (any Secret Service provider) works. Without one, Signalbox can't save tracker or code host tokens.
- **gh** (optional). If you use GitHub, `gh auth login` lets Signalbox read your pull requests without a token.

## Install the .deb

1. Download `Signalbox_<version>_amd64.deb` from the [download page](https://signalbox.accessa.co.ke/download/).
2. In a terminal, in the folder you downloaded it to, run the command below. The `./` matters: it tells `apt` to install the file rather than look for a package by that name. `apt` also installs the libraries Signalbox needs.
3. Open **Signalbox** from your app menu.

```
sudo apt install ./Signalbox_*_amd64.deb
```

When an update comes, Signalbox asks for your password to install the new package. See [Updates](updates.md).

## Run the AppImage

1. Download `Signalbox_<version>_amd64.AppImage` from the [download page](https://signalbox.accessa.co.ke/download/).
2. Make it executable, in a terminal in the folder you downloaded it to.
3. Run it, by double-clicking it or from that terminal.

```
chmod +x Signalbox_*_amd64.AppImage
./Signalbox_*_amd64.AppImage
```

Keep the AppImage where you put it, for example in `~/Applications`. Updates replace the file in place, so it must be in a folder you can write to.

> **Tip:** If the AppImage doesn't start and mentions FUSE, install your distribution's FUSE 2 package (on Ubuntu 22.04 and newer it is `libfuse2`, on 24.04 `libfuse2t64`).

## The first time it runs

- Signalbox finds `claude`, `codex`, `gemini`, `opencode`, `git` and `gh` on your `PATH`. Start it from your app menu or a terminal where those commands work. If you install an agent while it's open, restart Signalbox.
- Closing the window hides it. Your sessions keep running, and a lamp in the system tray shows their state. Click the lamp, or **Open Signalbox** in its menu, to bring the window back. **Quit** in the tray menu quits for real. If sessions are still working, Signalbox asks first.

## Related

- [First run](first-run.md)
- [Install on macOS](install-macos.md)
- [Updates](updates.md)
- [Update failed](update-failed.md)
- [Agent not found](agent-not-found.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/install-linux/
