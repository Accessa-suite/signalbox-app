# Summary

> Have the agent write a short summary of a ticket's work, what changed and why, and save it to the ticket's notes.

Section: Writing · Updated: 2026-11-23

A summary says what changed on a ticket and why, in a few sentences and a short list. It's meant for the ticket's notes, so you remember where the work stands.

## Write a summary

1. Open the ticket.
2. Click **Write…** and pick **Summary**.
3. Wait while it writes. Click **Cancel** to stop.
4. Read it, and edit it under **Edit** if needed. **Preview** shows it rendered.
5. Click **Add to notes** to put it below the ticket's current notes. When the notes are empty, the button says **Save to notes**.

To swap the notes for the summary instead, click **Replace notes**. If the ticket has notes, click again on **Replace the notes?** to confirm.

The editor closes and a message confirms, for example "Added the summary to DUKA-142's notes".

## What goes in

The agent reads the ticket, each linked branch's diff against its repo's prod branch, the commit messages, and the latest prompts and replies from the ticket's sessions. Long material is cut to fit, and the editor tells you what was cut.

It's asked for one or two sentences on the outcome, then a short list of the notable changes, plus anything left unfinished or risky. Under 200 words, in Markdown.

> **Tip:** Click **Write again** after more work lands to get a fresh summary of the current state.

## Related

- [Write… overview](write.md)
- [Tickets](tickets.md)
- [PR description](pr-description.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/summary/
