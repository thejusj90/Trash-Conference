# The Trash Conference — EOI Landing Page

Single-file static site. No build step required.

## Deploy on GitHub Pages
1. Create a new repo (e.g. `trash-conference`) and upload `index.html` to the root.
2. Go to **Settings → Pages**.
3. Under "Source," select the `main` branch and `/ (root)` folder → **Save**.
4. Your site goes live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

## Before launch — things still marked as placeholders in the file
- Curator quote/name (currently `[Curator Name], Founder, Plannex`)
- Seat counter ("13 of 50 seats offered") — static number, update manually as real applications come in
- Application close date (31 August 2026)
- Form currently only shows a front-end success message — wire it to an actual backend (see note below) before real applications depend on it.

## Wiring the form to actually receive submissions
Right now `eoiForm`'s submit handler just swaps in a success message — nothing is sent anywhere. Easiest no-backend options:
- **Formspree** (formspree.io) — add `action="https://formspree.io/f/yourFormId"` and `method="POST"` to the `<form>` tag, remove the `e.preventDefault()` in the JS, and it'll email submissions to you.
- **Google Sheets via a simple Apps Script webhook** — good if you want submissions in a spreadsheet automatically.

Ask me to wire either of these in and I can do it directly in the file.
