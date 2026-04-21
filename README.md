# MINOVA Hub Web UI

A browser-based interface for browsing and administering MINOVA distributed application networks.
Served at **[minova-afis.github.io](https://minova-afis.github.io)**.

---

## Accessing the UI

Open [minova-afis.github.io](https://minova-afis.github.io) in any modern browser.

You will be prompted for:

| Field | Description |
|---|---|
| **Hub URL** | Base URL of the Hub REST service, e.g. `https://saas-app.minova.com/minova/hub` |
| **Username** | Your Hub username (typically `user`) |
| **Password** | Your Hub password (same as the admin password in MINOVA applications) |
| **Remember me** | Persists credentials in browser localStorage across sessions |

> The Hub server must allow cross-origin requests from `https://minova-afis.github.io`.
> For isolated customer systems, point the Hub URL at the local ServiceController REST Hub address.

---

## Features

- **Tree navigation** — browse the full model hierarchy with live filter and expand/collapse
- **Value viewer and editor** — read and write node values directly in the tree or detail panel
- **File preview** — view log files, images, and PDFs inline with search, severity filtering, and auto-refresh
- **Favorites** — star any node (value, file, directory) for quick access; organized by remote model in the sidebar
- **Commands** — execute Hub commands from the context menu; supports typed arguments
- **Start / Stop** — toggle service state directly from the tree row
- **Deep linking** — share URLs that open at a specific node and viewer state (see parameters below)
- **Settings** — customize root path, hidden-node visibility, auto-refresh interval, and download size limit

---

## URL Parameters

Any link can include parameters to open the UI at a specific location and state:

| Parameter | Example | Description |
|---|---|---|
| `path` | `?path=Environment/Remotes/MyService` | Navigate directly to this node on load |
| `view` | `?view=1` | Auto-open the file viewer for the selected node |
| `auto` | `?auto=1` | Enable auto-refresh on the file viewer (5 s interval) |

**Example — open a specific service log with auto-refresh:**
```
https://minova-afis.github.io/?path=Environment/Remotes/MyService/Drives/Current/opt/service/logs/service.log&view=1&auto=1
```

---

## Profile and Defaults

When logging in for the first time from a new browser, the UI tries to load a `defaults.json` profile:

1. From the Hub backend at `Drives/Current/opt/minova/defaults.json`
2. From the frontend server (`/defaults.json`, this repository)

The profile can pre-configure root path, favorites, and display preferences for all users without manual setup.

To manage your own profile: open **Settings → Profile** to load from a file, save your current state to a file, or reset to the server defaults.

---

## Source

The UI is built from [minova-afis/web.ui.hub](https://github.com/minova-afis/web.ui.hub) and deployed here automatically on every push to `main`.
