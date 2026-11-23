# Not a checkout Signalbox knows

> Why Changes, Run, worktree setup or Move to worktree say "not a checkout Signalbox knows", and how to add the folder back.

Section: Troubleshooting · Updated: 2026-11-23

Signalbox only works in folders you've added as checkouts of a repo (and in the worktrees of those checkouts). This error means the folder you used isn't one of them, or Signalbox can no longer match it to one.

## Where you see it

- **Changes & files**, or **Changes** on a ticket or tab: "not a checkout Signalbox knows".
- **Run dev servers** and **Run worktree setup**: the same message.
- **Move to worktree** in the ticket drawer: "not a main checkout Signalbox knows". This one only works on a main checkout, not on a worktree.

## How Signalbox matches a folder

A folder belongs to a checkout when:

1. it's the checkout's path, or the same folder through a symlink; or
2. it shares the checkout's git repository: a worktree of it, or a folder inside either.

So worktrees you make with `git worktree add` are found on their own. A second, separate `git clone` of the same repo isn't. It has its own repository, so it has to be added as its own checkout.

## Common causes and fixes

### The folder was never added

You opened a folder Signalbox doesn't track, or a separate clone.

1. Open **Projects & settings** and click **Edit** on the project.
2. Under **Repos**, find the repo and click **Add checkout…**.
3. Choose the folder. Signalbox checks it's a clone of that repo before adding it.

To add several repos from one folder at once, click **Add repos from a folder…** instead. See [Add a project and its repos](add-a-project.md).

### The checkout was forgotten

**Forget** on a checkout in Settings removes it from Signalbox (nothing on disk is touched). Add it again with **Add checkout…**.

### The folder moved or was renamed

Signalbox stores the full path. If you moved the repo, the old checkout shows **missing** in the rail's **Checkouts** list.

1. Add the new location with **Add checkout…**.
2. **Forget** the old one.

Tickets keep their branches: branches are linked to the repo, not to a folder.

### It isn't a git repository any more

If the folder's `.git` was removed or broken, git can't tell Signalbox which repository it belongs to. Check with:

```sh
git -C /path/to/folder rev-parse --git-common-dir
```

If that fails, fix or re-clone the repo, then add it again.

### A worktree whose main checkout was removed

A worktree points back to its main checkout's `.git`. If that checkout was deleted or forgotten, the worktree no longer matches. Add the main checkout again, or add the worktree folder as a checkout of its own.

## Related

- [Add a project and its repos](add-a-project.md)
- [Branches & worktrees](branches-and-worktrees.md)
- [Changes](changes.md)
- [Run & worktree setup](run-and-worktree-setup.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/not-a-known-checkout/
