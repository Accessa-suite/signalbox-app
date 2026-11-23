# Board API

> Connect any kanban that implements the Signalbox Board API, a small REST contract, with a base URL and a token.

Section: Trackers & code hosts · Updated: 2026-11-23

The Signalbox Board API is a small REST contract that any kanban can implement, for example your own team board. Connect it with a base URL and a token, and it works like the built-in trackers.

## Connect a board

1. Open **Projects & settings** and scroll to **Trackers**.
2. Under **Tracker connections**, click **Add**.
3. Choose **Board API**.
4. Fill in **Name**, **Base URL** (the full HTTPS address of the API root, for example `/api` on `board.example.com`) and **Token**.
5. Click **Test**. Signalbox reads the board's discovery document and `/me`, then says **Signed in as** you and lists the board's capabilities.
6. Click **Save**.
7. Bind a project to one of its boards under **Projects & settings → Projects →** your project **→ Edit → Tracker for** your project, and map the stages. See [Stage → status mapping](stage-status-mapping.md).

> **Note:** The base URL must use HTTPS, except for `localhost` and `127.0.0.1`.

## What a board needs to implement

Every request carries `Authorization: Bearer <token>`. Bodies are JSON. The minimum is:

| Request | What it's for |
|---|---|
| `GET /.well-known/signalbox-board` | Name, `api_version` (must be `"1"`) and capabilities |
| `GET /me` | Checks the token and powers "assigned to me" |
| `GET /boards` | The boards a project can bind to |
| `GET /boards/{id}/columns` | Columns, each with a `category` |
| `GET /boards/{id}/cards` and `GET /cards/{id}` | Search and read cards (`q` and `assignee=me` filters) |
| `PATCH /cards/{id}` with `column_id` | Move a card |

A column's `category` is one of `backlog`, `todo`, `doing`, `review` or `done`. Signalbox uses it to suggest the stage mapping and to tell forward moves from backward ones.

Discovery example:

```json
{ "name": "Team board", "api_version": "1", "capabilities": ["comments", "create"] }
```

## Optional capabilities

Signalbox hides any feature a board doesn't list in `capabilities`.

| Capability | Adds |
|---|---|
| `comments` | **Comment…** on the linked issue, and posting the QA note as a comment (`POST /cards/{id}/comments`) |
| `create` | **Create issue** on a ticket and **Send to tracker** on a draft (`POST /boards/{id}/cards`) |
| `assign` | Advertised by the board; Signalbox doesn't assign cards yet |
| `dev_info` | Advertised by the board; Signalbox doesn't send a development panel yet |

Putting the QA note in a card's description uses `PATCH /cards/{id}` with `description`. Answer HTTP 403 when the token may not edit the card.

Errors should use the matching HTTP status with a body like `{ "error": { "code": "not_found", "message": "…" } }`. Signalbox shows the message.

## Related

- [Stage → status mapping](stage-status-mapping.md)
- [QA note](qa-note.md)
- [Kanboard](kanboard.md)
- [Tracker token rejected](tracker-token-rejected.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/board-api/
