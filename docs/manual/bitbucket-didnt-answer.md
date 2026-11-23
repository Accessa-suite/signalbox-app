# Bitbucket didn't answer in time

> What it means when a ticket's pull requests show "Bitbucket didn't answer in time" or "couldn't refresh (Bitbucket slow)", and what to do.

Section: Troubleshooting · Updated: 2026-11-23

Signalbox looks up a ticket's pull requests on your code host. On a slow link, Bitbucket can take longer than Signalbox waits, and the lookup fails with this message. Your PRs, tokens and settings are fine.

## What you see

In the ticket drawer's **Pull request** section, one of:

- **couldn't refresh (Bitbucket slow) · retry**, in grey, under PRs that were found earlier. The PRs shown are from the last lookup that worked. Hover the line to see when that was.
- **Bitbucket didn't answer in time**, in amber, when no earlier lookup had found PRs for that branch.

The same words can appear after **Test** in **Projects & settings → Code hosts**, or in **Create PR**. GitHub shows the same message with its own name.

A related message, **couldn't connect to Bitbucket** (shown as **can't reach Bitbucket**), means Signalbox couldn't reach the host at all.

## Why it happens

From some networks, Bitbucket's secure handshake alone takes 5 to 10 seconds, and one PR lookup makes several calls. Signalbox already allows for this:

- Up to 25 seconds to connect, handshake included.
- Up to 60 seconds for each call.
- One retry, 1.5 seconds later, for a call that couldn't connect or timed out. A write that may have gone through, such as creating a PR, is only retried if it never connected.
- One shared connection that is kept open between lookups, so the handshake isn't repeated each time.

When all that still runs out, you see the message.

## What to do

1. Click **retry** on the grey line, or the refresh button at the right of the **Pull request** heading.
2. Wait. Every 5 minutes, Signalbox looks again at tickets that had an open PR, and a later lookup usually works.
3. Check your network: a VPN, proxy or captive portal can slow or block the connection.
4. Check Bitbucket's status page, `bitbucket.status.atlassian.com`, for an outage.

If you hit a rate limit instead, the message says so and when to try again: "Bitbucket rate limit reached; try again in …".

> **Tip:** Nothing is lost while a refresh fails. The drawer keeps showing the last PRs it found, and review comments come back when the next lookup works.

## Related

- [Pull requests on the ticket](pull-requests.md)
- [Code hosts](code-hosts.md)
- [Create a PR](create-a-pr.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/bitbucket-didnt-answer/
