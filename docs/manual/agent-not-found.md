# Agent not found

> An agent shows "not installed", or its session ends at once with "command not found". How Signalbox finds agents, and how to fix it.

Section: Troubleshooting · Updated: 2026-11-23

Signalbox runs the agent CLIs you already have: `claude`, `codex`, `gemini` and `opencode`. If it can't find one, that agent shows **not installed** and can't be picked. This page explains where Signalbox looks and how to make it find yours.

## What you see

- In **Projects & settings → Agents**, the agent has a **not installed** flag and no path.
- In agent pickers, it's listed as `<name> (not installed)` and greyed out.
- A session starts and ends straight away. The terminal shows something like `command not found`, then **Session ended.**
- **Write…** fails with "couldn't start the agent: …".

## Where Signalbox looks

For each agent, Signalbox looks in this order:

1. The folders on its own `PATH`.
2. The agent's usual install folder, such as `~/.local/bin` for Claude Code and `~/.opencode/bin` for opencode.
3. Common install folders: `~/.local/bin`, nvm's Node versions (newest first), `~/.bun/bin`, `~/.npm-global/bin`, `~/.volta/bin`, `~/.cargo/bin`, `~/.yarn/bin`, `/usr/local/bin`, `/opt/homebrew/bin` and `/usr/bin`.
4. Your login shell, by running `command -v <name>` in it.

Sessions themselves start through your login shell (`$SHELL`), so they get the same `PATH` as a terminal you open yourself.

On macOS, an app opened from Finder or the Dock gets a minimal `PATH`. At start, Signalbox reads your login shell's `PATH` and uses it, so Homebrew, nvm and `~/.local/bin` installs work.

What Signalbox found is remembered for 10 minutes.

## Fix it

1. Check the agent works in a terminal:

```sh
claude --version
codex --version
gemini --version
opencode --version
```

2. If it doesn't, install it and log in to it first, following the agent's own instructions.
3. In Signalbox, open **Projects & settings → Agents** and click **Re-check**.
4. Still **not installed**? Quit Signalbox fully and open it again, so it picks up your shell's new `PATH`. Closing the window isn't enough: Signalbox keeps running in the tray or menu bar. Quit from the tray lamp's menu.

> **Tip:** If you installed the agent somewhere unusual, add that folder to `PATH` in your shell's login file (for example `~/.profile`, `~/.bash_profile` or `~/.zprofile`), then quit and reopen Signalbox.

## A ticket or project is set to an agent you removed

If the ticket's or project's agent isn't installed, new sessions on it try to start that agent and fail. Pick another agent:

- On the ticket: the **Agent** picker in the drawer, or choose the default option to inherit from the project.
- On the project: **Projects & settings**, **Edit** the project, then its **Agent**.
- The default for everything: **Projects & settings → Agents → Default agent**.

See [Supported agents](agents.md).

## "can't join a crew"

Each agent row in **Projects & settings → Agents** says **no crews yet** when that agent can't be a crew member. Pick another agent for that member. See [Crews](crews.md).

## Related

- [Supported agents](agents.md)
- [Sessions](sessions.md)
- [Install on macOS](install-macos.md)
- [Logs and data locations](logs-and-data.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/agent-not-found/
