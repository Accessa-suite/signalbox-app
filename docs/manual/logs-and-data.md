# Logs and data locations

> Where Signalbox keeps its database, hook and crew files, emulator logs and keychain entries on Linux and macOS, and how to see its log output.

Section: Troubleshooting · Updated: 2026-11-23

Signalbox keeps everything it owns in one data folder, and tokens in your system keychain. Use this page to find them when you're troubleshooting, backing up, or starting fresh.

## The data folder

| System | Folder |
|---|---|
| Linux | `~/.local/share/signalbox-v2/` (or `$XDG_DATA_HOME/signalbox-v2/`) |
| macOS | `~/Library/Application Support/signalbox-v2/` |

What's inside:

| File or folder | What it is |
|---|---|
| `signalbox.db` | The SQLite database: projects, repos, checkouts, tickets, notes, drafts, tracker links, settings, the time and cost cache and the search index |
| `events.jsonl` | Live state events from agent hooks (working, needs you, done) |
| `hooks.json` | The hooks settings file Claude Code sessions start with |
| `gemini-hooks.json` | The same for Gemini CLI |
| `mcp/` | One identity file per crew session, for the local crew server |
| `mcp.sock` | The crew server's socket (Linux). On macOS it's in a short private temp folder instead, such as `$TMPDIR/signalbox-v2/mcp.sock` |
| `logs/` | Emulator logs (`emulator-<name>.log`) from devices started with the device picker |
| `icon.png` | The icon used for desktop notifications |

> **Warning:** Quit Signalbox before you copy or delete `signalbox.db`. Copying it while the app runs can give you a broken copy.

## What isn't in the data folder

- **Your repos** stay where they are. Deleting a project in Signalbox doesn't touch them.
- **Agent transcripts** stay in each agent's own folder, such as `~/.claude/projects/` for Claude Code.
- **Tokens** are in the system keychain, under the service `ke.co.accessa.signalbox.v2`. Entries are named `tracker:<id>`, `forge:<id>`, `alerts:ntfy_token` and `alerts:telegram_token`. See [Privacy & data](privacy-and-data.md).
- **Worktrees** Signalbox creates are inside each checkout, under `.claude/worktrees/`.

## See Signalbox's log output

Signalbox prints warnings and errors to its standard error. To see them, start it from a terminal:

- **AppImage:** run the AppImage file from a terminal, for example `./Signalbox_<version>_amd64.AppImage`.
- **.deb:** run the `signalbox` program from a terminal. If your system names it differently, check the Exec line in its `.desktop` file under `/usr/share/applications/`.
- **macOS:** quit Signalbox, then run the program inside `/Applications/Signalbox.app/Contents/MacOS/` from Terminal.

Most problems also show in the app itself: as a red message where you clicked, in **Projects & settings** (for example **Last check failed:** under **About**, or **Last:** under **Phone alerts**), or behind the **!** next to **Fetched …** at the bottom of the rail for fetch errors (hover it).

## Start fresh

1. Quit Signalbox from the tray lamp's menu.
2. Move the data folder somewhere else (or delete it).
3. Open Signalbox. It starts on the welcome screen.

Tokens stay in the keychain. Remove them with your keychain app if you want them gone too.

## Related

- [Privacy & data](privacy-and-data.md)
- [Update failed](update-failed.md)
- [Agent not found](agent-not-found.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/logs-and-data/
