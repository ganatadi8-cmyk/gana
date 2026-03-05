# Sri Kanchamma Thalli Temple — Ampuram (Static Website)

This is a small static website located in the workspace root. It includes:

- `index.html` — main page
- `styles.css` — styles
- `script.js` — lightweight client-side interactivity

Quick start

- Open `index.html` directly in a browser (double-click the file).
- Or serve locally with Python 3:

```bash
python -m http.server 8000
# then open http://localhost:8000/
```

Notes / placeholders

- Replace placeholder phone numbers (`+91-XXXXXXXXXX`) with the temple contact.
- Update the admin email in `script.js` (`admin@temple.example`) to receive form submissions.
- Replace the donate link and any placeholder images with real assets.
- Add latitude/longitude into the `geo` block in `index.html` JSON-LD for better search results.

If you want, I can:

- Replace placeholders with real values you provide.
- Add a simple contact backend (Node/Python) or a form-to-email integration.
- Create a GitHub Pages or Netlify deployment configuration.

---
Created for local preview and quick sharing.
# Sri Kanchamma Thalli Temple — Static Site (MVP)

This is a small mobile-first static website scaffold for Sri Kanchamma Thalli Temple (Ampuram). It includes hero CTAs, a sevas catalog, gallery, testimonials, and a simple contact form that uses `mailto:` as a fallback.

Quick start:

1. Open `index.html` in a browser.
2. Replace `+91-XXXXXXXXXX` in `index.html` and `script.js` with the temple phone number.
3. Replace the Google Maps iframe `src` query with a proper place or embed code if desired.
4. Replace `admin@temple.example` in `script.js` with the real admin email.

Suggested next steps:

- Add a serverless function or form handler (Netlify/Vercel) to capture submissions and send SMS/email confirmations.
- Add real photos to `/assets` and optimize with `srcset`.
- Add JSON-LD `openingHours` and real geo coordinates.
- Localize content to Telugu for better engagement.

Files:

- `index.html` — main page
- `styles.css` — styles
- `script.js` — form and CTA wiring

## Backend (optional) — Node.js + SQLite

A minimal backend is included to persist contact form submissions in a local SQLite database and serve the static site from the same process.

Install dependencies and run:

```bash
npm install
npm start
```

This starts an Express server on port `3000` by default and creates `data.db` in the workspace root. The contact form will POST to `/api/contact`. If the server isn't running the frontend will fall back to opening a `mailto:` link.

The server also provides a simple admin endpoint at `/api/contacts` that returns recent submissions in JSON (no auth — for local use only).

Update placeholders

- Replace `admin@temple.example` in `script.js` with the real recipient if you prefer email fallback.
- Replace the phone number `+91-XXXXXXXXXX` in the HTML/JS with the temple contact.

### Python (Flask) alternative

If you don't have Node.js, a Python Flask server is included as an alternative. It provides the same endpoints and stores submissions in `data.db`.

Create a virtual environment, install dependencies, and run:

```powershell
python -m venv venv
venv\Scripts\Activate
pip install -r requirements.txt
python server.py
```

This starts the Flask server on port `3000` by default. The frontend will POST to `/api/contact`. `data.db` will be created in the workspace root.
