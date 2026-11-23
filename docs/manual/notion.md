# Notion

> Connect a Notion database to Signalbox through an internal integration, pick yourself as the user, and link pages to tickets.

Section: Trackers & code hosts · Updated: 2026-11-23

Connect a Notion database so its pages act as issues for your tickets. You can import pages, comment on them, put QA notes on the page and move their status as the branch merges.

## Before you start

1. Go to **notion.so/profile/integrations** and create an internal integration for your workspace.
2. Under **Capabilities**, turn on the ones in the table below. The form lists them under the secret field too.
3. Copy the integration secret.
4. Open the database you use for tasks in Notion. Click **•••** → **Connections** and add your integration. Signalbox only sees databases shared this way.

| Capability | Used for |
|---|---|
| **Read content** | Listing databases, searching and importing pages, reading statuses. |
| **Update content** | Moving a page's status; **Replace** for a QA note. |
| **Insert content** | **Create issue**, **Send to tracker**, and **Add below** for a QA note. |
| **Insert comments** | Comments and QA notes as comments. |
| **Read user information including email addresses** | Picking yourself under **Your Notion user**. |

**Read comments** isn't needed: Signalbox only adds comments.

## Add the connection

1. Open **Projects & settings** and scroll to **Trackers**.
2. Under **Tracker connections**, click **Add**.
3. Choose **Notion**. There's no URL to fill in.
4. Enter a **Name** and paste the **Integration secret**.
5. Click **Test**. Signalbox signs in and loads the people in your workspace.
6. Under **Your Notion user**, pick yourself. "Assigned to me" searches look for this person, because an integration can't be assigned to pages itself.
7. Click **Save**.

If you skip step 6, the connection shows **no Notion user picked**, and "Mine" searches show all open items. If loading people fails, give the integration "Read user information" and test again.

## Bind a project to a database

1. In **Projects & settings → Projects**, click **Edit** on your project.
2. Under **Tracker for** your project, pick the connection.
3. Pick the database under **Notion database**. If the list is empty, share a database with the integration first.
4. If the database has more than one status or select property, choose one under **Status property**. **Automatic (the Status property)** uses the property called Status.
5. Map your stages to statuses and click **Save**. See [Stage → status mapping](stage-status-mapping.md).

## How Notion pages map to issues

- **Key:** a page's ID property (Notion's unique ID, such as `TASK-12`), else a short id.
- **Status:** the options of the status property. Notion's groups (To-do, In progress, Complete) decide each option's place in the flow. A select property gets its place guessed from the option names.
- **Description:** the page body.

## What works with Notion

| Feature | Works | Notes |
|---|---|---|
| Import a page when you create a ticket | Yes | A key like `TASK-12` becomes the ticket key when it's free. A unique ID with no prefix, such as `#12`, becomes your project's prefix and that number, such as `DUKA-12`. |
| Link an existing page | Yes | Search by words, or paste a page link or id. |
| Create a page from a ticket | Yes | **Linked issue → Create issue**. |
| Send a draft to Notion | Yes | **Send to tracker** on a draft. |
| Comments | Yes | |
| QA note on the page | Yes | **Add below** puts it at the end of the page body. Sub-pages and databases on the page are always kept. |
| Move pages as branches merge | Yes | Forward only. A status with "fail" or "reject" in its name is never left automatically. |

> **Note:** **Replace** refuses pages with more than 300 blocks: "this Notion page has … blocks, too many to replace safely; add the note below instead".

> **Tip:** Notion allows about three requests a second. When it says "rate limited", Signalbox waits and tries again on its own.

## Troubleshooting

- **Notion can't see it: share the database with the integration in Notion (••• → Connections):** the database or page isn't shared with your integration.
- **the Notion integration isn't allowed to do this; check its capabilities:** add the missing capability (for example, insert comments) in the integration's settings.

## Related

- [Stage → status mapping](stage-status-mapping.md)
- [Importing from a tracker](import-from-a-tracker.md)
- [QA note](qa-note.md)
- [Tracker token rejected](tracker-token-rejected.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/notion/
