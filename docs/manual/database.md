# Database

> Browse, filter and edit your project's local MySQL, MariaDB, Postgres or SQLite database, and run SQL, in a Data tab next to your sessions.

Section: Work on code · Updated: 2026-11-24

Each project can open its local database in a **Data** tab. You can look through tables, filter and sort them, run SQL and fix a value in a cell without leaving Signalbox.

It works with MySQL, MariaDB, Postgres and SQLite, and only with databases on your own computer.

## Open it

Either:

- In the rail, click any checkout of the project under **Checkouts**, then **Database**, or
- Press Ctrl+K (⌘K on Mac) and pick **Database: your project**.

Each project has one Data tab. If it's already open, Signalbox switches to it. Closing the tab closes the connection.

![The Data tab: tables on the left, a filtered table with one edited cell waiting to be saved](images/database.png)

## Where the connection comes from

Signalbox reads the `.env` file in each repo's main checkout and uses the first one that has database settings. It understands:

- Laravel's settings: `DB_CONNECTION`, `DB_HOST`, `DB_PORT`, `DB_DATABASE`, `DB_USERNAME` and `DB_PASSWORD`. With `DB_CONNECTION=sqlite`, `DB_DATABASE` is the file, and the default is `database/database.sqlite`.
- A `DATABASE_URL`, such as `mysql://user:pass@127.0.0.1:3306/shop`, `postgres://user@localhost/shop`, `sqlite:db/dev.sqlite3` or Prisma's `file:./dev.db`.

The password is read from `.env` each time Signalbox connects. It isn't copied anywhere.

The bar at the top of the tab shows what it's connected to and which file it came from, for example **duka @ 127.0.0.1:3306 · from duka-api/.env**.

## Change the connection

If the `.env` doesn't work for you, for example because its host is a Docker service name, give the project its own settings:

1. Click **Connection** in the Data tab's bar, or open **Projects & settings → Projects →** the project **→ Edit** and scroll to **Database**.
2. Choose **Own settings**.
3. Pick the engine, then fill in the host, port, database, user and password. For SQLite, give the file's path.
4. Click **Test** to try it, then **Save**.

![A project's Database settings, with its own MySQL connection](images/database-settings.png)

The password is kept in your system keychain, never in Signalbox's settings. To go back to the `.env`, choose **From .env** and click **Save**.

### Local databases only

Signalbox only connects to databases on this computer: `localhost`, `127.0.0.1`, `::1`, a socket path, or a name that points only to this computer. Anything else is refused with **Only local databases for now**.

A database in Docker works if its port is published on your computer. Use `127.0.0.1` and the published port, not the service name.

## Browse a table

The list on the left shows every table and view, with a rough row count. Type in **Filter tables** to find one.

Click a table to see its rows. The first 200 load straight away, and more load as you scroll down. Empty values show as a grey **NULL**, and binary data shows its size.

- **Sort:** click a column header. Click again to reverse it, and a third time to stop sorting.
- **Filter:** click **+ Filter**, pick a column, a test (such as **contains**, **=**, **<** or **is NULL**) and a value, then click **Apply**. Add more filters to narrow it down further: a row must match all of them.

## Run SQL

The SQL editor sits above the table. Click **SQL** in the bar to show or hide it.

1. Type your SQL. Table and column names are suggested as you type.
2. Press Ctrl+Enter (⌘Enter on Mac) or click **Run**.

With nothing selected, Run takes the statement your cursor is in. Select text to run exactly that, for example several statements at once.

The rows appear in the grid below, with how many there are and how long it took. Errors show above the grid. A query that returns more than 5,000 rows shows the first 5,000, marked **first 5,000 rows only**.

While something runs, **Run** turns into **Cancel**. A query is stopped after 60 seconds.

![A query in the editor and its result below](images/database-sql.png)

An `UPDATE` or `DELETE` without a `WHERE` changes every row in the table, so Signalbox asks before it runs one. Click **Run anyway** if that's what you meant.

### Recent queries

Click **Recent** to see the last 50 queries you ran in this project, newest first. Click one to put it back in the editor.

## Edit and save

You can change values in a table that has a primary key.

1. Double-click a cell, or select it and press Enter.
2. Type the new value and press Enter. Press Esc to leave it as it was. Click **NULL** next to the box to empty the cell.
3. Changed cells turn amber, and the bar counts them, for example **3 changes**.
4. Click **Save** to write them all, or **Discard** to drop them.

All the changes are saved together. If one of them fails, for example because the row was deleted in the meantime, none of them are saved, and the reason shows above the grid.

**Set NULL** empties every selected cell at once.

Tables without a primary key, and views, are **read-only**: there's no safe way to say which row to change.

## Copy rows

- Select cells and press Ctrl+C (⌘C on Mac) to copy them as tab-separated text, ready to paste into a spreadsheet. Click a row number to select the whole row, and Shift+click to select a range.
- **Copy TSV** copies the selected rows, or all of them, with the column names.
- **Copy Markdown** copies them as a Markdown table, for a ticket or a pull request.

## What's not supported yet

- Databases on other computers, and SSH tunnels.
- Changing tables and columns from the screen. You can still run `ALTER TABLE` and other SQL in the editor.
- Importing and exporting files.
- A separate database for each worktree: every worktree of the project uses the same one.
- Letting agents use the database through Signalbox.

---

Also on the website: https://signalbox.accessa.co.ke/docs/database/
