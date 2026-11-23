# PR description

> Have the agent write a pull request title and description from the work, then copy it or open the PR with it.

Section: Writing · Updated: 2026-11-23

The agent writes a pull request title and a description with what changed, why, how to test it and the risks. Copy it into your code host, or open the PR from Signalbox with it.

## Write a PR description

1. Open the ticket.
2. Click **Write…** and pick **PR description**.
3. Wait while it writes. Click **Cancel** to stop.
4. Check the **Title** field and the description. Edit either one. **Preview** shows the description rendered.
5. Click **Copy title** and **Copy description** to paste them into your code host, or click **Create PR with this**.

**Create PR with this** opens the [Create PR](create-a-pr.md) form with this title and description. You can still change them there. It needs a branch linked to the ticket.

## What it writes

- **Title:** plain text, in the imperative ("Add till reconciliation"), under 72 characters.
- **Description:** Markdown with four sections: **What**, **Why**, **How to test** (concrete steps) and **Risks**.

The agent reads the same material as for a [summary](summary.md): the branch diff, commits and the ticket's sessions.

> **Note:** AI attribution lines such as "Generated with Claude Code" or "Co-Authored-By: …" are removed before a PR is opened from Signalbox.

> **Tip:** In the Create PR form, **Write with the agent** writes the same text without going through Write….

## Related

- [Create a PR](create-a-pr.md)
- [Write… overview](write.md)
- [Pull requests on the ticket](pull-requests.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/pr-description/
