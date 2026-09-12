# accounts

This directory is intentionally empty in the repo (see `.gitignore`). Before running the app, create:

1. `google_creds.json` — a Google Cloud service-account key with Sheets + Drive API access.
2. `apikeys.json` — copy `apikeys.json.example` in this folder, fill in real values.
   - Generate a fresh `ANNOTATOR_PASSWORD_HASH` for a **new Kenya-specific access code**
     In a Python shell:
     ```python
     from werkzeug.security import generate_password_hash
     print(generate_password_hash("your-new-kenya-access-code"))
     ```
   - Generate `ADMIN_PASSWORD_HASH` the same way for your chosen admin password.
3. Share your Google Sheet (named to match `SHEET_NAME` in `config.py`) with the
   service account's `client_email` so it can write to it.
