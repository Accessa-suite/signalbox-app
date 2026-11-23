# Release notes

> Have the agent write plain-language release notes for promoting one stage to the next, such as develop to staging, with test steps per ticket.

Section: Writing · Updated: 2026-11-23

Release notes say what will ship when one stage is promoted to the next, for example `develop → staging`. They're written for QA and non-technical readers, with test steps for each change.

## Write release notes

1. Open **Loose ends** in the rail.
2. Under the count at the top, find **Release notes**. There's one button per step in your project's line, such as `develop → staging` and `staging → main`. With **All** projects selected, the buttons are grouped by project name.
3. Click the step you're about to promote. The editor opens and starts writing straight away.
4. Read the notes and edit them. **Preview** shows them rendered.
5. Click **Copy**, or **Save to file**.

![Release notes on Loose ends: one button per stage step, per project](images/release-steps.png)

**Save to file** asks where to save, with a name like `release-notes-duka-develop-to-staging.md`. If the save dialog isn't available, the file goes to your Downloads folder and the message says where.

You can also start from the palette: press Ctrl+K (⌘K on Mac) and pick **Write release notes…**, or type a step to get, for example, **Write release notes: develop → staging**. In the editor, pick the **Project** and the step under **Promoting**, then click **Write**.

> **Note:** The buttons only show for projects with at least two stage branches. A project with no stages says it "has no stage line yet". Set stages in **Projects & settings**. See [The track](the-track.md).

## What goes in

For each repo in the project, Signalbox takes the commits that are in the first stage but not yet in the second (the remote's copies first), and matches them to tickets. Each ticket brings its title, notes and linked tracker issue. Commits that belong to no ticket are listed too.

## What it looks like

- Changes under **New**, **Improved** and **Fixed**. Empty headings are left out.
- One line per change, ending with its ticket key in brackets, and its tracker issue key when it has one.
- Commits with no ticket summed up in one **Other changes** line.
- **Test before release:** for each change, its ticket key and numbered steps.

Like a QA note, it uses plain language with no code, file or branch names.

## Related

- [Write… overview](write.md)
- [The track](the-track.md)
- [QA note](qa-note.md)
- [Daily log](daily-log.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/release-notes/
