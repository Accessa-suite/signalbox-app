# Changelog

Every Signalbox release, newest first. Also on [the website](https://signalbox.accessa.co.ke/changelog/). Installed copies update themselves.

## 0.2.4 (2026-11-24)

- New Database tab: open a project's local database from the checkout menu or the command palette. It connects using the project's .env, or settings you choose.
- Browse tables, sort and filter them, run SQL with autocomplete, and edit cells. Save applies all your edits at once.
- Works with MySQL/MariaDB, Postgres and SQLite, on databases on this computer.

Downloads: [macOS .dmg](https://signalbox.accessa.co.ke/updates/0.2.4/Signalbox_0.2.4_universal.dmg) · [Linux AppImage](https://signalbox.accessa.co.ke/updates/0.2.4/Signalbox_0.2.4_amd64.AppImage) · [Linux .deb](https://signalbox.accessa.co.ke/updates/0.2.4/Signalbox_0.2.4_amd64.deb)

## 0.2.3 (2026-11-24)

- Worktree setup: each dependency folder can be linked, copied or installed, or Signalbox can ask you each time a worktree is made.
- PHP vendor folders are copied by default, so the worktree runs its own code.

Downloads: [macOS .dmg](https://signalbox.accessa.co.ke/updates/0.2.3/Signalbox_0.2.3_universal.dmg) · [Linux AppImage](https://signalbox.accessa.co.ke/updates/0.2.3/Signalbox_0.2.3_amd64.AppImage) · [Linux .deb](https://signalbox.accessa.co.ke/updates/0.2.3/Signalbox_0.2.3_amd64.deb)

## 0.2.2 (2026-11-23)

- QA note: post it as a comment or put it in the task's description (add below, or replace).
- Settings: each tracker and code host lists the token scopes it needs, with copy buttons.
- Kanboard: paste any board link and Signalbox keeps just the site address.
- New ticket: tracker numbers like #42 become the ticket key; a checkout with uncommitted changes now says why no branch can be made and offers a new worktree.
- Pull requests keep working on slow connections to Bitbucket, and keep showing the last result if a refresh fails.
- Session tabs: Open ticket button, and the ticket title on hover.
- Crews with three or more workers each get their own pane.
- Files: new file, new folder, rename and delete.
- Worktrees that share a repo with a known checkout are recognised everywhere.
- Mobile: pick a phone, emulator or simulator for Run; Xcode as an editor on macOS.
- Fixes: matching loose-ends counts; the checkout menu always shows its tickets.

Downloads: [macOS .dmg](https://signalbox.accessa.co.ke/updates/0.2.2/Signalbox_0.2.2_universal.dmg) · [Linux AppImage](https://signalbox.accessa.co.ke/updates/0.2.2/Signalbox_0.2.2_amd64.AppImage) · [Linux .deb](https://signalbox.accessa.co.ke/updates/0.2.2/Signalbox_0.2.2_amd64.deb)

## 0.2.1 (2026-11-23)

- Create PR fills in the title and description from the branch's latest commit.
- Files view shows folders and files as a tree.
- Editors: Android Studio and the JetBrains IDEs are in the list.
- Fixes: lamps no longer overlap the time on board rows; a ticket's title no longer shrinks in a long drawer; no stray focus box in the Changes diff.

Downloads: [macOS .dmg](https://signalbox.accessa.co.ke/updates/0.2.1/Signalbox_0.2.1_universal.dmg) · [Linux AppImage](https://signalbox.accessa.co.ke/updates/0.2.1/Signalbox_0.2.1_amd64.AppImage) · [Linux .deb](https://signalbox.accessa.co.ke/updates/0.2.1/Signalbox_0.2.1_amd64.deb)

## 0.2.0 (2026-11-20)

- First release with self-updates: Signalbox checks for a new version at start and every 6 hours, asks before installing, and checks the signature first
- macOS builds: one universal app for Apple silicon and Intel, macOS 11 or later
- Create PR from the ticket, with the description written from the work
- Pull requests on the ticket: approvals, build status, review comments by file, and Fix review comments
- Daily log and release notes, gathered across tickets
- Phone alerts through ntfy or a Telegram bot
- Time and cost per ticket, with CSV export
- Ctrl+K palette (Cmd+K on macOS) with search across past sessions
- Notion and Kanboard trackers
- Crews of mixed agents talking through Signalbox's MCP server
- Agents: Claude Code, Codex, Gemini CLI and opencode

Downloads: [macOS .dmg](https://signalbox.accessa.co.ke/updates/0.2.0/Signalbox_0.2.0_universal.dmg) · [Linux AppImage](https://signalbox.accessa.co.ke/updates/0.2.0/Signalbox_0.2.0_amd64.AppImage) · [Linux .deb](https://signalbox.accessa.co.ke/updates/0.2.0/Signalbox_0.2.0_amd64.deb)
