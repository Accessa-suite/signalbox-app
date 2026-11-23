# Tracker token rejected

> Fix "the token was rejected" and other sign-in errors for Jira, Kanboard, Notion and Board API connections in Signalbox.

Section: Troubleshooting · Updated: 2026-11-23

When a tracker refuses Signalbox's sign-in, the connection's **Test**, tracker search, import and posting all fail with a message from that tracker. This page shows what each message means and how to fix it.

## First steps for any tracker

1. Open **Projects & settings → Trackers**.
2. Under **Tracker connections**, click **Edit** on the connection.
3. Check the **Base URL** and the other fields below for your tracker.
4. Paste the token again. Leave the field empty only if you want to keep the saved one.
5. Click **Test**. A working connection shows who you're signed in as.
6. Click **Save**.

Any valid token works. Signalbox doesn't ask for particular scopes; the tracker decides what the token may do, and Signalbox shows its answer.

> **Note:** Tokens are kept in your system keychain. If the message starts with `keychain:`, the keychain itself refused. Make sure it isn't locked, and on macOS choose **Always Allow** when asked. On Linux, a Secret Service such as GNOME Keyring must be running.

## Jira

| Message | What to do |
|---|---|
| `Jira: the token was rejected (HTTP 401)` | The **Email** and **API token** don't match. Use the email of the Atlassian account that made the token, and a token from id.atlassian.com → Security → API tokens. Your Atlassian password doesn't work here. |
| `Jira won't let you edit <KEY>: you need the Edit Issues permission in its project (…)` | The token works, but your Jira account can't edit that issue. Ask a Jira admin for Edit Issues in that project. |
| Other `Jira: … (HTTP 403)` | Your account can't see or change that project. Check its permissions in Jira. |

The **Base URL** is your Jira Cloud site's full HTTPS address, such as the one for `acme.atlassian.net`. Jira Server and Data Center aren't supported. See [Jira](jira.md).

## Kanboard

| Message | What to do |
|---|---|
| `Kanboard rejected the username or API token (HTTP 401)` | Check **Username** is your Kanboard login, and **Personal API token** comes from **My profile → API** in Kanboard. |
| `Kanboard doesn't allow <method> for this user (HTTP 403)` | Your Kanboard user can't do that in this project. Ask a Kanboard admin to add you to the project with enough rights. |
| `… didn't answer like Kanboard; check the URL` | The **Base URL** isn't a Kanboard server. Use the address you open Kanboard at. |

See [Kanboard](kanboard.md).

## Notion

| Message | What to do |
|---|---|
| `Notion rejected the integration secret (HTTP 401)` | Copy the **Integration secret** again from your internal integration at notion.so/profile/integrations. |
| `Notion can't see it: share the database with the integration in Notion (••• → Connections)` | Open the database in Notion, click **•••** → **Connections**, and add your integration. |
| `the Notion integration isn't allowed to do this; check its capabilities (HTTP 403…)` | In the integration's settings in Notion, turn on the capability for what failed: reading, updating or inserting content, reading or inserting comments, or reading user information (needed for **Your Notion user**). |

See [Notion](notion.md).

## Board API

| Message | What to do |
|---|---|
| `the token was rejected (HTTP 401)`, or the board's own message, such as `Token expired (unauthorized, HTTP 401)` | Get a new token from the board and paste it in. |
| `not allowed with this token (HTTP 403)` | The board refused that action for this token. Check its permissions on the board's side. |

See [Board API](board-api.md).

## Other messages

| Message | Meaning |
|---|---|
| `no token saved for this connection yet` | The keychain has no token for it. Edit the connection, paste the token and save. |
| `use an … URL (plain http is only allowed for localhost)` | The **Base URL** uses plain HTTP. Change it to the HTTPS address. |
| `… didn't answer in time` or `couldn't connect to …` | A network problem, not the token. Check the URL, your VPN or proxy, and try again. |
| `rate limited; try again shortly` | Wait a minute and try again. |

## Code host tokens

Bitbucket and GitHub tokens are set up under **Projects & settings → Code hosts**. Bitbucket has one rule of its own: it refuses Atlassian API tokens that have no Bitbucket scope at all. See [Code hosts](code-hosts.md).

## Related

- [Import from a tracker](import-from-a-tracker.md)
- [Jira](jira.md)
- [Kanboard](kanboard.md)
- [Notion](notion.md)
- [Board API](board-api.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/tracker-token-rejected/
