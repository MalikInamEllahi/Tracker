# AGENTS.md

## Cursor Cloud specific instructions

### Product

**Tracker** is an **Employee Tracking and Utilization System**: a single-page static web app (`employee-tracking-system.html`) that stores departments, employees, projects, and allocations in the browser via `localStorage`. There is no backend, database, or package manager in this repository.

### Branch note

`main` currently contains only `README.md`. The runnable application lives on **`cursor/employee-tracking-system-2126`** (file `employee-tracking-system.html`). Check out that branch before serving or testing the UI.

### Services

| Service | Required? | How to run |
|---------|-----------|------------|
| Static HTTP server | Yes (recommended) | From repo root: `python3 -m http.server 8080` |
| Backend / DB / Docker | No | Not used |

Open: `http://127.0.0.1:8080/employee-tracking-system.html`

You can also open the HTML file via `file://`, but using a local HTTP server matches normal browser behavior for this app.

### Lint / test / build

There are **no** `package.json`, Makefile test targets, or CI-configured lint/test scripts. Validation is manual in the browser (add employee → **Save Changes** → confirm list and toast).

### Development workflow

1. Check out `cursor/employee-tracking-system-2126` if needed.
2. Start the HTTP server (see table above).
3. Use **Admin** in the sidebar to add employees; use **Save Changes** in the top bar to persist to `localStorage`.
4. **Settings** supports demo reset, JSON import/export, and version history.

### Gotchas

- First visit auto-loads **demo data** as unsaved working state until you click **Save Changes**.
- A **draft restore** modal may appear if a newer draft exists in `localStorage` from a prior session.
- Data is per-browser profile; clearing site data removes saved employees and projects.
