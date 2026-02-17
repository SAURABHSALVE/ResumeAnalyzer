# ResumeAnalyzer

ResumeAnalyzer is a lightweight Django application to upload, store and analyze resumes. It provides a simple web UI to upload PDF/Word resumes and a backend that extracts/organizes resume data for further processing.

## Features
- Upload resumes (stored in `media/resumes`)
- Simple analysis/views under the `analyzer` app
- Example templates for upload and dashboard

## Quickstart

1. Create and activate a Python virtual environment:

   python -m venv .venv
   .venv\\Scripts\\activate     # Windows

2. Install dependencies:

   pip install -r resume_analyzer\\requirements.txt

3. Copy environment variables from `.env.example` to `.env` and set values (do NOT commit secrets):

   - Create a file `resume_analyzer\\.env` based on `resume_analyzer\\.env.example`.
   - Set `OPENAI_API_KEY` or other service keys in your local `.env`.

4. Run migrations and start the development server:

   cd resume_analyzer
   python manage.py migrate
   python manage.py runserver

5. Open `http://127.0.0.1:8000/` and use the app.

## Notes & Security
- This repository previously contained sensitive keys in `resume_analyzer/.env`. Those secrets must be kept out of the repo. Use the local `.env` and add `.env` to `.gitignore` (already present in the project `.gitignore`).
- Do NOT commit `db.sqlite3`, `media/` or your virtual environment. They are ignored in `resume_analyzer/.gitignore`.

## Deploying
- For production, use a proper WSGI server (Gunicorn, uWSGI) behind a reverse proxy. Configure static/media serving and secure environment variables in the host.

## Contributing
- Open issues or PRs for bugs and feature requests.

## License
- MIT

## Contact
- Project maintainer: SAURABH (original repo owner)
