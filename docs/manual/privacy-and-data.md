# Privacy & data

> What Signalbox keeps on your machine, what it sends and to whom, where tokens are stored, and how to remove it all.

Section: More · Updated: 2026-11-23

Signalbox is a desktop app. It has no Signalbox account and no Signalbox server for your work. This page lists what it keeps, what leaves your machine, and where it goes.

## What stays on your machine

- **The database**: projects, repos, checkouts, tickets, notes, drafts, links to tracker issues, settings, the time and cost cache, and the search index. It's one SQLite file in Signalbox's data folder. See [Logs and data locations](logs-and-data.md).
- **Your code.** Signalbox reads your repos with git and shows diffs and files. It doesn't upload them anywhere itself.
- **Agent transcripts.** They stay where each agent writes them (for example `~/.claude/projects/` for Claude Code). Signalbox reads them to show sessions, time and cost, and to build the search index.
- **Crew messages** go between agents over a local socket. Nothing listens on a network port.

The app has no analytics or telemetry. The Signalbox website counts page visits; the app doesn't report anything about you or your use.

## What leaves your machine

Signalbox only talks to services you set up, plus the update check.

| Where | What is sent | When |
|---|---|---|
| **Your git remotes** | `git fetch` for every repo | At start and every 5 minutes, and when you click the fetch button |
| **Your tracker** (Jira, Kanboard, Notion or a Board API) | Searches and issue reads; issues you create or send from a draft; comments and QA notes you post; status changes from automatic moves | When you search, import, post or create; automatic moves when a branch reaches a mapped stage |
| **Your code host** (Bitbucket or GitHub) | Pull request lookups (reviews, comments, builds); pushes and new PRs | Lookups in the background for tickets with an open PR and when you open a ticket; pushes and PRs only when you click **Create PR** |
| **ntfy or Telegram** | The ticket key and title, the agent, and the first line of its last message. Code and anything that looks like a secret are stripped | Only when phone alerts are on and an alert is due |
| **The Signalbox update server** | A request for the latest version | At start and every 6 hours if automatic checks are on, or when you check by hand |

Nothing is posted to a tracker or a code host without you clicking a button, except automatic status moves you've mapped. See [Stage → status mapping](stage-status-mapping.md).

## Agents

Coding agents (Claude Code, Codex, Gemini CLI, opencode) run on your machine with your own login. What they send to their provider is between you and that provider, as when you run them in a terminal.

Signalbox gives agents two things:

- The prompt you or Signalbox type into the session, such as a crew briefing or review comments from **Fix review comments**.
- For **Write…**, the daily log and release notes: a writing agent run on your machine over the ticket, its branch diff, commits and the tail of its sessions. That material goes to the writing agent's provider. The text comes back to you to edit; nothing is posted until you choose to.

Signalbox never adds permission-skipping flags to an agent.

To report live state, Signalbox starts Claude Code with its own hooks settings file, and gives Gemini CLI a settings file the same way. Your own agent config files aren't edited.

## Tokens and secrets

Tracker tokens, code host tokens and phone alert tokens are kept in your operating system's keychain: Keychain on macOS, Secret Service (such as GNOME Keyring) on Linux. They aren't in Signalbox's database, and the app's interface can't read them back once saved.

Entries are stored under the service `ke.co.accessa.signalbox.v2`:

| Entry | What it is |
|---|---|
| `tracker:<connection id>` | A tracker connection's token |
| `forge:<connection id>` | A code host connection's token |
| `alerts:ntfy_token` | The ntfy access token |
| `alerts:telegram_token` | The Telegram bot token |

If you use `gh` for GitHub, Signalbox asks `gh` for its login; that token stays in `gh`'s own store.

## Removing data

- **A project:** **Projects & settings**, open the project, **Delete project**. This forgets the project, its repos and checkouts. Nothing on disk is touched.
- **A token:** remove the connection, or click **Forget** next to a phone alert token.
- **Everything:** quit Signalbox and delete its data folder. Remove the keychain entries above with your keychain app. Your repos and agent transcripts aren't affected.

## Related

- [Logs and data locations](logs-and-data.md)
- [Phone alerts](phone-alerts.md)
- [Code hosts](code-hosts.md)
- [Updates](updates.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/privacy-and-data/
