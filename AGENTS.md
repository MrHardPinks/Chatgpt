# AGENTS.md

## Cursor Cloud specific instructions

This is a single-file static web application (`chatgpt.html`) with no build system, no package manager, and no dependencies to install.

### Running the app

Serve the file with any static HTTP server:

```
python3 -m http.server 8080
```

Then open `http://localhost:8080/chatgpt.html` in a browser.

### Architecture notes

- The entire app is one self-contained HTML file using Tailwind CSS via CDN.
- Authentication checks emails against a public Google Sheets whitelist (fetched as CSV). Passwords are stored in browser `localStorage`.
- After login, the app fetches data from a second Google Sheet and displays a random line.
- There are no automated tests, no linter config, and no build step.
- Internet access is required at runtime for CDN assets (Tailwind, Google Fonts) and Google Sheets API calls.
