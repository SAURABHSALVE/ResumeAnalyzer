# ResumeAnalyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/) [![Repo Size](https://img.shields.io/github/repo-size/SAURABHSALVE/ResumeAnalyzer)](https://github.com/SAURABHSALVE/ResumeAnalyzer)

Interactive, visually friendly README for the ResumeAnalyzer Django app — upload, manage and analyze resumes quickly.

---

## Table of Contents

- [Demo](#demo)
- [Quick Start](#quick-start)
- [Features](#features)
- [Architecture](#architecture)
- [Environment & Secrets](#environment--secrets)
- [Development](#development)
- [Deploying](#deploying)
- [Contributing](#contributing)
- [License](#license)

---

## Demo

Run the app locally (see Quick Start) to try the upload and dashboard features. To include a demo GIF or screenshot, place the file under `docs/` or `media/` and reference it here.

---

## Quick Start

1. Create and activate a Python virtual environment:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

2. Install dependencies:

```powershell
pip install -r resume_analyzer\requirements.txt
```

3. Copy `.env.example` to `.env` and set secrets locally (do NOT commit):

```powershell
copy resume_analyzer\.env.example resume_analyzer\.env
# edit resume_analyzer\.env and add values
```

4. Run migrations and launch:

```powershell
cd resume_analyzer
python manage.py migrate
python manage.py runserver
```

Open http://127.0.0.1:8000/ in your browser.

---

## Features

- ✅ Upload multiple resumes (stored at `media/resumes`)
- ✅ Simple dashboard and upload view in the `analyzer` app
- ✅ Extensible analysis pipeline (add NLP/parsers)

---

## Architecture

High-level flow:

- User uploads resume -> Server (Django)
- Server saves file to `media/resumes`
- Server sends file to Parser/Analyzer
- Parser extracts and stores data in the database
- Dashboard retrieves and displays extracted data

---

## Environment & Secrets

- This repo previously had a sensitive key in `resume_analyzer/.env`. DO NOT commit secrets.
- Keep your API keys in `resume_analyzer/.env` and add `.env` to your global `.gitignore` if necessary.
- If a secret was accidentally committed, rotate it immediately and follow GitHub's secret scanning guidance.

---

## Development

- Run tests (if present):

```powershell
cd resume_analyzer
python manage.py test
```

- Lint/format with your preferred tools (Black/flake8).

---

## Deploying

- For production use: Gunicorn + Nginx, set `DEBUG=False` and provide secure environment variables.

---

## Contributing

- Open issues or PRs. For significant changes, open an issue first to discuss.

---

## License

MIT

---

If you want I can: add a demo GIF, include screenshots from `resume_analyzer/media`, or generate a CI badge — tell me which.
