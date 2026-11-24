# Signalbox manual

## Getting started

- [What is Signalbox](what-is-signalbox.md): Signalbox is a free desktop app for macOS and Linux that ties AI coding agent sessions to tickets, branches and the path to production.
- [Install on macOS](install-macos.md): Install Signalbox on a Mac from the .dmg and open it the first time, past the "Apple could not verify" warning.
- [Install on Linux](install-linux.md): Install Signalbox on Linux from the .deb package or the AppImage, and what each needs.
- [First run](first-run.md): What you see the first time you open Signalbox, how the window is laid out, and the three things to set up before your first ticket.
- [Add a project and its repos](add-a-project.md): Add a project from a folder of repos, set each repo's stage branches, and manage checkouts, worktrees and the crew root afterwards.
- [Create your first ticket](create-your-first-ticket.md): Every field of the New ticket form, step by step: project, title, tracker import, the branch from prod, checkout or worktree, agent or crew.
- [Start your first session](start-your-first-session.md): Start an agent on a ticket, give it its first instruction, follow it from the lamps, and pick it up again later.

## Tickets & branches

- [Tickets](tickets.md): What a ticket holds, its four statuses, notes, the agent per ticket, the Tickets list and Drafts, and how to delete a ticket.
- [The track](the-track.md): How Signalbox shows where work is, from local to prod: stages, lamps, the Loose ends board, Sidings, and the uncommitted, unpushed and cold flags.
- [Branches & worktrees](branches-and-worktrees.md): Create and link a ticket's branches, work in git worktrees, move a branch into a worktree and promote it back, and set the branch name pattern.
- [Importing from a tracker](import-from-a-tracker.md): Start a ticket from a Jira, Kanboard, Notion or Board API issue, link an existing ticket to an issue, or create an issue from a ticket or draft.

## Agents & sessions

- [Supported agents](agents.md): Signalbox runs Claude Code, Codex, Gemini CLI and opencode. How it finds them, how it picks one for a session, and what each one reports.
- [Sessions](sessions.md): Start, resume, attach and archive agent sessions on a ticket, and find your way around the tabs they open in.
- [Crews](crews.md): Run an orchestrator and one agent per repo in one split tab. The members message each other through Signalbox, and each can be a different agent.
- [States and notifications](states-and-notifications.md): What the working, needs you, done and idle lamps mean, where they show, and when Signalbox sends a desktop notification.

## Work on code

- [Changes](changes.md): Review what an agent changed in a checkout or worktree, edit the files in place, revert a file, and compare against prod or the last commit.
- [Files](files.md): Browse every file in a checkout, find one by name, and create, rename or delete files and folders without leaving Signalbox.
- [Run and worktree setup](run-and-worktree-setup.md): Make new worktrees ready to use (.env, dependencies, setup commands), and run each checkout's dev servers on its own ports, or on a phone or emulator.
- [Open in editor](open-in-editor.md): Choose the editor Signalbox opens files in: VS Code, Cursor, Zed, Android Studio, any JetBrains IDE, Xcode on a Mac, or your own command.
- [Database](database.md): Browse, filter and edit your project's local MySQL, MariaDB, Postgres or SQLite database, and run SQL, in a Data tab next to your sessions.

## Trackers & code hosts

- [Kanboard](kanboard.md): Connect a self-hosted Kanboard to Signalbox with your username and personal API token, then link tasks to tickets and move them as branches merge.
- [Jira](jira.md): Connect Jira Cloud with your Atlassian email and an API token, link issues to tickets, post QA notes and move issues through your workflow.
- [Notion](notion.md): Connect a Notion database to Signalbox through an internal integration, pick yourself as the user, and link pages to tickets.
- [Board API](board-api.md): Connect any kanban that implements the Signalbox Board API, a small REST contract, with a base URL and a token.
- [Stage → status mapping](stage-status-mapping.md): Tell Signalbox which tracker status matches each stage on your line, and let it move linked issues forward as branches merge.
- [Code hosts](code-hosts.md): Connect Bitbucket Cloud or GitHub so tickets show their pull requests, review comments and builds, and so you can open PRs from Signalbox.
- [Pull requests on the ticket](pull-requests.md): See each branch's pull request in the ticket drawer, with approvals, build state and review comments by file, and hand the comments to the agent.
- [Create a PR](create-a-pr.md): Open a pull request on Bitbucket or GitHub from a ticket's branch, with the title and description filled from your commits or written by the agent.

## Writing

- [Write… overview](write.md): Have an agent write a summary, PR description, QA note, daily log or release notes from the work. You review and edit it before anything is saved.
- [Summary](summary.md): Have the agent write a short summary of a ticket's work, what changed and why, and save it to the ticket's notes.
- [PR description](pr-description.md): Have the agent write a pull request title and description from the work, then copy it or open the PR with it.
- [QA note](qa-note.md): Have the agent write a plain-language QA note for testers, then post it on the linked issue as a comment or into its description.
- [Daily log](daily-log.md): Have the agent write what you did on a day, from your commits, session prompts and ticket moves, grouped by ticket.
- [Release notes](release-notes.md): Have the agent write plain-language release notes for promoting one stage to the next, such as develop to staging, with test steps per ticket.

## More

- [Time & cost](time-and-cost.md): See active time, tokens and API-equivalent cost per ticket, set an hourly rate per project, and export it all as CSV.
- [Search & palette](search-and-palette.md): Press Ctrl+K (⌘K on Mac) to jump to any ticket, project, view or action, or to find words said in any agent session.
- [Keyboard shortcuts](keyboard-shortcuts.md): Every keyboard shortcut in Signalbox, for Linux and macOS: new ticket, back to the board, the palette, saving files and closing dialogs.
- [Phone alerts](phone-alerts.md): Get a message on your phone through ntfy or a Telegram bot when an agent needs you or finishes while you're away from the laptop.
- [Updates](updates.md): How Signalbox checks for new versions, asks before installing, and restarts without cutting off a working agent.
- [Privacy & data](privacy-and-data.md): What Signalbox keeps on your machine, what it sends and to whom, where tokens are stored, and how to remove it all.

## Troubleshooting

- [macOS won't open Signalbox](macos-wont-open.md): Fix "Apple could not verify Signalbox" or "Signalbox is damaged" on macOS with one Terminal command, or with Open Anyway in System Settings.
- [Bitbucket didn't answer in time](bitbucket-didnt-answer.md): What it means when a ticket's pull requests show "Bitbucket didn't answer in time" or "couldn't refresh (Bitbucket slow)", and what to do.
- [Not a checkout Signalbox knows](not-a-known-checkout.md): Why Changes, Run, worktree setup or Move to worktree say "not a checkout Signalbox knows", and how to add the folder back.
- [Agent not found](agent-not-found.md): An agent shows "not installed", or its session ends at once with "command not found". How Signalbox finds agents, and how to fix it.
- [Tracker token rejected](tracker-token-rejected.md): Fix "the token was rejected" and other sign-in errors for Jira, Kanboard, Notion and Board API connections in Signalbox.
- [Update failed](update-failed.md): What to do when an update won't download or install, when the .deb update asks for a password, or when About says updates aren't available.
- [Logs and data locations](logs-and-data.md): Where Signalbox keeps its database, hook and crew files, emulator logs and keychain entries on Linux and macOS, and how to see its log output.

## FAQ

- [FAQ](faq.md): Short answers to common questions about Signalbox: cost, agents, platforms, trackers, worktrees, privacy and what happens when you close the window.

The same pages, with search: https://signalbox.accessa.co.ke/docs/
