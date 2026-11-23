# Code hosts

> Connect Bitbucket Cloud or GitHub so tickets show their pull requests, review comments and builds, and so you can open PRs from Signalbox.

Section: Trackers & code hosts · Updated: 2026-11-23

Connect your code host so each ticket shows the pull requests from its branches, with reviews, builds and review comments. The same connection lets you [create a PR](create-a-pr.md) from the ticket.

Signalbox supports **Bitbucket Cloud** and **GitHub** (github.com or GitHub Enterprise).

## Add a connection

1. Open **Projects & settings** and scroll to **Code hosts**.
2. Under **Code host connections**, click **Add**.
3. Choose **Bitbucket Cloud** or **GitHub**.
4. Fill in the fields below for your host.
5. Click **Test**. A working connection says **Signed in as** and your account name.
6. Click **Save**.

![Code host connections in Settings](images/settings-code-hosts.png)

Tokens are kept in your system keychain, not in Signalbox's database. When you edit a connection, leave the token empty to keep the saved one.

## Bitbucket Cloud

| Field | What to enter |
|---|---|
| **Name** | Anything, for example "Team Bitbucket" |
| **Workspace** | Optional. Only repos in this workspace use the connection. Needed for a workspace access token. |
| **Atlassian email** | The account your API token belongs to. Leave it empty for a workspace, project or repository access token. |
| **API token** | An Atlassian API token, or an access token |

To make an Atlassian API token:

1. Go to **id.atlassian.com → Security → API tokens**.
2. Click **Create API token with scopes** and choose **Bitbucket**.
3. Tick every scope, or at least `read:pullrequest`, `read:repository` and `write:pullrequest`.
4. Copy the token into Signalbox with your Atlassian email.

> **Warning:** Bitbucket refuses an Atlassian token that has no Bitbucket scopes at all. This is Bitbucket's rule, not Signalbox's. If Test says the token has no Bitbucket scopes, make a new one with Bitbucket scopes as above.

A token that works but can't read your profile (an access token, or a scoped token without the user scope) tests as "token accepted (it can't read your profile, which is fine)".

## GitHub

| Field | What to enter |
|---|---|
| **Name** | Anything, for example "Work GitHub" |
| **Host** | `github.com`, or your GitHub Enterprise host |
| **Owner** | Optional. Only repos under this user or organisation use the connection. |
| **Use my gh login** | Tick to use the GitHub CLI's login instead of a token |
| **Token** | A personal access token, if you don't use `gh` |

For a token, use either:

- a fine-grained token with **Pull requests**, **Commit statuses** and **Checks** read-only, plus **Pull requests: Read and write** if you want Create PR, or
- a classic token with the `repo` scope.

**Use my gh login** is available when `gh auth login` has been run for that host. Signalbox reads the `gh` token each time it needs it and never stores it.

## Which repos use which connection

Each repo uses the connection that matches its remote's host, then its owner (workspace or organisation). The connection's row lists the repos that use it, or **no repos yet**.

If a repo's remote is on a code host but no connection matches, Settings shows "No connection yet for:" with the repo name. Add a connection for that host or owner.

## Related

- [Pull requests on the ticket](pull-requests.md)
- [Create a PR](create-a-pr.md)
- ["Bitbucket didn't answer in time"](bitbucket-didnt-answer.md)
- [Jira](jira.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/code-hosts/
