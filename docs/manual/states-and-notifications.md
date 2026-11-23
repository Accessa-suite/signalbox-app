# States and notifications

> What the working, needs you, done and idle lamps mean, where they show, and when Signalbox sends a desktop notification.

Section: Agents & sessions · Updated: 2026-11-23

Signalbox shows what each running session is doing with a coloured lamp, so you can leave agents working and come back when one needs you. When you're not looking, it can also tell you with a desktop notification.

## The four states

| Lamp | State | Meaning |
|---|---|---|
| Amber, pulsing | **working** | The agent is on a turn: thinking, editing, running tools. |
| Red, pulsing | **needs you** | The agent is waiting for you, usually to approve something or answer a question. |
| Green | **done** | The agent finished its turn and is waiting for your next prompt. |
| Unlit | **idle** | Running, but no state reported yet (or the agent doesn't report one). |

Not every agent reports every state. Claude Code reports all three. Codex only reports **done**. opencode reports none, so it always shows idle. See [Supported agents](agents.md#what-each-agent-reports).

## Where the lamps show

### The Running list

The rail's **Running** section lists every open session tab, with its lamp, ticket key, checkout and state in words: **working**, **needs you**, **done** or **idle**.

- Click a row to go to its tab.
- Hover a row to see the agent's last message.
- A crew is one row marked **crew**, with a small dot per member. Its lamp shows the most urgent member: needs you first, then working, then done. Clicking it takes you to the member that needs you, or else the one you used last. Hover to see each member's state.

### Tabs

Each session tab and crew tab has a lamp in the same colours. A crew tab shows its most urgent member. Hover the tab for the ticket title and the last message.

Inside a crew tab, each pane's header has its own lamp and state.

### The tray

Signalbox puts a lamp in the system tray (the menu bar on macOS). It shows the most urgent state across everything running:

- red: something needs you,
- amber: something is working,
- green: sessions are running and all are done or idle,
- grey: nothing is running.

Hover it for a count, such as "Signalbox: 3 running, 1 need you, 2 working". Click it to bring the window forward. Its menu has **Open Signalbox**, **Add draft…** and **Quit**.

## Desktop notifications

Signalbox sends a desktop notification when a session open in a tab:

- **needs you**: the notification says "Needs you:" and the agent's question, or
- is **done**: it says "Done:" and the agent's last message.

The title is the ticket key (plus the crew role, for a crew member) and the ticket title.

It doesn't notify you when you're already looking: the Signalbox window has focus and that session's tab is open (for a crew, that member's pane is the one you last clicked). It never notifies for **working**.

Click the notification to bring Signalbox forward on that session's tab.

> **Note:** Sessions only report states while Signalbox runs them. A session you started in another terminal shows no lamp until you resume it from its ticket.

## When you're away from the computer

Desktop notifications only help when you're at the desk. To get a message on your phone when an agent needs you, set up [Phone alerts](phone-alerts.md).

## Related

- [Sessions](sessions.md)
- [Crews](crews.md)
- [Supported agents](agents.md)
- [Phone alerts](phone-alerts.md)

---

Also on the website: https://signalbox.accessa.co.ke/docs/states-and-notifications/
