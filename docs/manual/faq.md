# FAQ

> Short answers to common questions about Signalbox: cost, agents, platforms, trackers, worktrees, privacy and what happens when you close the window.

Section: FAQ · Updated: 2026-11-23

Short answers to the questions people ask most. Each one links to the page with the details.

## Using Signalbox

### Is Signalbox free?

Yes. Signalbox is free. You need your own subscriptions or API access for the coding agents you run in it.

### Which coding agents does it work with?

Claude Code (`claude`), Codex (`codex`), Gemini CLI (`gemini`) and opencode (`opencode`). Install at least one and log in to it. You can set a default agent, one per project, one per ticket, and pick another for a single session. See [Supported agents](agents.md).

### Which systems does it run on?

macOS 11 Big Sur or later (Apple silicon and Intel), and 64-bit Linux as a `.deb` or an AppImage. There's no Windows build. See [Install on macOS](install-macos.md) and [Install on Linux](install-linux.md).

### Do I need Jira, Kanboard or Notion?

No. Tickets live in Signalbox itself. A tracker is optional: connect one to import issues, move cards as branches merge, and post QA notes. See [Import from a tracker](import-from-a-tracker.md).

### Do I need GitHub or Bitbucket?

No. Any git remote works for the track and the lamps. A code host connection adds pull requests, review comments, builds and **Create PR** on the ticket. See [Code hosts](code-hosts.md).

### Can I use my existing repos, branches and worktrees?

Yes. Add the folder with your repos and Signalbox finds them; nothing on disk changes. Git worktrees of a checkout show up on their own in the rail's **Checkouts** list. Branches that aren't on a ticket yet show under **Unclaimed branches** in **Loose ends**, where you can make a ticket for each. See [Add a project and its repos](add-a-project.md).

### What about sessions I started outside Signalbox?

Agent sessions in your checkouts with no ticket show in **Sidings**. Attach each one to a ticket or archive it. You can also attach a session by its id from a ticket's **Sessions** section with **Attach**. See [Sessions](sessions.md).

### Can several agents work on one ticket together?

Yes, as a crew: an orchestrator plus one agent per repo, in one split tab, talking to each other. Members can run different agents. The project needs a crew root, set when you add it or in its settings. See [Crews](crews.md).

### Does closing the window stop my sessions?

No. Closing the window hides it; sessions keep running. Bring it back from the tray lamp (the menu bar on Mac, or the Dock). To stop everything, choose **Quit** from the lamp's menu. If agents are still working, Signalbox asks first. See [Sessions](sessions.md).

### I used Signalbox V1. Can I bring my data across?

Yes. If Signalbox finds V1's data, the welcome screen and **Projects & settings** offer **Import from Signalbox V1**. It copies projects, tickets and sessions. V1's data is only read, and anything already in V2 is skipped.

## Privacy and safety

### Does Signalbox send my code anywhere?

Signalbox itself doesn't upload your code. It talks only to the services you connect (your git remotes, tracker, code host and phone alerts) and to the update server. The agents you run talk to their own providers, as they do in a terminal. See [Privacy & data](privacy-and-data.md).

### Does it track how I use it?

No. The app has no analytics or telemetry.

### Will it let agents run without asking for permission?

No. Signalbox never adds permission-skipping flags to any agent. Each agent asks for approval the way it normally does, and Signalbox shows **needs you** when it's waiting. See [States & notifications](states-and-notifications.md).

### Where are my tokens stored?

In your operating system's keychain: Keychain on macOS, Secret Service (such as GNOME Keyring) on Linux. Not in Signalbox's database. See [Privacy & data](privacy-and-data.md).

## Money and time

### Is the cost figure what I'm charged?

No. It's the API-equivalent cost: what the tokens would cost at the provider's list prices. Flat-rate plans charge differently. See [Time & cost](time-and-cost.md).

## Related

- [What is Signalbox](what-is-signalbox.md)
- [Create your first ticket](create-your-first-ticket.md)
- [Troubleshooting: Agent not found](agent-not-found.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/faq/
