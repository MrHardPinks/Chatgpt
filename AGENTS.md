# AGENTS.md

## Cursor Cloud specific instructions

### Overview

This is a single-file static HTML web application (`chatgpt.html`) — a "Bank Secure Portal" that authenticates users against a Google Spreadsheet whitelist, stores passwords in `localStorage`, and displays data fetched from another Google Spreadsheet.

### Stack

- Vanilla HTML/CSS/JavaScript (no build system, no package manager, no framework)
- Tailwind CSS loaded via CDN
- No backend; no database; no environment variables

### Running the application

Serve the file with any static HTTP server:

```bash
python3 -m http.server 8080 --directory /workspace
```

Then open `http://localhost:8080/chatgpt.html` in a browser.

### Notes

- There are no automated tests, no linter configuration, and no build step.
- The app requires internet access to fetch data from external Google Sheets CSV endpoints.
- Email whitelist validation and data fetching happen client-side via `fetch()` to hardcoded Google Sheets URLs.
- Passwords are stored per-email in the browser's `localStorage` (key format: `bank_pass_<email>`).
